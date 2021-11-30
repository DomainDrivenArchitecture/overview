# Quasi idempotence

Idempotence means you can execute a function multiple times and always get the same result.

In real world idempotence typically is difficult because of three aspects:

1. Equality hard to define
2. There are unreflected changes in functions input
3. Function has side effects

For intentionally side effect executing functions we introduce "quasi idempotence". To avoid ambiguousness we have to define on which attribute we recognize former executions.

## Status

Approved.

## Context

Software installation with provs. In case of temporal broken external dependencies we want to be able to do another installation over the previous partially broken one.

We follow the principle "build from scratch", so we leave the question of software version updates unconsidered here.

## Consequence

1. add / change (a line) in existing files
   1. Solution: Query for changed location respecting the file type / format and skip if it was already performed. We try to avoid this case and use separate files instead of modifying existing ones.
2. installation of an single / directory file
   1. Solution: If the file/directory exists, we consider installation successful and skip this step in another installation run
3. installation of many files/directories
   1. Solution: If the last file/directory exists, we consider installation successful and skip this step in another installation run - this is useful in order to skip time consuming steps. For fast / trivial steps we can choose solution 2.
4. install apt/deb package
   1. Solution: Query whether package (name without version) is installed (either implicitly e.g. in case of apt or explicitly in other cases to avoid unnecessary downloads etc)
5. running docker containers
   1. Solution: Query whether  container with name (we have to provide the name on container start) is already running
