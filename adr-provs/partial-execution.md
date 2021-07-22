# partial execution of provs

## Status

to be discussed

## Context

We want to be able to execute single provision steps to apply partial installation / configuration.

### Options
1. ClassAndFunction
 - Abhängigkeiten
 - Transport von Credentials
2. Switch on cli per parameter / mapping in code from parameter to function
3. Per KotlinScript file
4. Configurable in the configuration

## Decision

* Wir repräsentieren unsere Configuration

* Wir nutzen erst mal die Struktur von DDD application / domain / infrastructure - unter Vorbehalt
  * Vorbehalt1: besseren Namen für fachliches finden
  * Vorbehalt2: entscheiden, was in der domain testbar sein muss

* Wir nutzen nur einschichtige Konfiguration, da wir nur noch uns selbst als Nutzerkreis ansehen.
