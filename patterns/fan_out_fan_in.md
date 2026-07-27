# Fan-Out / Fan-In Pattern

The Fan-Out / Fan-In pattern is a core orchestration design used when a single input must be split into multiple parallel tasks and later consolidated into a single result.  
It enables massive parallelism while preserving a controlled and deterministic workflow.

In the orchestration architecture, this pattern is implemented by the orchestration layer distributing work across multiple stateless functions and then aggregating their results.

---

## Conceptual Model

```text
                Input Event
                     ↓
                Orchestrator
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
   Task Function A  Task Function B  Task Function C
        ↓             ↓             ↓
        └─────────────┼─────────────┘
                     ↓
               Aggregation Step
                     ↓
                Final Result
