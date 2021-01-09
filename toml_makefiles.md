# Makefiles in toml with cargo make

> Cargo make is a rust lang make command, can be used with makefiles vritten in toml !!!

[Cargo make docs](https://sagiegurari.github.io/cargo-make/)

## Simple Makefile.toml

```toml
[tasks.your_task]
command = "cargo"
args = ["build", "--verbose", "--all-features"]
script = '''
brew services start php
echo "hello"
'''
```

## Execute the makefile tasks

```
$ cargo make your_task
```
