# YoutubeDL-Material

```sh
docker compose up --build
```

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
