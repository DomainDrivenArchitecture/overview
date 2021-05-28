https://github.com/juxt/aero

### Explicit and intentional

Configuration should be explicit, intentful, obvious, but not clever. It
should be easy to understand what the config is, and where it is
declared.

Determining config in stressful situations, for example, while
diagnosing the cause of a production issue, should not be a
[wild goose chase](http://en.wiktionary.org/wiki/wild-goose_chase).

### Avoid duplication ...

Config files are often duplicated on a per-environment basis, attracting
all the problems associated with duplication.

### ... but allow for difference

When looking at a config file, a reader will usually ask: "Does the value differ from the default, and if so how?". It's clearly better to answer that question in-place.

### Allow config to be stored in the source code repository ...

When config is left out of source code control it festers and diverges from the code base. Better to keep a single config file in source code control.

### ... while hiding passwords

While it is good to keep config in source code control, it is important to ensure passwords and other sensitive information remain hidden.

### Config should be data

While it can be very flexible to have 'clever' configuration 'programs', it can be [unsafe](http://www.learningclojure.com/2013/02/clojures-reader-is-unsafe.html), lead to exploits and compromise security. Configuration is a key input to a program. Always use data for configuration and [avoid turing-complete](http://langsec.org/occupy) languages!

### Use environment variables sparingly

We suggest using environment variables judiciously and sparingly, the way Unix intends, and not [go mad](http://12factor.net/config). After all, we want to keep configuration explicit and intentional.

Also, see these arguments [against](https://gist.github.com/telent/9742059).