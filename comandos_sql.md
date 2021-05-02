# Comandos SQL

Voltar à página inicial do [COMANDOMON](README.md).



## Sumário

- [Tarefas](#Tarefas)
- [Introdução](#Introdução)
- [Comandos](#Comandos)



## Tarefas

- [ ] Seguir padrão das outras lista de comandos
- [ ] Terminar aulas de SQL
- [ ] Ver necessidade de mover comandos do PostgreSQL para esse arquivo



## Introdução

`SQL` : Structured Query Language em desenvolvimento... https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/
DER: **D**iagrama **E**ntidade **R**elacionamento (Desenho)
    Entidades: tabelas
    Relacionamentos: chaves estrangeiras
MER: **M**odelo **E**ntidade **R**elacionamento

chave primária (PK): único, não pode ser nulo
    UUID, auto increment, surrogate key?(valor sintético para identificação), composta

chave estrangeira (FK):

relacionamentos (desenho)
    -|-|---------|-|- : um (obrigatório) para um (obrigatório, exatamente um)
    -|-|---------O-|- : um (obrigatório) para um (opcional, zero ou um)
    -|-|---------|-<- : um (obrigatório) para muitos (obrigatório, ao menos um)
    -|-|---------O-<- : um (obrigatório) para muitos (opcional, zero ou N)
    ->-|---------|-<- : muitos (obrigatório) para muitos (obrigatório) (tabela de junção, dois relacionamentos um para muitos)

    Não precisa de desenho, posso desenhar
    -(1,1)---------(1,1)- : um para um
    -(1,1)---------(0,1)- : um para um (opcional)
    -(1,1)---------(1,n)- : um para muitos
    -(1,1)---------(0,n)- : um para muitos (opcional)
    -(1,n)---------(1,n)- : muitos para muitos

    também
    -1---------1- : um para um
    -1---------0- : um para um (opcional)
    -1---------*- : um para muitos


## Código

Referenciar readme da pasta sql aqui...

Na pasta `sql`, execute
```
docker-compose up -d
```

Para parar o contêiner, execute
```
docker stop estudos_sql
```


## Comandos

Para , execute
```

```
