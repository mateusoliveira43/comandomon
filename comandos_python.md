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