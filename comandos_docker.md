# Comandos Docker

Voltar à página inicial do [COMANDOMON](README.md).



## Sumário

- [Tarefas](#Tarefas)
- [Introdução](#Introdução)
- [Comandos](#Comandos)



## Tarefas

- [ ] Seguir padrão das outras lista de comandos



## Introdução

Docker é uma ferramenta para montar e compartilhar **Containers** (existem outras, como o [podman](https://podman.io/)).

Um Container é o empacotamento do código de uma aplicação, e suas dependências, que pode ser executado independente do ambiente ou máquina hospedeira.

Containers compartilham o kernel (Linux) da máquina hospedeira, diferente das máquinas virtuais, que necessitam emular um novo sistema operacional. Isso implica que Containers são mais rápidos e leves que máquinas virtuais.

Containers também são isolamentos (**namespaces** isolam a parte lógica: processos, usuários, networking, ...; **cgroups** isolam a parte física: cpu, memória, io, ...; essas funcionalidades derivando do compartilhamento do kernel da máquina hospedeira).



## Comandos

Para instalar o Docker, execute
```
curl -fsSL https://get.docker.com | bash
```
[Mais informações](https://docs.docker.com/engine/install/)

Para rodar um Container, execute
```
docker container run <nome_imagem>
```
Se a imagem não estiver disponível na máquina hospedeira, ela é baixada.

Opções
- `--tty` (ou `-t`) para alocar um terminal.
- `--interactive` (ou `-i`) para rodar em modo iterativo.
- `--detach` (ou `-d`) para rodar em segundo plano.
Para parar o Container em execução, `CTRL+C`.

Para sair do Container sem pará-lo, `CTRL+P+Q`.

Para listar os Containers em execução, execute
```
docker container ls
```
Opção `--all` (ou `-a`) para também listar Containers parados.

Para pegar informações de um (ou mais) Container, execute
```
docker container inspect <nome_ou_id_container>
```

Para se conectar ao entrypoint do Container, execute
```
docker container attach <nome_ou_id_container>
```

Para rodar um comando no Container, execute
```
docker container exec <nome_ou_id_container> <comando>
```

Para parar, iniciar, reiniciar, pausar e retomar um (ou mais) Container, execute
```
docker container stop <nome_ou_id_container>
docker container start <nome_ou_id_container>
docker container restart <nome_ou_id_container>
docker container pause <nome_ou_id_container>
docker container unpause <nome_ou_id_container>
```

Para apagar um (ou mais) Container, execute
```
docker container rm <nome_ou_id_container>
```
Opção `--force` (ou `-f`) para apagar Containers que estejam em execução.

Para ver os logs de um Container, execute
```
docker container logs --follow <nome_ou_id_container>
```
Opção `--follow` (ou `-f`) para manter o processo ativo, e ir mostrando os logs que vão aparecendo. `CTRL+C` para parar o processo.

TODO
```
docker network ls
docker volume ls
docker image ls -a

'docker network rm ' + networks
'docker volume rm ' + volumes
'docker rmi -f ' + images
```
