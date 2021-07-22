# One layer of configuration

## Status

Accepted

## Context

In configuration management often convention code is mixed-up with installation and configuration code. 
In order to enable reuse we discussed whether we want to separate convention from installation and configuration code.

## Decision

* To keep it simple, we follow the mixup strategy.
  
## Consequence

* We use only one layer of configuration
* We are the primary intended user