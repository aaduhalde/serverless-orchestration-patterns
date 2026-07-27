# Event-Driven Architecture Pattern

The Event-Driven pattern is the foundation of modern serverless and cloud-native systems.  
Instead of executing workflows synchronously or in tightly coupled processes, systems react to **events** and propagate them through independent, loosely coupled components.

In the orchestration architecture diagram, this pattern begins at the **Event Sources** layer and activates the entire workflow through the orchestration engine.

This design allows systems to scale naturally, remain resilient to failures, and evolve without breaking existing components.

---

## Conceptual Model

```text
[ Event Source ]
       ↓
[ Stateless Function ]
       ↓
[ Orchestrator ]
       ↓
[ External Services / Storage / APIs ]
