# International Planning Competition 2023 HTN Tracks

This is the website for the hierarchical (HTN) tracks of the
[IPC 2023](https://ipc2023.github.io).
It is the 2nd IPC containing hierarchical tracks, after its first occurance in [2020](https://ipc.hierarchical-task.net).


## Calls
Please forward the following calls to all interested parties.

 - [Call for Domains](calls/ipc2023-call-for-domains.txt)


## Schedule

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
|Results announced     |July 12, 2023|
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

## Technical Issues.
Competitors are required to submit their code via a github repository that was set up by the track's organisers. At the time of submission, these repositories will be private and will be made public after the competition results have been announced.

Until the feature stop (see Schedule) competitors can make any change to their planners. After the feature stop, competitors are only allowed to send pull requests with bug fixes. We will review every pull request with its accompanying description of the bug fix to make sure that no significant changes or parameter tuning are possible.

As in 2020, we will provide a continous integration system. We will run planners on sample problems and publish the resulting outputs. To faciliate the detection of anomalies, each competitor is required to also submit a script that validates the planners output and that is responsible to highlight (potential) errors that need to be investigated.

As in the HTN IPC of 2020, we will use the container software Apptainer (formerly known as Singularity) to promote reproducibility and simplify program compilation. You can find the documentation on how the Apptainer files are written [here](https://apptainer.org/docs/user/1.0/definition_files.html).

We will automatically extract the configurations you want to submit from your repository. We create one configuration per Apptainer file in the *root* directory of your repository. Apptainer files are files whose file ending is **.def**.


## Registration
In order to participate in the HTN IPC, you need to register until February 28, 2023. To do so, please send an email to [Gregor Behnke](mailto:g.behnke@uva.nl) containing the following information
 - names of participants
 - email contacts of participants
 - GitHub usernames (only these will be able to modify the submitted planner)
 - the number of repositories needed (see below for details)
 - which tracks you want to participate
 - whether you require any special software that cannot be made part of the public repository (e.g. CPLEX).

As the other IPC tracks, the HTN track allows for multiple submissions to use the same planner codebase. These submissions can, e.g., differ in the configuration of the planner such as the used heuristic(s) or search techniques. Each of these configurations will (most likely) be a separate apptainer definition file (formerly Singularity file).

~~The number of submissions per participant (natural person who participates) is limited to **three** per track. That means that any person may only be named as a "participant" for at most three submission per track. This limit applies to the number of configurations and not codebases. I.e. the limit is already reached if a participant submits one codebase that is used for three configurations in one track.~~

After some discussion we have decided to update and clarify the submission rules as follows (on 24-02-2023):

Authors are allowed to submit an arbitrary number – within reason – of different planning systems per track.
Two planning systems are considered different if the relevant codebase, i.e., the parts of the code that are actually being executed, differs substantially, as judged by the organizers.
(This allows, e.g., for submitting different planning approaches as separate planning systems even if they are part of a common software.)

For each planning system submitted, a maximum of **three** different configurations may be submitted.

A modification of somebody else's HTN planning system is a valid submission if and only if the original author(s) have been made aware of the submission and are consenting.

## Organizers
 - [Ron Alford](ronwalf@volus.net) (MITRE)
 - [Dominik Schreiber](dominik.schreiber@kit.edu) (Karlsruhe Institute of Technology)
 - [Gregor Behnke](g.behnke@uva.nl) (University of Amsterdam)

Contact us: [ipc2023-htn@googlegroups.com](mailto:ipc2023-htn@googlegroups.com)
