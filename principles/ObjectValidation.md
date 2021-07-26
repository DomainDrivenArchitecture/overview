# Object validation

Validation of objects is essential for the quality of object-oriented programs.

This page provides a rough overview of different techniques and strategies around object validation.

## Basics

### Object types
The appropriate kind of validation may differ on the kind of object, whether it is
* mutable or
* immutable

### Validation results 

Validation results can be divided into:
* **Detailed**: containing a list of violations
* **Simple**: reporting just one violation (or even only success/failure), either with a simple or a generic message

### Technical possibilities
Most languages are offering the following possibilities for failure handling:
* Return values
* Exceptions

### Validation time
* Before object creation
* After creation (but before actual usage of the data)

### Validation patterns
* Validation on existing objects/states during business operations (i.e. after object creation) (see https://enterprisecraftsmanship.com/posts/validation-and-ddd/) :
  * validate / isValid methods (backdraw: race conditions can lead to invalid state)
  * in application services (backdraw: potential business logic leakage)
  * TryExecute (backdraw: no CQRS separation: potential state change AND returning data (i.e. error message))
  * Execute / CanExecute => call separately „Can“- and „execute“-method, (partial) state is stored locally which means no race conditions can lead to an invalid state
* Validation during object creation (avoids invalid objects), without public validation method
  * In constructor
  * In factory method (e.g. create method)
  * In Factory
  * In Builder
* Validation before object creation with public validation method (avoids invalid objects, allows CQRS and detailed results):
  * With (static/class level) validation AND factory method - (https://savoiragile.com/2012/06/28/english-object-validation-on-immutable-objects/ & https://reflectoring.io/java-immutables/ )
  * Using Essence pattern (https://stackoverflow.com/questions/9776193/good-practice-to-validate-immutable-values-objects )
  * Also Factory and Builder pattern could be added with a validate method (https://stackoverflow.com/questions/16221010/should-the-factory-pattern-contain-validation-logic ), but does not seem very common


## Potential strategies

### Strategies for validations after object creation 
(From https://enterprisecraftsmanship.com/posts/validation-and-ddd/):
  * The Execute / TryExecute pattern works best for task-based scenarios.
  * For CRUD scenarios, you need to choose between Execute / TryExecute and validation in application services. The choice comes down to purity versus ease of implementation.

### Strategies for validations before object creation

  * With (static/class level) validation AND factory method (for less complex cases)
  * Essence pattern (for complex cases)

### Strategies for validation results:
* Detailed, containing a list of violations => for crud operations of multi-field input
* Simple: reporting one violation either with a simple or a generic message => for task-based operations (user just wants to execute a task and wants to know if the task was successful or not resp. why not)

### Technical mechanisms:
* Return value for “expected” failures
* Exception for “unexpected” failures

https://stackoverflow.com/questions/99683/which-and-why-do-you-prefer-exceptions-or-return-codes
https://stackoverflow.com/questions/5460101/choosing-between-exception-and-return-value
https://enterprisecraftsmanship.com/posts/error-handling-exception-or-result/

---
###Appendix
Possibilities for creation of objects (patterns, etc):
* Constructor
* Factory method (e.g. create method)
* Factory
* Builder
* Essence
* Other creational patterns: Prototype, Object Pool, Abstract Factory, Singleton
      