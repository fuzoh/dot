# Configure a new repo

## Setting name for specific repo

```sh
git --config --local user.name "<NAME>"
git --config --local user.email "<NAME>"
git --config --local user.signingkey "<KEY_ID>"

git remote add origin <URL>
git remote set-url --add --push origin <PUSH_URL>
```