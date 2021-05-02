# Comandos PostgreSQL

Voltar à página inicial do [COMANDOMON](README.md).


## Sumário

- [Tarefas](#Tarefas)
- [Instalação](#Instalação)
- [Comandos](#Comandos)



## Tarefas

- [ ] Seguir padrão das outras lista de comandos



## Instalação

Comandos para o Sistema Operacional Linux. Execute-os no Terminal.

Para instalar o `PostgreSQL`, execute
```bash
sudo apt-get install postgresql postgresql-contrib
```

Para desinstalar o `PostgreSQL`, execute
```bash
sudo apt-get --purge remove postgresql*
```

Para verificar a versão instalada, execute
```bash
psql -V
```

## Comandos

Esse material é apenas um resumo, procure a documentação completa do `PostgreSQL` para maiores informações.

Para entrar na linha de comando do `PostgreSQL` no Linux, no Terminal execute
```bash
sudo -u <usuario> psql
```
alterando `<usuario>` pelo nome de usuário do `PostgreSQL` (por padrão `postgres`).

Para entar na linha de comando do `PostgreSQL` no Windows, no PowerShell execute
```bash
psql -U <usuario>
```
alterando `<usuario>` pelo nome de usuário do `PostgreSQL`.

Para usar o comando anterior no Linux, é necessário dar uma senha ao usuário, executando na linha de comando do `PostgreSQL`
```
ALTER USER <usuario> WITH PASSWORD '<senha>';
```

Depois, alterar o método de autenticação de `peer` para `md5` no arquivo `pg_hba.conf` (provavelmente na pasta `etc/postgresql/`). É necessário privilégios de administrador para alterar o arquivo.

Por fim, é necessário reiniciar o serviço do `PostgreSQL`, executando no Terminal
```bash
sudo service postgresql restart
```

Execute os comandos a seguir na linha de comando do `PostgreSQL`.

Para listar os comandos do `PostgreSQL`, execute
```
\?
```

Para listar os comandos de SQL, execute
```
\h
```

Para listar os bancos de dados, execute
```
\l
```

Para se conectar a um banco de dados nomeado `<database>`, execute
```
\c <database>
```

Para listar as tabelas de um banco de dados, execute
```
\dt
```

Para deletar um banco de dados nomeado `<database>`, execute
```
DROP DATABASE <database>;
```

Para ver as especificações dos campos de uma tabela nomeada `<tabela>`, execute
```
\d "<tabela>"
```

Para listar os elementos/objetos de uma tabela nomeada `<tabela>`, execute
```
TABLE "<tabela>";
```

Para sair da linha de comando do `PostgreSQL`, execute
```
\q
ctrl+D
```
