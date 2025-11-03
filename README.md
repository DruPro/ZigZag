# ZigZag  
<img src="https://github.com/DruPro/ZigZag/blob/main/zigzagdesc.png"
     alt="ZigZag — state-driven behavioral system mascot and header"
     loading="lazy"
     width="400"
     style="background:#ffffff; display:block;" />

## Overview  
ZigZag is a **state-driven behavioral system** framework designed to enable entities (agents, objects, modules) to transition through well-defined states and adapt their behavior based on those states.  
Think of it as managing the *what*, *when*, and *how* of behavior in a structured way:  
- **States** define the mode or condition of the system (e.g., Idle, Active, Listening, Error).  
- **Behaviors** are the actions or responses triggered when an entity is in a given state.  
- **Transitions** govern the movement between states (based on events, conditions, or timeouts).

## Why state-driven behavior?  
- Keeps behavior logic **clear and predictable**.  
- Makes it easier to **extend**, **test**, and **maintain** modules.  
- Enables dynamic network systems such as protocol negotiation, node discovery, or adaptive communication.

## Core Concepts  
- **Entity**: any object, node, or process that has state and associated behavior.  
- **State**: named condition of the entity (e.g., `Initializing`, `Connected`, `Transmitting`, `Terminated`).  
- **Behavior**: a set of operations that execute when the entity is in a specific state.  
- **Transition**: rule or event that causes an entity to move from one state to another.  
- **State Machine / Graph**: representation of states and possible transitions between them.

## Usage Example  
```pseudo
entity Node  
  state = Initializing  

on event "network_ready":  
  if state == Initializing:  
    transition to Connecting  

when state == Connecting:  
  attempt handshake()  

on event "handshake_success":  
  transition to Connected  

when state == Connected:  
  begin dataExchange()  

on event "timeout":  
  transition to Reconnecting  

when state == Reconnecting:  
  retry handshake()  

on event "fatal_error":  
  transition to Terminated  

when state == Terminated:  
  cleanup()  
  log "Node terminated."
