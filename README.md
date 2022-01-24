# Formation Docker

## Liens URL

> https://www.docker.com/

## Installation Docker

- Client
- Engine

> https://docs.docker.com/

> https://docs.docker.com/engine/install/

  - Via packages fournis par la distri (pas forcément dispo (RedHat) ou pas forcément à la dernière version)

  - Via package fournis par le répo officiel Docker

- Docker engine : service Linux

    ```bash
    $ sudo systemctl status docker
    ```

    - En configuration par défaut : il stocke tous ses éléments dans ```/var/lib/docker```

## Client Docker

```bash
$ docker version
$ docker --help
$ docker system --help
$ docker system df
$ docker system df --help
$ docker system info
```

- Lister les ressources :

    - image: 
        ```bash
        $ docker image ls
        ```
    - conteneurs:
        ```bash
        $ docker container ls
        ```

## Les images docker

- Docker hub : registry publique

> https://hub.docker.com/


## Les conteneurs

- image choisie
- instanciation d'un conteneur

    ```bash
    $ docker container run centos:8
    ```