# ZigZag  
<img src="https://github.com/DruPro/ZigZag/blob/main/zigzagdesc.png"
     alt="ZigZag — state-driven behavioral system mascot and header"
     loading="lazy"
     width="1200"
     height="800"
     style="background:#ffffff; display:block;" />

## Overview  
ZigZag is a **state-driven behavioral system** framework designed to enable entities (agents, objects, modules) to transition through well-defined states and adapt their behavior based on those states.  
Think of it as managing the *what*, *when*, and *how* of behavior in a structured way:  
- **States** define the mode or condition of the system (e.g., Idle, Active, Paused, Error).  
- **Behaviors** are the actions or responses triggered when an entity is in a given state.  
- **Transitions** govern the movement between states (based on events, conditions or time).

## Why state-driven behavior?  
- Keeps behavior logic **clear and predictable**.  
- Makes it easier to **extend**, **test**, and **maintain** modules.  
- Enables dynamic behavior like an actor switching roles, a UI component changing modes, or a trading bot shifting strategies.

## Core Concepts  
- **Entity**: any object, module or actor that has state and associated behavior.  
- **State**: named condition of the entity (e.g., `Initializing`, `Running`, `Waiting`, `Terminated`).  
- **Behavior**: a set of operations that execute when the entity is in a specific state.  
- **Transition**: rule or event that causes an entity to move from one state to another.  
- **State Machine / Graph**: representation of states and possible transitions between them.

## Usage Example  
```pseudo
entity Bot  
  state = Initializing  

on event "config_loaded":  
  if state == Initializing:  
    transition to Running  

when state == Running:  
  perform tradingCycle()  

on event "pause_signal":  
  transition to Paused  

when state == Paused:  
  wait for resumeSignal  

on event "error_detected":  
  transition to Error  

when state == Error:  
  perform cleanup()  
  transition to Terminated  
