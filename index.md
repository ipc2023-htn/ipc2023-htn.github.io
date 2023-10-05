# International Planning Competition 2023 HTN Tracks

This is the website for the hierarchical (HTN) tracks of the
[IPC 2023](https://ipc2023.github.io).
It is the 2nd IPC containing hierarchical tracks, after its first occurance in [2020](https://ipc2020.hierarchical-task.net/).


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
|Feature stop (final planner submission) |  May 31, 2023, AoE|
|Planner Abstract submission deadline  |   May 31, 2023, AoE|
|Contest run           |June, 2023|
|Results announced     |July 12, 2023|
|Result analysis deadline  |   August, 2023|



## Tracks
There will be (up to, provided sufficient interest) six tracks in IPC's HTN track. These are:
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
 - 30min time limit
 - The cost of the discovered plan is ignored, only the CPU time to discover a plan is counted.
 - The score of a planner on a solved task is 1 if the task was solved within 1 second and 0 if the task was not solved within the resource limits. If the task was solved in T seconds (1 ≤ T ≤ 1800) then its score is 1 - log(T)/log(1800). The score of a planner is the sum of its scores for all tasks.
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
We will use the same input language as the previous [HTN IPC 2020](https://ipc2020.hierarchical-task.net/benchmarks/input-language)

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


## Participants

The following planning systems participated in the HTN track of the IPC 2023.
In this table, you can find the link to the repositories for each competitior as well as links to the apptainer containers we build based on them.

### Participants

In the following table, you can find all participating planners from the HTN track of the IPC 2023. The linked github repositories contain the planners as used in the IPC evaluation.
We also provide the apptainer images we build for every planner. **Note: these links are currently not available as we have not uploaded the files yet**
*Note: We cannot provide the apptainer containers for the configurations ppro-xo-opt-as-dof-ao, ppro-xo-opt-as-dof-lmc, and ppro-xo-opt-as-lmc. These require CPLEX to build -- which cannot be provided as public download. If you which to run these planners, you need to obtain your own license for CPLEX and add CPLEX to the build process of the repository.*

| Participant | Authors | Github | Containers | 
|---|---|---|---|
| Aries | Arthur Bit-Monnot | [Aries](https://github.com/ipc2023-htn/Aries) | [aries-sat]() <br> [aries-agile]() <br> [aries-opt]() |
| SIADEX | Ignacio Vellido Expósito, Jorge Soler-Padial, <br> Juan Fernández Olivares, Luis Castillo | [SIADEX](https://github.com/ipc2023-htn/SIADEX) | [SIADEX]() |
| Lifted Linear | Ying Xian Wu, Conny Olz, <br> Songtuan Lin, Pascal Bercher | [Lifted Linear](https://github.com/ipc2023-htn/lifted-linear) | [LiftedLinear-1]() <br> [LiftedLinear-2]() <br> [LiftedLinear-3]() |
| Linear Simple | Ying Xian Wu, Conny Olz, <br> Songtuan Lin, Pascal Bercher | [Linear Simple](https://github.com/ipc2023-htn/Linear-Simple) | [LinearSimple-agile-1]() <br> [LinearSimple-agile-2]() <br> [LinearSimple-agile-3]() <br> [LinearSimple-sat-1]() <br> [LinearSimple-sat-2]() <br> [LinearSimple-sat-3]() |
| Linear Complex | Ying Xian Wu, Conny Olz, <br> Songtuan Lin, Pascal Bercher | [Linear Complex](https://github.com/ipc2023-htn/Linear-Complex/) | [LinearComplex-agile-1]() <br> [LinearComplex-agile-2]() <br> [LinearComplex-agile-3]() <br> [LinearComplex-sat-1]() <br> [LinearComplex-sat-2]() <br> [LinearComplex-sat-3]()|
| PANDApro | Daniel Höller | [PANDApro](https://github.com/ipc2023-htn/pandaPi) | [lamda-po-agl-gas-ao]()<br> [lamda-po-agl-gas-lmc]()<br> [lamda-to-agl-gbfs-ao]()<br> [lamda-to-agl-gbfs-lmc]()<br> [ppro-po-agl-gas-ff]()<br> [ppro-po-sat-gas-ff]()<br> [ppro-to-agl-gbfs-add]()<br> [ppro-to-sat-gbfs-add]()<br> *ppro-xo-opt-as-dof-ao* (requires CPLEX)<br> *ppro-xo-opt-as-dof-lmc* (requires CPLEX) <br> *ppro-xo-opt-as-lmc* (requires CPLEX) |
| TOAD | Daniel Höller | [TOAD](https://github.com/ipc2023-htn/toad) | [toad-io-dfad]()<br> [toad-io-ff]() <br> [toad-po-dfad]()  |
| PandaDealer | Conny Olz, Daniel Höller, <br> Pascal Bercher | [PandaDealer](https://github.com/ipc2023-htn/PandaDealer) | [PandaDealer-agile-1]()<br> [PandaDealer-agile-2]()<br> [PandaDealer-agile-lama]()<br> [PandaDealer-optimal]()<br> [PandaDealer-sat-1]()     <br> [PandaDealer-sat-2]() |
| PDDL4J | Gaspard Quenard, Oleksandr Firsov, <br> Damien Pellier, Humbert Fiorino | [PDDL4J](https://github.com/ipc2023-htn/PDDL4J) | [LiftedTreePath]()<br>[OptiPlan]()|

### Current Status of Planner Submissions

See [status page](https://ipc2023-htn.github.io/plannerStatus.html).


## Benchmark Set
We have used most of the domain from the previous IPC 2020. For both the Total-Order and the Partial-Order Tracks, we have added two new domains:
 - SharpSAT (total-order, by Dominik Schreiber)
 - Lamps (total-order, by Gregor Behnke)
 - Ultralight-Cockpit (partial-order, by Jane Jean Kiam)
 - Colouring (partial-order, by Gregor Behnke)

The full set of instances used for the HTN Track of the IPC 2023 is available on [github](https://github.com/ipc2023-htn/ipc2023-domains).




## Results
The IPC 2023 has concluded and the results have been presented at [ICAPS 2023 in Prague](https://icaps23.icaps-conference.org/).
The results presentation can be found [here](https://ipc2023-htn.github.io/results-presentation.pdf).
The full results tables can be found [here](https://ipc2023-htn.github.io/results).
The results website also contains links to CSV files of the results (and additionally coverage data).

You can download the raw log files of the planners and the per-instances scores for the [TO Track](https://ipc2023-htn.github.io/ipc2023-to-raw-data.zip) and the [PO Track](https://ipc2023-htn.github.io/ipc2023-po-raw-data.zip).

The winners are:


| Track | Winner | Runner-Up | 
|---|---|---|
|Total-Order Satisficing | PandaDealer-agile-lama <br> *Conny Olz, Daniel Höller, Pascal Bercher* | PANDApro $\lambda$ AO <br> *Daniel Höller* |
|Total-Order Agile | PandaDealer-agile-1 and PandaDealer-agile-lama <br> *Conny Olz, Daniel Höller, Pascal Bercher* | PANDApro $\lambda$ lm-cut <br> *Daniel Höller* |
|Total-Order Optimal | PandaDealer-optimal <br> *Conny Olz, Daniel Höller, Pascal Bercher* | PANDApro lm-cut and PANDApro DOF <br> *Daniel Höller* |
|Partial-Order Satisficing | Grounded-Linear-Satisficing <br> *Ying Xian Wu, Conny Olz, Songtuan Lin, Pascal Bercher* | PANDApro $\lambda$ AO and lm-cut <br> *Daniel Höller* |
|Partial-Order Agile | Grounded-Linear-Agile <br> *Ying Xian Wu, Conny Olz, Songtuan Lin, Pascal Bercher* | PANDApro $\lambda$ AO and lm-cut <br> *Daniel Höller* |
|Partial-Order Optimal | PANDApro lm-cut <br> *Daniel Höller* | Aries <br> *Arthur Bit-Monnot* |



The __*full results*__ tables can be found [here](https://ipc2023-htn.github.io/results).


## Proceedings and Planner Abstracts

The preliminary versions of the planner abstracts can be found here.
The participants can still submit a final version, which can also include an analysis of the behaviour of their planner in the IPC.
We will publish these proceedings once we have them.


| Participant | Planner Abstract | 
|---|---|---|---|
| Aries | [Aries](https://ipc2023-htn.github.io/proceedings/Bit-Monnot-2023-IPC-Aries.pdf) |
| SIADEX | SIADEX |
| Lifted Linear | Lifted Linear |
| Linear Simple | Linear Simple |
| Linear Complex | Linear Complex |
| PANDApro | [PANDApro](https://ipc2023-htn.github.io/proceedings/Hoeller-2023-IPC-PandaPro.pdf) <br> [PANDApro $\lambda$](https://ipc2023-htn.github.io/proceedings/Hoeller-2023-IPC-Lambda.pdf)  |
| TOAD |[TOAD](https://ipc2023-htn.github.io/proceedings/Hoeller-2023-IPC-Toad.pdf) |
| PandaDealer |  [PandaDealer](https://ipc2023-htn.github.io/proceedings/Olz-2023-IPC-PandaDealer.pdf) |
| PDDL4J | [LiftedTreePath](https://ipc2023-htn.github.io/proceedings/Quenard-2023-IPC-LiftedTreePath.pdf) <br> [OptiPlan](https://ipc2023-htn.github.io/proceedings/Firsov-2023-IPC-OptiPlan.pdf)|



## Organizers
 - [Ron Alford](ronwalf@volus.net) (MITRE)
 - [Dominik Schreiber](dominik.schreiber@kit.edu) (Karlsruhe Institute of Technology)
 - [Gregor Behnke](g.behnke@uva.nl) (University of Amsterdam)

Contact us: [ipc2023-htn@googlegroups.com](mailto:ipc2023-htn@googlegroups.com)
