# Retry & Idempotency Pattern

In distributed and serverless systems, transient failures are inevitable.  
Network glitches, temporary API unavailability, rate limits, or cloud service hiccups happen constantly.  
The Retry pattern ensures that these failures are handled automatically and safely, without human intervention or data corruption.

However, retries alone are dangerous without **idempotency**.  
Together, Retry + Idempotency form the backbone of reliable serverless execution.

---

## Conceptual Model

```text
Task Execution
     ↓
Error Detected
     ↓
Is Retryable?
   ├─ Yes → Retry with Backoff → Success → Continue
   │
   └─ No  → Send to DLQ
