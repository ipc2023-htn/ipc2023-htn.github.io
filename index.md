# International Planning Competition 2023 HTN Tracks

This is the website for the hierarchical (HTN) tracks of the
[IPC 2023](https://ipc2023.github.io).
It is the 2nd IPC containing hierarchical tracks, after its first occurance in [2020](https://ipc.hierarchical-task.net).


## Calls
Please forward the following calls to all interested parties.

 - [Call for Domains](calls/ipc2023-call-for-domains.txt)


## Preliminary Schedule

| Event  | Date  |
|---|---|
|Call for domains  |   October 12, 2022|
|Call for participation| October, 2022|
|Domain expression of interest deadline|     December 31, 2022|
|Domain submission deadline |    February 28, 2023|
|Demo problems provided    |  February 10, 2023|
|Initial planner submission |    February 28, 2023|
|Feature stop (final planner submission) |    May, 2023|
|Planner Abstract submission deadline  |   May, 2023|
|Contest run           |June, 2023|
|Results announced     |July, 2023|
|Result analysis deadline  |   August, 2023|



## Tracks
There will be (up to, provided sufficient interesst) six tracks in IPC's HTN track. These are:
 - Total-Order Agile
 - Total-Order Satisficing
 - Total-Order Optimal
 - Partial-Order Agile
 - Partial-Order Satisficing
 - Partial-Order Optimal

The semantics of these tracks is explained in the following.

### Total-Order
 - In the total-order tracks, all task networks will be totally-ordered sequences of tasks

### Partial-Order
 - In the partial-order tracks, task networks may contain any arbitrary partial order of tasks.


### Agile Track
 - single CPU core
 - 8Gb memory limit
 - 5min time limit
 - The cost of the discovered plan is ignored, only the CPU time to discover a plan is counted.
 - The score of a planner on a solved task is 1 if the task was solved within 1 second and 0 if the task was not solved within the resource limits. If the task was solved in T seconds (1 ≤ T ≤ 300) then its score is 1 - log(T)/log(300). The score of a planner is the sum of its scores for all tasks.
 - If an invalid plan is returned, all tasks in the domain are counted as unsolved.
 - If that happens in more than one domain, the entry is disqualified.

### Satisficing Track
 - single CPU core
 - 8Gb memory limit
 - 30min time limit
 - Multiple plans can be returned, the one with the lowest cost is counted.
 - The score of a planner on a solved task is the ratio C\*/C where C is the
   cost of the cheapest discovered plan and C\* is the cost of a reference plan. The score on an unsolved task is 0. The score of a planner is the sum of its scores for all tasks.
 - If an invalid plan is returned, all tasks in the domain are counted as unsolved.
 - If that happens in more than one domain, the entry is disqualified.

### Optimal Track
 - single CPU core
 - 8Gb memory limit
 - 30min time limit
 - Plans must be optimal
 - The score of a planner is the number of solved tasks
 - If a suboptimal or invalid plan is returned, all tasks in the domain are counted as unsolved.
 - If that happens in more than one domain, the entry is disqualified.


## HDDL Fragment
We will use the same input language as the previous [HTN IPC 2020](https://ipc.hierarchical-task.net/benchmarks/input-language)

## Registration
Comming soon

## Organizers
 - [Ron Alford](https://www.volus.net) (MITRE)
 - [Dominik Schreiber](https://www.dominikschreiber.de/) (Karlsruhe Institute of Technology)
 - [Gregor Behnke](https://staff.fnwi.uva.nl/g.behnke/) (University of Amsterdam)

Contact us: [ipc2023-htn@googlegroups.com](mailto:ipc2023-htn@googlegroups.com)
