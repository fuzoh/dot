# Git

## Push to multiple origins at once

```
# Add an origin for a repo :
$ git remote add origin git@codeberg.org:bastiennicoud/dot

# Add more origins url's (need to re-assign the previously created origin url)
$ git remote set-url --add --push origin git@codeberg.org:bastiennicoud/dot
$ git remote set-url --add --push origin git@github.com:bastiennicoud/dot

# List all the added url's
$ git remote -v
```

## Signing commits

1. Install a [gpg suite](https://gpgtools.org). (allows to store passphrase in macOS keychain)
2. Generate a gpg key on the computer (must use a github verified email)
3. Tell git to use the gpg key (in config, user.signingkey)
4. Add the public key to the github account
5. Lets go
