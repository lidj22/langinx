# [Gitea](https://about.gitea.com)

```sh
docker compose up --build
```
During gitea configuration, set the server domain/hostname to `gitea`.

Required certs:
```
/certs/staging/gitea.crt
/certs/staging/gitea.key
```

SSH config:
```
Host gitea
    HostName $IP
    Port 222
    IdentityFile ~/.ssh/$GITEA_PRIVATE_KEY
```
