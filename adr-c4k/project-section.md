# How is the c4k-project section?

## Status

accepted

## Context

We need some place to collect common used code for our Convention4Kubernetes modules.

Discussion about project-section in general
* Value
    * Smaller modules make it easier to cope with systems complexity
        * test code seperately
        * fewer people work on the same repo -> less merging
    * Increase consistency by reusing code instead of creating redundancy
    * enforces clearer architectur (decisions)
    * separation of code along the different development velocities border.
    * enforces architectural section
* Cost
    * increase of systems complexity
        * Dependency Hell / transitive dependencies
        * Section requires good documentation
        * more artifacts
    * Worse Developer Experience
        * Refactoring across multiple modules is hard to handle
        * Debugging of seperate modules my be time-consuming (multiple layers)
        * some coding tools (e.g. jump to definition) do not work over multiple repositories
        * slower development roundtrip (e.g. when using repl)
    * less awarness of what co-workes are commiting/working on
    * Danger of naive projcet section

## Decision

[](project-section-artifact.png)

1. We move common used code (predicates for spec, config handling with aero, gopass resolution, yaml serialization and encoding) to c4k-common project.
2. For cli & web frontend code we accept redundancy till we've a clearer picture on how to extract commons
3. For postgres deployments we accept redundancy till we've a clearer picture on how to extract commons

## Consequences

1. We can use described code in common.
2. After more experience we will decide about a changed section.

