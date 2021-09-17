# Git

## Generate ssh keys
```sh
# Generate a new ssh key (with modern ed25519 algorithm)
$ ssh-keygen -t ed25519 -C "email@test.com"
# Or on legacy system
$ ssh-keygen -t rsa -b 4096 -C "email@test.com"

# Copy the public key in clipboard (only on macos)
$ pbcopy < ~/.ssh/id_ed25519.pub
# Or copy the key by opening it on your favourite editor or with cat

# Start ssh-agent
$ eval "$(ssh-agent -s)"

# Add key to the agent
$ ssh-add -K ~/.ssh/ed25519
```

> On mac add the key to your `~/.ssh/config`, to automaticaly load keys into the agent.
> `$ open ~/.ssh/config`
> Add on `config` file :
> ```
> Host *
>   AddKeysToAgent yes
>   UseKeychain yes
>   IdentityFile ~/.ssh/id_ed25519
> ```

## Push to multiple origins at once

```sh
# Add an origin for a repo :
$ git remote add origin git@codeberg.org:bastiennicoud/dot.git

# Add more origins url's (need to re-assign the previously created origin url)
$ git remote set-url --add --push origin git@codeberg.org:bastiennicoud/dot.git
$ git remote set-url --add --push origin git@github.com:bastiennicoud/dot.git

# List all the added url's
$ git remote -v
```

## Use a specific ssh key

First generate à new key, and add it to the agent.

Then add the key to the `.ssh/config`:
```
Host my-other-ssh-key-name
>   AddKeysToAgent yes
>   HostName git-hosting.dev
>   UseKeychain yes
>   IdentityFile ~/.ssh/the_other_ssh_key
```

Then use the `Host` identifier in your git repository configuration. EX: `git@my-other-ssh-key-name:my-repo-identifier.git`

## Signing commits

You need a GnuPG distrubution, and personal gpg keys.

```sh
# List existing GPG key's
$ gpg --list-secret-keys --keyid-format LONG

# Add the key id to the git config
$ git config --global user.signingkey <key id>

# Sign all commits by default
$ git config --global commit.gpgsign true

# Copy a public gpg key in the clipboard (macos only)
$ gpg --armor --export KEY_ID | pbcopy

# Set GPG_TTY var on linux
export GPG_TTY=$(tty)
```
