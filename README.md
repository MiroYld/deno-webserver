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