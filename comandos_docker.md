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




### Containers

Para rodar um Container, execute
```
docker container run <nome_imagem>
```
Se a imagem não estiver disponível na máquina hospedeira, ela é baixada.

Opções
- `--tty` (ou `-t`) para alocar um terminal.
- `--interactive` (ou `-i`) para rodar em modo iterativo.
- `--detach` (ou `-d`) para rodar em segundo plano.
- `--name` para dar um nome ao Container (caso contrário, um nome aleatório é designado a ele).
Para parar o Container em execução, `CTRL+C`.

Para sair do Container sem pará-lo, `CTRL+P+Q`.

Para listar os Containers em execução, execute
```
docker container ls
```
Opções
- `--all` (ou `-a`) para também listar Containers parados.
- `--size` (ou `-s`) para mostrar o tamanho dos Containers.

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

Para apagar todos os Containers parados, execute
```
docker container prune
```
Opção `--force` (ou `-f`) para não perguntar se realmente deseja apagá-los.

Para ver os logs de um Container, execute
```
docker container logs --follow <nome_ou_id_container>
```
Opção `--follow` (ou `-f`) para manter o processo ativo, e ir mostrando os logs que vão aparecendo. `CTRL+C` para parar o processo.

Para visualizar as estatísticas de uso de recursos nos Containers, execute
```
docker container stats
```
Para parar o comando em execução, `CTRL+C`.

Pode ser passado o nome de um Container, para listar apenas ele.

Opção `--all` (ou `-a`) para também listar Containers parados.

Para mostrar os processos em execução em um Container, execute
```
docker container top <nome_ou_id_container>
```



### Imagens

Para montar uma imagem, execute
```
docker image build --tag <nome:versao> --file <caminho_do_Dockerfile> <caminho>
```
Atalho do comando: `docker build`

Opções
- `--tag` (ou `-t`) para nomear a imagem.
- `--file` (ou `-f`) para passar o caminho do Dockerfile.

Para listar as imagens baixadas, execute
```
docker image ls
```
Opção `--all` (ou `-a`) para também listar imagens intermediárias.

Para apagar uma (ou mais) imagem, execute
```
docker image rm <nome_ou_id_imagem>
```
Opção `--force` (ou `-f`) para apagar imagens que estejam sendo usadas.

Para apagar todos as imagens paradas, execute
```
docker image prune
```
Opção `--force` (ou `-f`) para não perguntar se realmente deseja apagá-las.

Para ver as camadas criadas por uma imagem, execute
```
docker image history <nome_ou_id_imagem>
```
Atalho do comando: `docker history`

Para rodar uma varredura de vulnerabilidades de segurança em uma imagem, execute
```
docker scan <nome_ou_id_imagem>
```
É necessário ter uma conta no [Docker Hub](https://hub.docker.com/).



### Volumes

Existem três tipos de volumes:
- `bind`: quando já existe o diretório na máquina hospedeira, e queremos montar ele no Container.
- `volume`.
- `tmpfs`.

Para criar volumes, passe a opção `--mount` nos comandos de Container
```
--mount src=<nome_volume>,dst=<caminho_no_container>
--mount type=bind,src=<caminho_pasta>,dst=<caminho_no_container>
```

Ou execute `docker volume create <nome_volume>`, e passe a opção
```
--mount src=<nome_volume>,dst=<caminho_no_container>
```
nos comandos de Container

Para criar volumes com permissão de apenas leitura, passe a opção `readonly` (ou `ro`)
```
--mount type=bind,src=<caminho_pasta>,dst=<caminho_no_container>,readonly
```

Para listar os volumes, execute
```
docker volume ls
```

Para apagar um (ou mais) volume, execute
```
docker volume rm <nome_volume>
```

Para remover todos os volumes não utilizados, execute
```
docker volume prune
```
Opção `--force` (ou `-f`) para não perguntar se realmente deseja apagá-los.



### Redes

Para listar as redes, execute
```
docker network ls
```

Para apagar uma (ou mais) redes, execute
```
docker network rm <nome_ou_id_rede>
```

Para remover todos as redes não utilizados, execute
```
docker network prune
```
Opção `--force` (ou `-f`) para não perguntar se realmente deseja apagá-las.



### TODO Compose
