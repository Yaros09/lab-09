# Lab9-TiMP

## Установка GPG

```
sudo apt install gpg
```

## Создание ключа RSA

```
gpg --list-secret-keys --keyid-format LONG
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
```

```
gpg -K ${GITHUB_USERNAME}
GPG_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep ssb | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
GPG_SEC_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep sec | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
gpg --armor --export ${GPG_KEY_ID}
$ git config user.signingkey ${GPG_SEC_KEY_ID}
$ git config gpg.program gpg
```

```
git tag v0.0.0.2
git push origin main --tags
```
