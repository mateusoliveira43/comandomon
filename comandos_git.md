# Comandos Git

Voltar à página inicial do [COMANDOMON](README.md).



## Sumário

- [Tarefas](#Tarefas)
- [Introdução](#Introdução)
- [Instalação](#Instalação)
- [Comandos](#Comandos)



## Tarefas

- [ ] Estudar comandos de tags e de reverter ações
- [ ] Melhorar introdução acrescentando *commits*, *merges*, etc



## Introdução

`Git` é um sistema de controle de versão, isto é, podemos recuperar versões anteriores de um projeto que o utiliza a qualquer momento. Além disso, é uma ferramenta que pode ser usada para gerenciar projetos com mais de um colaborador, salvando informações de quem e quando cada alteração foi feita.



## Instalação

Para instalar o `Git` no Linux, no Terminal execute
```bash
sudo apt-get install git
```

Para instalar o `Git` no Windows: [Git Bash](https://Git-scm.com/download/win).

Para verificar a versão instalada, no Terminal do Linux/Windows PowerShell execute
```bash
git --version
```



## Comandos

Execute os comandos dessa seção no Terminal do Linux/Windows PowerShell.

Esse material é apenas um resumo, para ver a documentação completa do `Git`, execute
```
git --help
```

Para configurar seu nome de usuário e email em toda sua máquina (globalmente), execute 
```
git config --global user.name "<nome de usuário>"
git config --global user.email "<email>"
```
alterando `<nome de usuário>` e `<email>` pelos desejados. Essas configurações serão utilizadas para indicar quem fez as alterações na história do repositório.

Para listar as configurações de usuário do `Git` da máquina, execute
```
git config --global -l
```

Para editar as configurações de usuário do `Git` da máquina, execute
```
git config --global -e
```

Para iniciar um repositório, execute
```
git init
```

Para baixar um repositório remoto, execute
```
git clone <endereco>
```
alterando `<endereco>` pelo endereço do repositório remoto (por padrão a URL do repositório + .git).

Para adicionar um repositório remoto nomeado `<nome>`, execute
```
git remote add <nome> <endereço>
```
alterando `<endereco>` pelo endereço do repositório remoto.

Para mostrar o estado (em relação à arquivos não rastreados/modificados/deletados e a fila de espera de arquivos a serem *commitados*), execute
```
git status
```

Para mostrar um gráfico dos *commits*, execute
```
git log --all --decorate --oneline --graph
```

Para mostrar o nome do repositório remoto, execute
```
git remote show
```

Para listar as `branches` do repositório (e mostrar em qual está no momento), execute
```
git branch
```

Para trocar para a `branch` nomeada `<ramo>` (use a tecla `Tab` para listar as opções), execute
```
git checkout <ramo>
```

Para criar uma `branch` nomeada `<ramo>` e se mover para ela, execute
```
git checkout -b <ramo>
```

Para adicionar todos os arquivos alterados, no nível do diretório, à fila de espera a serem *commitados*, execute
```
git add .
```

Para adicionar todos os arquivos alterados à fila de espera a serem *commitados*, execute
```
git add -A
```
Opção `-A` de `all`.

Para *commitar* todos os arquivos na fila de espera a serem *commitados*, execute
```
git commit -m "<mensagem>"
```
alterando `<mensagem>` e pela mensagem desejada. Opção `-m` de `message`.

Para enviar os *commits* à `branch` nomeada `<ramo>` do repositório remoto nomeado `<repositorio>` (por padrão `origin`), execute
```
git push <repositorio> <ramo>
```
Se usada a opção `-u` (de `upstream`), não é necessário passar o repositório e ramo nas próximas vezes que usar os comandos `push` ou `pull`.

Para incluir uma tag no versionamento, execute
```
git tag -a <nome-da-tag> -m "<mensagem>"
```

Para enviar a tag para o repositório remoto nomeado `<repositorio>`, execute
```
git push <repositorio> <nome-da-tag>
```

Para *mergear* as alterações da `branch` nomeada `<ramo>` na `branch` em que se encontra, execute
```
git merge <ramo>
```

Para deletar a `branch` nomeada `<ramo>` (não pode se encontrar nela), execute
```
git branch -D <ramo>
```
Opção `-D` de `delete` e `force`.

Para atualizar a `branch` local nomeada `<ramo>` com as alterações de sua contraparte no repositorio remoto nomeado `<repositorio>`, execute
```
git pull <repositorio> <ramo>
```

Para atualizar a `branch` em que se encontra com as alterações da `branch` nomeada `<ramo>`, execute
```
git rebase -i <ramo>
```
Isso irá abrir a linha de comando do editor de texto de sua máquina (`nano` ou `vim`, provavelmente).

Para transformar **n** *commits* em um único que contenha todas as alterações desses commits (não funciona se for o *commit* inicial do repositório), execute
```
git rebase -i <commit>~1
```
alterando `<commit>` pelo identificador do primeiro *commit* (código alfa-numérico que cada *commit* possui).

Isso irá abrir a linha de comando do editor de texto de sua máquina. Deixe o primeiro *commit* como `pick` e mude os outros para `s` (ou `squash`). Em seguida, digite a mensagem desse novo *commit*.

Para automatizar esse processo, execute
```
git commit --fixup <commit>
```
a cada commit (exceto o primeiro).

Isso os deixará marcados como **fixup** na hora do rebase (que funciona como squash).

Na hora do rebase, execute
```
git rebase --autosquash -i <commit>~1
```

Como foram apagados os *commit* anteriores, para enviar as alterações para o repositório remoto, será necessário usar a opção `-f` (de `force`) no comando de `push`. Exemplo
```
git push -f origin feature/new-site-section
```
Antes de realizar o *rebase*: 5 *commits* contendo as informações das alterações realizadas.
![Antes de realizar o rebase](images/rebase1.svg)

Depois de realizar o *rebase* dos *commits* A, B, C, D e E: 1 único *commit* contendo as mesmas informações.
![Depois de realizar o rebase do 5 commits](images/rebase2.svg)
