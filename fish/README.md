# Fish shell configuration

* [Fish shell website](https://fishshell.com)
* [Fish shell docs](https://fishshell.com/docs/current/index.html#installation)

## Installation

```sh
$ brew install fish
```

## Set as default shell

```sh
# Add to the list of known shells
$ echo “/usr/local/bin/fish” | sudo tee -a /etc/shells

# Change the default shell
$ chsh -s /usr/local/bin/fish
```

## Config file

```sh
# Create a config file in the fish user folder
$ touch ~/.config/fish/config.fish
```
