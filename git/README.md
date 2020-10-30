# Git

## Generate ssh keys
```
# Generate a new ssh key
$ ssh-keygen -t rsa -b 4096 -C "email@test.com"

# Copy the public key in clipboard (only on macos)
$ pbcopy < ~/.ssh/id_rsa.pub

# Start ssh-agent
$ eval "$(ssh-agent -s)"

# Add key to the agent
$ ssh-add -K ~/.ssh/id_rsa
```

> On mac add the key to your `~/.ssh/config`, to automaticaly load keys into the agent.

## Push to multiple origins at once

```
# Add an origin for a repo :
$ git remote add origin git@codeberg.org:bastiennicoud/dot.git

# Add more origins url's (need to re-assign the previously created origin url)
$ git remote set-url --add --push origin git@codeberg.org:bastiennicoud/dot.git
$ git remote set-url --add --push origin git@github.com:bastiennicoud/dot.git

# List all the added url's
$ git remote -v
```

## Signing commits

1. Install [gpg suite](https://gpgtools.org). (allows to store passphrase in macOS keychain)
2. Generate a gpg key on the computer (must use a github verified email)
3. Tell git to use the gpg key (in config, user.signingkey)
4. Add the public key to the github account
5. Lets go

```
# Generate a GPG key
$ gpg --full-generate-key

# List existing GPG key's
$ gpg --list-secret-keys --keyid-format LONG

# Copy a public gpg key in the clipboard (macos only)
$ gpg --armor --export KEY_ID | pbcopy
```
