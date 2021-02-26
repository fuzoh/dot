# Managing keys

We want to manage the master key on a live OS disconnected from internet. I use a encrypted key to store the master key, To work with the key, set the GnuPG home path to the key.
```
$ export GNUPGHOME=/mnt/keys/gnupg
```

## Master key generation

```
$ gpg --full-generate-key

$ gpg --edit-key <KEYID>

$ addkey

$ gpg --export <KEYID>.       > publickey.gpg
$ gpg --export-secret-keys    > secretkey.gpg
$ gpg --export-secret-subkeys > secretsubkey.gpg

```