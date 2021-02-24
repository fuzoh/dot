# Some security tips

## Check signatures

```
# Check signature on windows
# Available algorithms MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512
$ certUtil -hashfile C:\myFileToCheck.txt <ALGORITHM>

# Check gpg signature
# Import the public key
$ gpg --import <PUBKEY>
# Verify the signature
$ gpg --verify <SIGNATURE> <FILE>
```
