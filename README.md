# OS Laboratory Activity 3
## Multilevel Queue and Real-Time CPU Scheduling

### Student Information
- Name: Reuyan, Alwyn Jade
- Course and Section:  BSCA - B186
- Instructor: Ma. Fe Bahinting
- Date Submitted: December 10, 2026

### I. Introduction
This laboratory activity focuses on the implementation and simulation of Multilevel Queue (MLQ) and real-time CPU scheduling algorithms using Python and GitHub. The goal is to explore how MLQ organizes processes into different queues with specific scheduling policies, and how Rate Monotonic Scheduling (RMS) and Earliest Deadline First (EDF) manage periodic tasks based on priority and deadline requirements.

### II. Objectives
- Explain the operation of Multilevel Queue, RMS, and EDF scheduling algorithms.
- Implement MLQ scheduling using Round Robin and FCFS.
- Implement preemptive RMS and EDF scheduling simulations using Python.
- Generate and interpret Gantt charts showing process and task execution.
- Calculate CPU utilization, waiting time, turnaround time, and deadline compliance.
- Create and manage a GitHub repository containing Python source code and laboratory documentation.

### III. Scheduling Algorithms
1. Multilevel Queue Scheduling
2. Rate Monotonic Scheduling
3. Earliest Deadline First

### IV. Program Implementation
The scheduling algorithms were simulated using Python 3. The `mlq.py` script utilizes nested lists and deques to simulate multi-level queue preemption based on the Round Robin time quantum. Real-time schedulers (`rms.py` and `edf.py`) simulate a tick-by-tick system over 20ms, recalculating deadlines and sorting tasks based on shortest period (RMS) or absolute deadlines (EDF) to allocate the CPU appropriately. 

### V. Test Data
The MLQ system schedules 5 processes using predetermined arrival and burst times across two queues. The RMS and EDF algorithms schedule three independent periodic tasks, T1, T2, and T3, with distinct execution times and relative deadlines matching their periods. 

### VI. Results and Discussion
Execution generated matching Gantt charts simulating CPU allocations.
- **MLQ:** Interactive processes heavily preempted batch jobs, performing correctly.
- **RMS:** The sufficient bound (~77.98%) safely captured the 65% CPU utilization, resulting in PASS and zero deadline misses.
- **EDF:** The classical single-processor condition was met (65% <= 100%), yielding zero deadline misses while demonstrating a dynamic priority queue mapping. 

### VII. Algorithm Comparison
| Criteria | MLQ | RMS | EDF |
| :--- | :--- | :--- | :--- |
| Scheduling basis | Queue priority | Task period | Absolute deadline |
| Priority assignment | Fixed queue priority | Fixed task priority | Dynamic task priority |
| Scheduling type | Depends on queue policy | Preemptive | Preemptive |
| Main application | Process classification | Periodic real-time tasks | Deadline-based real-time tasks |
| Deadline monitoring | Not inherent | Yes | Yes |

### VIII. Conclusion
Implementing real-time scheduling algorithms mathematically highlights how systems balance throughput with task prioritization logic. Using dynamic allocation (like EDF) proves highly efficient for absolute deadline mapping, while fixed queue assignments (MLQ and RMS) create predictable, rigid priority boundaries for varying process classes.
