# lab-09

## Установка GPG

```
sudo apt install gpg
```
![Снимок экрана от 2022-05-24 01-20-46](https://user-images.githubusercontent.com/91633974/169919354-48486d5d-6e66-4b53-a8c2-439b8f412b65.png)

## Создание ключа RSA

```
gpg --list-secret-keys --keyid-format LONG
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
```
![InkedСнимок экрана от 2022-05-24 01-29-29_LI](https://user-images.githubusercontent.com/91633974/169919424-4b927669-e477-4387-acf4-5e5d4b422800.jpg)

```
gpg -K ${GITHUB_USERNAME}
GPG_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep ssb | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
GPG_SEC_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep sec | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
gpg --armor --export ${GPG_KEY_ID}
$ git config user.signingkey ${GPG_SEC_KEY_ID}
$ git config gpg.program gpg
```
![InkedСнимок экрана от 2022-05-24 01-30-52_LI](https://user-images.githubusercontent.com/91633974/169919458-bec35581-f5f1-4844-bc11-2448a00829fc.jpg)
![InkedСнимок экрана от 2022-05-24 01-31-38_LI](https://user-images.githubusercontent.com/91633974/169919499-eda5df77-d1c5-4f57-a79b-75c4a35a9afc.jpg)

```
git tag v0.0.0.2
git push origin main --tags
```
![Снимок экрана от 2022-05-24 01-38-50](https://user-images.githubusercontent.com/91633974/169919532-21ea254d-1fb3-4a79-91fa-eff4540e60cb.png)

#Релиз
```
git tag v0.1.0.0
git push origin main --tags
github-release release --user Yaros09 --repo lab-09 --tag v0.1.0.0 --name "general_10"
```
![Снимок экрана от 2022-05-24 16-32-52](https://user-images.githubusercontent.com/91633974/170048315-65efcfde-08bc-40ac-b650-d24fdc97c0fc.png)

