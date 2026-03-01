# AzureLogicApps-Concurrency

Examples of Azure Logic Apps Standard workflows focused on **concurrency** and its effects — in particular, race conditions that arise when shared variables are mutated inside a parallel `For each` loop.

## Overview

The `For each` action in Azure Logic Apps Standard runs iterations **in parallel by default**. When multiple iterations concurrently read and write the same workflow variable (e.g. incrementing a running total), the results can be incorrect due to race conditions. This repository contains three side-by-side workflows that illustrate the problem and demonstrate two different solutions.

## Repository structure

```
AzureLogicApps-Concurrency/
├── README.md
└── LogicAppConcurrency/
    ├── LogicAppConcurrency.code-workspace   # VS Code multi-root workspace
    ├── Function/                            # Supporting Azure Functions project
    └── LogicApp/                            # Logic Apps Standard project
        ├── host.json
        ├── connections.json
        ├── .funcignore
        ├── .gitignore
        ├── .vscode/
        ├── lib/
        ├── RaceCondition/
        │   └── workflow.json
        ├── Synchronous/
        │   └── workflow.json
        └── Threshold/
            └── workflow.json
```

## Workflows

All three workflows are **Stateful** and share the same basic structure:

1. Initialize two variables: `Sum` (integer, 0) and `Special Message` (string).
2. Initialize a `Data Array` variable containing the integers 1–100.
3. Use a `For each` loop to iterate over the array, incrementing `Sum` by each item and checking whether a special condition is met.
4. After the loop, return an HTTP 200 response if `Sum` equals 5,050 (the expected total of 1+2+…+100), or HTTP 400 if it does not.

### RaceCondition

**Path:** [`LogicAppConcurrency/LogicApp/RaceCondition/workflow.json`](LogicAppConcurrency/LogicApp/RaceCondition/workflow.json)

| Property | Value |
|---|---|
| Trigger | HTTP Request (`When_a_HTTP_request_is_received`) |
| `For each` concurrency | Default (parallel) — no `runtimeConfiguration.concurrency` setting |

**Scenario:** Demonstrates the race condition. Because iterations run in parallel, multiple iterations can read the same `Sum` value simultaneously before any of them has written back their increment. The result is that `Sum` never reaches 5,050 and the workflow returns HTTP 400.

Additionally, the loop contains an inner condition that checks whether `Sum` equals **exactly** 10 in order to append a special message. In parallel execution this exact-equality check is likely to be skipped entirely (the value jumps past 10 between reads), so `Special Message` remains empty.

**Expected outcome:** HTTP 400 — the calculated sum will be wrong.

---

### Synchronous

**Path:** [`LogicAppConcurrency/LogicApp/Synchronous/workflow.json`](LogicAppConcurrency/LogicApp/Synchronous/workflow.json)

| Property | Value |
|---|---|
| Trigger | HTTP Request (`When_a_HTTP_request_is_received`) |
| `For each` concurrency | `runtimeConfiguration.concurrency.repetitions: 1` (sequential) |

**Scenario:** Fixes the race condition by setting `repetitions` to `1`, which forces the `For each` loop to process one iteration at a time. Each iteration fully completes (read → increment → write) before the next one starts, so `Sum` accumulates correctly.

The `repetitions` setting lives inside the `For each` action definition:

```json
"runtimeConfiguration": {
  "concurrency": {
    "repetitions": 1
  }
}
```

The same exact-equality check (`Sum == 10`) is used for the special message, and it now fires reliably because execution is sequential.

**Expected outcome:** HTTP 200 — `Sum` equals 5,050 and (if the sum reaches exactly 10 during iteration) the special message is appended.

---

### Threshold

**Path:** [`LogicAppConcurrency/LogicApp/Threshold/workflow.json`](LogicAppConcurrency/LogicApp/Threshold/workflow.json)

| Property | Value |
|---|---|
| Trigger | HTTP Request (`When_a_HTTP_request_is_received`) |
| `For each` concurrency | Default (parallel) — no `runtimeConfiguration.concurrency` setting |

**Scenario:** Explores an alternative approach to the special-message problem without disabling parallelism. Instead of checking `Sum == 10` *inside* the loop (which parallel execution makes unreliable), the special-message check is moved **after** the loop. A post-loop condition checks whether `Sum > 10` and whether the message has not already been set, then appends the message if needed.

> **Note:** Moving the threshold check outside the loop avoids the in-loop race condition for that specific check, but the parallel `For each` still causes a race condition on `Sum` itself. The final `Sum` value will still be incorrect and the workflow returns HTTP 400.

**Expected outcome:** HTTP 400 — the calculated sum will still be wrong due to the parallel race condition on `Sum`.

---

## Concurrency settings reference

| Setting | Location | Effect |
|---|---|---|
| `runtimeConfiguration.concurrency.repetitions` | Inside a `Foreach` action | Maximum number of loop iterations that may run at the same time. Set to `1` for sequential (safe for shared variables); higher values (or omitted) allow parallel execution. |

The default parallelism for `For each` in Azure Logic Apps Standard is up to 20 concurrent iterations.

---

## Running locally

### Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/)
- [Azure Logic Apps (Standard) VS Code extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurelogicapps)
- [Azure Functions Core Tools v4](https://learn.microsoft.com/azure/azure-functions/functions-run-local)
- [Azurite storage emulator](https://learn.microsoft.com/azure/storage/common/storage-use-azurite) (included with the VS Code extension or installable via npm)
- [.NET SDK](https://dotnet.microsoft.com/download) (for the companion `Function` project)

### Open the workspace

1. Open VS Code.
2. Select **File → Open Workspace from File…** and choose [`LogicAppConcurrency/LogicAppConcurrency.code-workspace`](LogicAppConcurrency/LogicAppConcurrency.code-workspace).

   This opens the `LogicApp` and `Function` folders as a multi-root workspace with the correct extension settings pre-configured.

### Start the Logic App locally

1. Press **F5** (or **Run → Start Debugging**). VS Code will start Azurite and the Logic Apps runtime using the tasks defined in `.vscode/tasks.json`.
2. Once the runtime is running, right-click any workflow folder (`RaceCondition`, `Synchronous`, or `Threshold`) in the Explorer and select **Overview** to retrieve its local callback URL.

### Trigger the HTTP workflows

Send an HTTP GET or POST request to the workflow callback URL. For example, using `curl`:

```bash
curl -X POST "<callback-url>"
```

Compare the responses across the three workflows to observe how concurrency settings affect the final `Sum` value and whether the special message appears.

