# MrBayes 

**Description:** MrBayes is a program for Bayesian inference and model choice across a wide range of phylogenetic and evolutionary models. MrBayes uses Markov chain Monte Carlo (MCMC) methods to estimate the posterior distribution of model parameters.

**URL:** http://mrbayes.sourceforge.net

**Team:**  

## Compilation

### Spack Package Modification

Details of any changes to the Spack recipe used.

Git commit hash of checkout for pacakage:

Pull request for Spack recipe changes:

### Building MrBayes



#### Compiler 1

```
spack install <app>%<compiler1>
```

```
$ spack spec -Il <app>%<compiler1>

```

## Test Case 1

[ReFrame Benchmark 1](#)

```
../bin/reframe -c benchmark.py -r --performance-report
```

### Validation

Details of the validation for `Test Case 1`.


### ReFrame Output

```
==============================================================================
PERFORMANCE REPORT
------------------------------------------------------------------------------
     **** 
------------------------------------------------------------------------------
```

### On-node Compiler Comparison

Performance comparison of two compilers.

| Cores | Compiler 1 | Compiler 2 |
|-------|------------|------------|
|       |            |            |


### Serial Hot-spot Profile

List of top-10 functions / code locations from a serial profile.

Use the GCC compiler.

#### Testcase 1

Profiling command used:
```
map --profile srun -N 1 -n 1 mb cynmix.nex
```

| Position | Routine               | Time (%) |
| -------- | --------------------- | -------- |
| 1        | pthread_cond_signal   | 70.8%    |
| 2        | \_\_log_finite          | 5.8%     |
| 3        | Move_ParsSPR          | 4.3%     |
| 4        | CondLikeDown_Std      | 3.5%     |
| 5        | CondLikeScaler_Std    | 3.2%     |
| 6        | TreeLikelihood_Beagle | 1.4%     |
| 7        | GetFitchPartials      | 1.4%     |
| 8        | \_\_GI\_\_IO_file_sync    | 1.4% |
| 9        | __exp_finite | 1.2% |
| 10       | CondLikeRoot_Std | 0.9% |

#### Testcase 2

Profiling command used:

```
map --profile srun -N 1 -n 1 mb hym.nex
```

| Position | Routine                                                      | Time (%) |
| -------- | ------------------------------------------------------------ | -------- |
| 1        | CondLikeDown_Std                                             | 22.8%    |
| 2        | CondLikeScaler_Std                                           | 17.8%    |
| 3        | __log_finite                                                 | 15.1%    |
| 4        | CondLikeRoot_Std                                             | 9.6%     |
| 5        | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcStatesPartials(float*, int const*, float const*, float const*, float const*, int, int) | 6.9%     |
| 6        | beagle::cpu::EigenDecompositionCube<float, 1>::updateTransitionMatrices(int, int const*, int const*, int const*, double const*, double const*, float**, int) | 3.8%     |
| 7        | Likelihood_Std                                               | 3.3%     |
| 8        | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcPartialsPartials(float*, float const*, float const*, float const*, float const*, int, int) | 3.1%     |
| 9        | __exp_finite                                                 | 2.9%     |
| 10       | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcEdgeLogLikelihoods(int, int, int, int, int, int, double*) | 2.7%     |

#### Testcase 3

Profiling command used:

```
map --profile srun -N 1 -n 1 mb kim.nex
```

| Position | Routine                | Time (%) |
| -------- | ---------------------- | -------- |
| 1        | CheckExpandedModels    | 50.0%    |
| 2        | ProtID [inlined]       | 16.7%    |
| 3        | \_\_GI\_\_IO_file_sync | 16.7%    |
| 4        | MPI_Finalize           | 16.7%    |
| 5        | main                   | <0.1%    |
| 6        | CommandLine            | <0.1%    |
| 7        | ParseCommand           | <0.1%    |
| 8        | DoExecute              | <0.1%    |
| 9        | DoMatrixParm           | <0.1%    |
| 10       | CharacterCode          | <0.1%    |

#### Testcase 4

Profiling command used:

```
map --profile srun -N 1 -n 1 mb primates.nex
```

| Position | Routine                                                      | Time (%) |
| -------- | ------------------------------------------------------------ | -------- |
| 1        | pthread_cond_signal                                          | 62.8%    |
| 2        | __log_finite                                                 | 11.2%    |
| 3        | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcEdgeLogLikelihoods(int, int, int, int, int, int, double*) | 7.6%     |
| 4        | Move_ParsSPR                                                 | 2.6%     |
| 5        | TreeLikelihood_Beagle                                        | 2.1%     |
| 6        | beagle::cpu::EigenDecompositionCube<float, 1>::updateTransitionMatrices(int, int const*, int const*, int const*, double const*, double const*, float**, int) | 1.9%     |
| 7        | log                                                          | 1.2%     |
| 8        | GetFitchPartials                                             | 1.2%     |
| 9        | __exp_finite                                                 | 1.1%     |
| 10       | GetParsFP                                                    | 0.9%     |



### Full Node Hot-spot Profile

List of top-10 functions / code locations from a full node profile.

Use GCC compiler.

#### Testcase 1

Profiling command used:
```
map --profile srun -N 1 -n 64 mb cynmix.nex
```

| Position | Routine             | Time (%) | MPI (%) |
| -------- | ------------------- | -------- | ------- |
| 1        | MPI_Allreduce       | 89.6%    | 89.6%   |
| 2        | pthread_cond_signal | 5.9%     |         |
| 3        | MPI_Waitall         | 0.9%     | 0.9%    |
| 4        | __log_finite        | 0.4%     |         |
| 5        | CondLikeDown_Std    | 0.3%     |         |
| 6        | Move_ParsSPR        | 0.3%     |         |
| 7        | open64              | 0.2%     |         |
| 8        | GetFitchPartials    | 0.2%     |         |
| 9        | MPI_Isend           | 0.2%     | 0.2%    |
| 10       | CondLikeScaler_Std  | 0.2%     |         |

#### Testcase 2

Profiling command used:

```
map --profile srun -N 1 -n 64 mb hym.nex
```

| Position | Routine                                                      | Time (%) | MPI (%) |
| -------- | ------------------------------------------------------------ | -------- | ------- |
| 1        | MPI_Allreduce                                                | 42.1%    | 42.1%   |
| 2        | CondLikeDown_Std                                             | 12.0%    |         |
| 3        | CondLikeScaler_Std                                           | 8.6%     |         |
| 4        | __log_finite                                                 | 7.9%     |         |
| 5        | MPI_Waitall                                                  | 6.0%     | 6.0%    |
| 6        | CondLikeRoot_Std                                             | 5.0%     |         |
| 7        | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcStatesPartials(float*, int const*, float const*, float const*, float const*, int, int) | 3.2%     |         |
| 8        | __exp_finite                                                 | 1.6%     |         |
| 9        | beagle::cpu::EigenDecompositionCube<float, 1>::updateTransitionMatrices(int, int const*, int const*, int const*, double const*, double const*, float**, int) | 1.4%     |         |
| 10       | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcPartialsPartials(float*, float const*, float const*, float const*, float const*, int, int) | 1.4%     |         |

#### Testcase 3

Profiling command used:

```
map --profile srun -N 1 -n 64 mb kim.nex
```

| Position | Routine                     | Time (%) | MPI (%) |
| -------- | --------------------------- | -------- | ------- |
| 1        | MPI_Allreduce               | 54.2%    | 54.2%   |
| 2        | MPI_Finalize                | 25.9%    | 25.9%   |
| 3        | MPI_Bcast                   | 4.4%     | 4.4%    |
| 4        | \_\_GI\_\_IO_file_fopen     | 3.1%     |         |
| 5        | CompressData                | 2.4%     |         |
| 6        | CheckExpandedModels         | 1.7%     |         |
| 7        | IsIn [inlined]              | 1.4%     |         |
| 8        | ParseCommand                | 0.7%     | 54.2%   |
| 9        | strlen                      | 0.7%     |         |
| 10       | \_\_GI\_\_IO_file_underflow | 0.6%     |         |

#### Testcase 4

Profiling command used:

```
map --profile srun -N 1 -n 64 mb primates.nex
```

| Position | Routine                                                      | Time (%) | MPI (%) |
| -------- | ------------------------------------------------------------ | -------- | ------- |
| 1        | MPI_Allreduce                                                | 86.8%    | 86.8%   |
| 2        | pthread_cond_signal                                          | 6.6%     |         |
| 3        | __log_finite                                                 | 1.4%     |         |
| 4        | MPI_Waitall                                                  | 1.0%     | 1.0%    |
| 5        | beagle::cpu::BeagleCPU4StateImpl<float, 1, 0>::calcEdgeLogLikelihoods(int, int, int, int, int, int, double*) | 0.9%     |         |
| 6        | MPI_Barrier                                                  | 0.7%     | 0.7%    |
| 7        | Move_ParsSPR                                                 | 0.3%     |         |
| 8        | TreeLikelihood_Beagle                                        | 0.3%     |         |
| 9        | MPI_Send                                                     | 0.2%     | 0.2%    |
| 10       | beagle::cpu::EigenDecompositionCube<float, 1>::updateTransitionMatrices(int, int const*, int const*, int const*, double const*, double const*, float**, int) | 0.2%     |         |

### Strong Scaling Study

On-node scaling study for two compilers.

| Cores | Compiler 1 | Compiler 2 |
|-------|------------|------------|
| 1     |            |            |
| 2     |            |            |
| 4     |            |            |
| 8     |            |            |
| 16    |            |            |
| 32    |            |            |
| 64    |            |            |


### Off-Node Scaling Study

Off-node scaling study comparing C6g and C6gn instances.

| Nodes | Cores | C6g | C6gn |
|-------|-------|-----|------|
| 1     | 8     |     |      |
| 1     | 16    |     |      |
| 1     | 32    |     |      |
| 1     | 64    |     |      |
| 2     | 128   |     |      |
| 4     | 256   |     |      |
| 8     | 512   |     |      |


### On-Node Architecture Comparison

On-node scaling study for two architectures.

| Cores | C6gn (Aarch64) | C5n (X86) |
|-------|----------------|-----------|
| 1     |                |           |
| 2     |                |           |
| 4     |                |           |
| 8     |                |           |
| 16    |                |           |
| 32    |                |           |
| 64    |                |           |


## Optimisation

Details of steps taken to optimise performance of the application.
Please document work with compiler flags, maths libraries, system libraries, code optimisations, etc.

### Compiler Flag Tuning

Compiler flags before:
```
CFLAGS=
FFLAGS=
```

Compiler flags after:
```
CFLAGS=
FFLAGS=
```

#### Compiler Flag Performance

| Cores | Original Flags | New Flags |
|-------|----------------|-----------|
| 1     |                |           |
| 2     |                |           |
| 4     |                |           |
| 8     |                |           |
| 16    |                |           |
| 32    |                |           |
| 64    |                |           |


### Maths Library Report

Report on use of maths library calls generated by (Perf Lib Tools)[https://github.com/ARM-software/perf-libs-tools].
Please attach the corresponding apl files.


### Maths Library Optimisation

Performance analysis of the use of different maths libraries.


| Cores | OpenBLAS | ArmPL | BLIS |
|-------|----------|-------| ---- |
| 1     |          |       |      |
| 2     |          |       |      |
| 4     |          |       |      |
| 8     |          |       |      |
| 16    |          |       |      |
| 32    |          |       |      |
| 64    |          |       |      |


### Performance Regression

How fast can you make the code?

Use all of the above aproaches and any others to make the code as fast as possible.
Demonstrate your gains by providing a scaling study for your test case, demonstrating the performance before and after.



## Report

### Compilation Summary

Details of lessons from compiling the application.

### Performance Summary

Details of lessons from analysing the performance of the application.


### Optimisation Summary

Details of lessons from performance optimising the application.