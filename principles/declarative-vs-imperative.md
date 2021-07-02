# Imperative vs declarative

Configuration management tools are usually classified as either **imperative** or **declarative**.
Imperative means that you define the steps which are necessary to achieve the goal.
Declarative means that you just define the state you want to achieve, and the tooling makes it happen.

### Declarative

**Pros**
* Easier configuration as you just define the desired end-state 
  and you don't need to check nor remember the actual state. 


**Cons**

* No or only little control over the execution order resp. control flow
* Race conditions can lead to bugs which can be difficult to reproduce resp. solve
* Difficult to debug
* The built-in checks for the actual state and the required steps usually don't cover all edge case.
  Declarative provisioning may not be able to meet complexer requirements and/or may result in errors.


### Imperative

**Pros**
* Gives control over the execution order resp. control flow
* Easier to debug step-by-step execution

**Cons**

* More complicated and more work as you need to define the required steps yourself and may need to check the current state.


### Implarative

We prefer systems which are offering best of both worlds, i.e. advantages from the **imperative** paradigm as:
* control of execution order (with all kinds of looping and conditional possibilities)
* easy debugging
* being able to cover complex cases

as well as important advantages of the **declarative** paradigm, such as:
* easy configuration
* idempotence resp. quasi-idempotence
* no need to check nor remember the system state.

We call this "implarative".

## Clear results overview

With provisioning you hope everything goes fine but of course also errors can occur.
To be able to solve potential problems it is important to get clear information what are the steps performed and where did it go wrong and why.
So, while for successful executions it is nice to have, in case of errors it is essential to get a clear results overview.

![](/resources/images/results-overview.png)