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

> https://docs.docker.com/engine/reference/commandline/images/


## Les conteneurs

> https://docs.docker.com/engine/reference/commandline/container_run/

- image choisie
- instanciation d'un nouveau conteneur

    ```bash
    $ docker container run centos:8
    ```

- Ex cmd :

```bash
$ docker image ls
$ docker container ls
$ docker container --help
$ docker container run --help
$ docker container run centos:8
$ docker image ls
$ docker container ls
$ docker container ls --help
$ docker container ls -a
$ docker container run centos:8
$ docker container ls -a
$ docker container run centos:8 cat /etc/redha-release
$ docker container run centos:8 cat /etc/redhat-release
$ cat /etc/os-release 
$ docker container ls -a
$ docker container run centos:8 sleep 60
$ docker container ls -a
$ docker system df
$ docker container run --help
$ docker container run -it centos:8
$ docker container ls
$ docker container ls -a
$ docker container --help
$ docker container start --help
$ docker container start -i afa74e96324c
```

- Cycle de vie du conteneur

    - Par défaut un conteneur s'instancie, exécute la commande prévue par l'image et s'arrête si plus de processus à l'intérieur
    - Un conteneur basé sur image applicative (daemon), ou qui exécute une commande qui dure,  déclenche un processus actif et donc reste "up"
    - Mode interactif + tty : prise de contrôle dans un conteneur
    - Mode détaché : background (instanciation du conteneur en background) => approche production


## Network

- Publication de port : permet la conexion réseau/port vers un conteneur depuis l'extérieur du docker hôte

    > https://docs.docker.com/config/containers/container-networking/


- Historique: lier des conteneurs par leur nom réseau :

  > https://docs.docker.com/network/links/

  > /!\ LEGACY

- Méthode best-practive 
    - réseau bridge de type user-defined

      > https://docs.docker.com/network/bridge/

      - Mise en place automatique de DNS entre les conteneurs d'un même réseau


    - réseau host : stack réseau du docker hote

    - Réseau none : pas de stack réseau