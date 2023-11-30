# [Docker Registry](https://docs.docker.com/registry/)

```sh
docker compose up --build
```

Required certs:
```
/certs/staging/registry.crt
/certs/staging/registry.key
```

Test
```sh
docker pull ubuntu
docker image tag ubuntu $HOSTNAME:5000/ubuntu
docker push $HOSTNAME:5000/ubuntu
```