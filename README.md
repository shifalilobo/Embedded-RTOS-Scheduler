# Embedded RTOS Scheduler

Designed and implemented a lightweight RTOS scheduler in C to simulate task scheduling mechanisms used in real-time systems. Developed core modules including Task Control Blocks (TCB), Ready Queue, Scheduler, Context Switching Logic, and Timer Tick Handler. Verified functionality through simulation and timing analysis.


## Overview

Designed and implemented a simplified RTOS scheduler inspired by FreeRTOS principles. The project focuses on task management and scheduling algorithms for real-time embedded systems. The scheduler supports task priorities, delays, and periodic execution. The design demonstrates how an RTOS kernel manages multiple tasks and allocates CPU resources based on scheduling policies.


## Key Features

### Developed a lightweight RTOS scheduler supporting:

- Task creation and deletion
- Ready queue management
- Priority-based scheduling
- Round-robin scheduling
- Tick timer handling
- Task delay mechanism
- Context switching simulation
- Idle task implementation
- Periodic task execution
- Cooperative and preemptive scheduling modes

### Designed and integrated core modules including:

- Task Control Block (TCB)
- Scheduler Core
- Ready Queue
- Delay Queue
- Tick Timer Module
- Context Switch Handler
- Idle Task
- Task Manager

### Implemented task states:

- Ready
- Running
- Blocked
- Suspended

### Supported scheduling algorithms:

- Round Robin Scheduling
- Priority-Based Preemptive Scheduling

### Functional capabilities:

- Task selection based on priority
- Time slicing between equal-priority tasks
- Tick-driven scheduling
- Blocking and unblocking tasks
- Delay and timeout handling
- CPU utilization through idle task execution


## System Architecture

The RTOS scheduler consists of a timer tick module, scheduler core, task queues, and a context switching mechanism. Tasks are selected from the ready queue according to their priority and execution state.


## Architecture Diagram
<img width="4240" height="5924" alt="image" src="https://github.com/user-attachments/assets/65a02045-7c51-406f-adce-fb71c6c421bf" />



## Scheduler Flow

```text
System Tick Interrupt
        │
        ▼
Tick Timer Module
        │
        ▼
Scheduler Core
        │
 ┌──────┴──────┐
 ▼             ▼
Ready Queue   Delay Queue
        │
        ▼
Highest Priority Task
        │
        ▼
Context Switch Handler
        │
        ▼
Task Execution
```

## Core Modules

### Task Control Block (TCB)

Maintains information associated with each task, including:

- Task ID
- Task State
- Priority
- Stack Pointer
- Delay Counter

### Ready Queue

Stores tasks that are ready for execution and enables task selection based on scheduling policy.

### Delay Queue

Maintains blocked tasks waiting for a timeout to expire before becoming ready again.

### Tick Timer Module

Generates periodic tick events used for task scheduling and timeout management.

### Scheduler Core

Determines the next task to execute based on priority and scheduling algorithm.

### Context Switch Handler

Performs task switching by saving and restoring task contexts.

### Idle Task

Runs whenever no user tasks are ready for execution, ensuring efficient CPU utilization.


## Task States

The scheduler manages tasks through the following states:

- Ready
- Running
- Blocked
- Suspended


## Scheduling Algorithms

### Round Robin Scheduling

Tasks having the same priority are executed in a cyclic manner with equal CPU time allocation.

### Priority-Based Scheduling

The scheduler always selects the highest-priority ready task for execution.


## Directory Structure

```text
Embedded-RTOS-Scheduler
│
├── src
│   ├── scheduler.c
│   ├── scheduler.h
│   ├── task.c
│   ├── task.h
│   ├── queue.c
│   ├── queue.h
│   ├── tick_timer.c
│   ├── tick_timer.h
│   ├── context_switch.c
│   ├── context_switch.h
│   └── main.c
│
├── include
│
├── test
│   ├── scheduler_test.c
│   └── task_test.c
│
├── docs
│   ├── architecture.png
│   ├── scheduler_flow.png
│   └── execution_trace.png
│
└── README.md
```


## Verification

Performed functional verification using software-based test cases to validate:

- Task creation and initialization
- Round-robin scheduling behavior
- Priority-based task selection
- Delay handling and task wake-up mechanism
- Context switching operation
- Queue management and task transitions


## Tools & Technologies

- C Programming
- Embedded Systems
- RTOS Concepts
- Scheduling Algorithms
- Linked Lists and Queues
- GCC
- VS Code
- Git
- GitHub


## Applications

This scheduler architecture can be applied in:

- Embedded firmware development
- Automotive Electronic Control Units (ECUs)
- Battery Management Systems (BMS)
- IoT devices
- Industrial automation systems
- Real-time monitoring systems


## Outcome

Successfully demonstrated the operation of a lightweight RTOS scheduler and gained hands-on experience in task management, scheduling algorithms, queue implementation, context switching, and timing mechanisms. This project strengthened practical understanding of RTOS internals and concepts commonly used in FreeRTOS and embedded firmware development.


## Future Enhancements

The following features can be added to further enhance the scheduler:

- Software timers
- Semaphores
- Mutexes
- Message queues
- Event groups
- Dynamic memory management
- Priority inheritance mechanism
- Inter-task communication
- Multi-level priority queues
- Support for periodic tasks
