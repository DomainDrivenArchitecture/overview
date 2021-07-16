# partial execution of provs

## Status

accepted

## Context

Configuration for our provisioning software provs.

## Decision

We provide a materialized configuration (represented by classes or schema). Configuration is read at application start and injected into services / components (see https://martinfowler.com/articles/injection.html).
