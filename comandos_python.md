# Comandos Python

Voltar à página inicial do [COMANDOMON](README.md).



## Sumário

- [Tarefas](#Tarefas)
- [Instalação](#Instalação)
- [Comandos](#Comandos)



## Tarefas

- [ ] Seguir padrão das outras lista de comandos
- [ ] Pensar/lembrar de mais comandos importantes (olhar repositório estudos Python)



## Instalação

Para instalar o gerenciador de pacotes `pip`, execute
```
sudo apt install python3-pip
pip install -U pip
```

Para instalar o gerenciador de ambiente virtuais `virtualenv`, execute
```
pip install -U virtualenv
```



## Comandos

Para mostrar os pacotes/bibliotecas instaladas no seu projeto, execute
```
pip list
```

Para mostrar informações do pacote/biblioteca nomeado `<nome>`, instalado no seu projeto, execute
```
pip show <nome>
```

Para gerar um arquivo `requirements.txt` de dependências do projeto, execute
```
pip freeze > requirements.txt
```
Note que é melhor anotar os pacotes realmente instalados, em vez de listar pacotes que já seriam instalados por serem dependência de outros.

Para listar os atributos de um objeto, use a função
```python
dir(objeto)
```

Para inspecionar bytecode gerado pelo Python, use as funções
```python
import dis

dis.show_code(função)
dis.dis(função)
```

### Poetry

[Documentação completa](https://python-poetry.org/docs/)

Para criar um novo projeto (nova pasta), execute
```
poetry new <nome>
```

Para iniciar o Poetry em um projeto já existente, na raiz do projeto execute
```
poetry init
```

Para instalar as dependências do projeto, execute
```
poetry install
```
Use a opção `--no-dev` para não instalar as dependências de desenvolvimento.

Use a opção `--no-root` para não instalar o projeto em si.

Para adicionar uma dependência ao projeto, execute
```
poetry add <nome>
```
Use a opção `-D` para adicionar uma dependência de desenvolvimento.

Para ativar o ambiente virtual, execute
```
poetry shell
```
Para desativá-lo, execute `CTRL+D`.

Para visualizar a árvore de dependências do projeto, execute
```
poetry show --tree
```

Para executar um comando sem o ambiente virtual ativo, execute
```
poetry run <comando>
```

Para conferir se o arquivo `pyproject.toml` está no formato correto, execute
```
poetry check
```

Para gerar um arquivo `requirements.txt`, execute
```
poetry export -o <nome>.txt
```
Use a opção `--dev` para também salvar as dependências de desenvolvimento no arquivo.
