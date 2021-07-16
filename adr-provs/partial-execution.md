# partial execution of provs

## Status

to be discussed

## Context

We want to be able to execute single provision steps to apply partial installation / configuration.

### Options
1. By CLI and specify ClassAndFunction
2. Switch on cli per parameter / mapping in code from parameter to function
3. Per KotlinScript file
4. Configurable in the configuration

General points to keep in mind:
- Dependencies
- Transport of credentials