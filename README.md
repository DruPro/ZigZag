<img src="https://github.com/DruPro/ZigZag/blob/main/zigzagdesc.png"
  alt="ZigZag — state-driven behavioral system mascot and header"
  loading="lazy"
  width="400"
  style="background:#ffffff; display:block;" />

## Overview

**ZigZag** is a **state-driven behavioral framework** built for **event-driven architecture**.
It allows entities — known as **actors** — to react to events, transition between well-defined states, and adapt their behavior dynamically.

Each actor can **create other actors**, forming hierarchical systems where **child actors** can also spawn or manage their own sub-actors. This enables complex, distributed, and adaptive systems to emerge from modular, isolated units of logic.

---

## Core Philosophy

### ⚙️ Event-Driven Design

At its core, ZigZag operates on **events**. Events drive transitions, trigger behaviors, and facilitate communication between actors. This creates a system where reactivity and responsiveness are natural — not bolted on.

### 🧩 State-Driven Behavior

Every actor in ZigZag behaves as a **finite-state machine**. Its current state determines how it responds to incoming events and what actions it performs.
This ensures clarity, predictability, and modular logic flow throughout the system.

### 🌱 Actor Hierarchy

Actors are **self-contained behavioral units** that can:

* **Create new actors** dynamically.
* **Manage child actors** through supervision or delegation.
* **Propagate events** through an actor hierarchy.

This hierarchical composition allows ZigZag systems to model both **micro-behaviors** and **macro-level orchestration** seamlessly.

### 🔁 Reactive Bindings

Actors can maintain **two-way bindings** with shared data or signals. Changes in one actor’s data automatically propagate to others that depend on it — keeping systems synchronized without tight coupling.

### 🔒 Isolated Shared Mutability

ZigZag introduces **controlled shared state**. Actors can share mutable references safely, ensuring no race conditions occur, even in concurrent or networked environments. Each actor operates within a defined **access window** or through **message-passing**, preserving deterministic behavior.

---

## Architecture

| Layer                | Description                                               |
| -------------------- | --------------------------------------------------------- |
| **Event Layer**      | Routes events across actors and hierarchies.              |
| **FSM Core**         | Governs state transitions and per-state behavior logic.   |
| **Actor System**     | Manages actor creation, lifecycles, and hierarchies.      |
| **Signal System**    | Handles reactive two-way bindings and change propagation. |
| **Shared Context**   | Provides safe, isolated shared state between actors.      |
| **Isolation Engine** | Enforces access boundaries and prevents race conditions.  |

---

## Roadmap

### ✅ **Phase 1 — FSM Core (MVP)**

* [x] Define `State`, `Behavior`, and `Transition` primitives
* [x] Support event-based transitions
* [x] Establish per-state lifecycle hooks
* [x] Enable event routing within an actor

---

### 🔄 **Phase 2 — Event System**

* [ ] Global and local event buses
* [ ] Event priority queues and scheduling
* [ ] Event bubbling across parent-child hierarchies
* [ ] Scoped event broadcasting

---

### 🌱 **Phase 3 — Actor System**

* [ ] Actor creation and destruction lifecycle
* [ ] Child actor management (supervision and delegation)
* [ ] Hierarchical event propagation
* [ ] Dynamic actor spawning during runtime

---

### ⚡ **Phase 4 — Reactive System**

* [ ] Implement two-way reactive data bindings
* [ ] Change propagation with dependency tracking
* [ ] Update deduplication and loop prevention
* [ ] Integration with event-driven signals

---

### 🔒 **Phase 5 — Shared Context & Isolation**

* [ ] Scoped shared mutable contexts
* [ ] Safe concurrent access mechanisms
* [ ] Atomic state updates with rollback support
* [ ] Access isolation windows per actor

---

### 🌐 **Phase 6 — Distributed Architecture**

* [ ] Remote event dispatch and routing
* [ ] Network-level actor communication
* [ ] Remote spawning and distributed state replication
* [ ] Adaptive node discovery and protocol negotiation

---

### 🧰 **Phase 7 — Developer Experience**

* [ ] Visual event and state debugger
* [ ] Hierarchical actor inspector
* [ ] Interactive simulation and playback tools
* [ ] Documentation and live examples

---

## Vision

ZigZag’s purpose is to provide a **foundation for event-driven, actor-based, and state-oriented systems**.
It merges the clarity of **finite-state machines**, the scalability of **actor hierarchies**, and the flexibility of **reactive dataflow**, all under a model that remains **predictable, testable, and extensible**.

From UI components to network nodes and distributed runtimes, ZigZag aims to make **complex behavior simple, modular, and composable**.

