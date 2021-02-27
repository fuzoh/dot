# Managing keys

We want to manage the master key on a live OS disconnected from internet. I use a encrypted key to store the master key, To work with the key, set the GnuPG home path to the key.
```sh
$ export GNUPGHOME=/mnt/keys/gnupg
```

## Key generation

```sh
# Key generation
$ gpg --full-generate-key

# Generating a revoke certificate
$ gpg --output <REVOKE_CERT_FILE> --gen-revoke <KEY_ID>
```

## Key edition

```sh
# Enter in edition mode for a specific key
$ gpg --edit-key <key-id>

# Some commands to interact with keys in edition mode
$ help # Display all commands
$ key # Select a subkey
$ revkey # Revoke a key
$ addkey # Create a subkey
$ expire # Change expiration
$ adduid # Add new identity to the key
```

## Export keys

```sh
# Export keys in binary format
$ gpg --export --output <PUBLIC_KEY.asc> <key-id>
$ gpg --export-secret-keys --output <SECRET_KEY.asc> <key-id>
$ gpg --export-secret-subkeys --output <SECRET_SUBKEYS.asc>

# Export in ascii armored format
# Use the --armor (-a) flag
$ gpg --export --output <FILE.asc> --armor <key-id>
$ gpg --export-secret-keys --output <FILE.asc> --armor <key-id>
```

## Import keys

```sh
# Check key fingerprint
$ gpg --with-fingerprint <KEY_FILE>

# Import a public key
$ gpg --import <A_PUBLIC_KEY_FILE>

# Import backuped secret key
$ gpg --allow-secret-key-import --import <A_PRIVATE_KEY_FILE>
```
