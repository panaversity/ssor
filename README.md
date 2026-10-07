# SSOR: State System of Record

> **The Temporal State & Lineage Layer for Enterprise Agentic Systems**  
> *Part of the Panaversity Agentic Infrastructure Suite (`KSoR` + `SSOR` + `DSoR`)*

---

## What is SSOR?

**SSOR (State System of Record)** is a bitemporal, typed hierarchical vector graph substrate designed to store, persist, and audit dynamic workflow state for enterprise AI agents.

In enterprise automation, failure rarely stems from a lack of model reasoning—it stems from the **absence of structured, persistent, and auditable state**. Enterprise workflows are not isolated, stateless tasks; they live in an evolving web of changing environments, historical interactions, policy updates, and human interventions.

While traditional databases store raw data and logs store telemetry, SSOR provides a single, unified source of truth for **what state the world is in right now, how it got here, and why**.

---

## What SSOR Does

SSOR aggregates and structures fragmented enterprise interactions into a continuous, compounding state layer through four main functions:

1. **Persists Tri-Layer Workflow Context:**
   * **Semantic Layer:** Encapsulates domain concepts, entity definitions, and structural relationships.
   * **Episodic Layer:** Captures time-bound events, user interactions, environment changes, and historical context with explicit valid-time windows.
   * **Procedural Layer:** Maps active state machine execution graphs, step dependencies, constraint violations, and retry histories.

2. **Maintains Bitemporal Lineage (W3C PROV-O):**
   Tracks both **Valid Time** (*when a statement was true in reality*) and **Transaction Time** (*when the system recorded it*), ensuring complete auditability with explicit `wasDerivedFrom`, `wasGeneratedBy`, and `attributedTo` provenance links.

3. **Continuously Hydrates Agent Context:**
   Instead of re-deriving state from raw unstructured text on every execution, SSOR incrementally ingests telemetry from agent runs, hydrating the graph so context compounds over time.

4. **Provides ISO/IEC 39075 GQL & Vector Querying:**
   Exposes a standardized pattern-matching interface that lets AI agents execute declarative graph queries combined with semantic vector search over temporal states.

---

## How SSOR Connects to KSoR and DSoR

SSOR completes the **Panaversity Infrastructure Triad**, acting as the dynamic temporal engine that connects static institutional knowledge (**KSoR**) with governed execution and action logs (**DSoR**).
