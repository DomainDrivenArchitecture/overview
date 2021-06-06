# Idempotence and quasi-idempotence

Idempotence means that you can apply the same function multiple times without changing the result beyond the initial application.

However, there are cases in which you don't want strict idempotence. E.g. if you are installing a program or cloning a git repo a second time, you might want to get the latest version,
even if an older version has already been installed earlier. This behavior is also known as quasi-idempotence.
