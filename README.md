# Benchmarking Examples With gradle-profiler
These examples assume _gradle-profiler_ is installed on your machine and you are currently within the project directory for the project you want to benchmark.

## Basic Benchmark Scenarios From The Command Line
Benchmark the `assemble` task using the default settings
```
gradle-profiler --benchmark --project-dir . assemble
```

Benchmark a _clean_ `assemble` build using the default settings
```
gradle-profiler --benchmark --project-dir . clean assemble
```

Save benchmarking output to a custom directory
```
gradle-profiler --benchmark --project-dir . --output-dir benchmarking/ assemble
```

Change the number of _warm-up_ and/or _measured_ builds
```
gradle-profiler --benchmark --project-dir . --warmups 10 --iterations 15 assemble
```

## Complex Benchmark Scenarios Using A .scenarios File

Take a look at the `benchmarking.scenarios` file.

That file defines 4 benchmarking scenarios
- assemble_clean
- incremental_build
- assemble_clean_caching
- assemble_no_op

To run these scenarios, execute the following
```
gradle-profiler --benchmark --project-dir . --scenario-file benchmarking.scenarios
```
