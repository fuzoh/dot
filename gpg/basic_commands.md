# GPG basic commands

```
# Generating a key
$ gpg --full-generate-key

# Exporting a key
$ gpg --export --output <FILE.asc> --armor <KEY_ID>

# Import a key
$ gpg --import <A_PUBLIC_KEY_FILE>
```

## Encryption

```
# Encrypt
$ gpg --recipient <KEY_ID> --encrypt <FILE_TO_ENCRYPT>

# Decrypt
$ gpg --output <OUTPUT_FILE> --decrypt <ENCRYPTED_FILE.gpg>
```

## Sign

```
# Sign a file (embeded signature)
$ gpg --sign <FILE> --output <FILE_SIGNATURE.sig>
# Text signature (use --clearsign flag)
$ gpg --clearsign <FILE> --output <FILE_SIGNATURE.sig>

# Sign and generate a detached signature
$ gpg --detach-sign <FILE> --output <FILE_SIGNATURE.sig> --armor

# Verify a signate (you need to import the signer public key before)
$ gpg --verify <SIGNED_FILE>
$ gpg --verify <DETACHED_SIGNATURE> <FILE>
```

## Sign and encrypt

```
# Encrypt and sign
$ gpg --sign <FILE> --encrypt --recipient <KEY_ID> [--armor]

# Decrypt and verify
$ gpg --output <FILE> --decrypt <ENCRYPTED_FILE>
```