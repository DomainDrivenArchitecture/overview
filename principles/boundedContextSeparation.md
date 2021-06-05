# Bounded Context Separation Priciple

For mudole section there are several tactiques. One important is the section alongside of Bounded Contexts (Martin Fowlder: Bounded Context)[https://martinfowler.com/bliki/BoundedContext.html].

But separation of modules always has it's up and downs:

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
