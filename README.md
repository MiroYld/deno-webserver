# deno-webserver
deno-webserser deployment using kubernetes

## Before installation

1) Add an entry in the /etc/hosts file that associates
Minikube's IP address to host "deno.minikube".
```
$ echo "$(minikube ip) deno.minikube" | sudo tee -a /etc/hosts
```
## Use with github repository

```
$ git clone https://github.com/MiroYld/deno-webserver.git
$ cd deno-webserver/charts/deno/
$ helm install deno-webserver . -f values.yaml

```
go to : http://deno.minikube

## Use with Helm

```
1) helm repo add miroyld https://miroyld.github.io/deno-webserver/
2) helm install deno-webserver miroyld/deno-webserver
```

## Docker

1) **For mariadb use :** https://hub.docker.com/_/mariadb
2) **For deno use :**  https://hub.docker.com/r/codebuds/deno-webserver

## Changelog

deno-webserver:
- 0.5.1
  - Update documentation and NOTES
- 0.5.0
  - Upgrade deno version to 1.6.0
  - Add initContainer that check mariadb state before starting web server
- 0.4.0
  - Fix maria db connection
  - Add Readiness probe to maria db
  - Add Liveness probe to webserver
- 0.3.0
  - Use release variable to create deploy
  - Change deno-webserver image to `codebuds/deno-webserver:1.5.1`
  - Know issue:
    - mariadb container might failed to create (Will be fixed in next release)
- 0.2.0
  - Add GitHub action to create release
  - Add GitPage
  - Change MariaDB to StatefulSet
- 0.1.0
  - Create helm chart
  - Create deno-webserver
  - Create mariadb