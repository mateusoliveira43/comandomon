# Comandos Shell

Voltar à página inicial do [COMANDOMON](README.md).



## Sumário

- [Tarefas](#Tarefas)
- [Instalação](#Instalação)
- [Comandos](#Comandos)



## Tarefas

- [ ] Seguir padrão das outras lista de comandos
- [ ] Listar vídeos úteis



## Instalação

Passo para instalação e configuração do [oh my zsh](https://github.com/ohmyzsh/ohmyzsh) no Linux.

Para conferir se o zsh está instalado, execute
```
zsh --version
```
Se não, instale-o executando
```
sudo apt-get install zsh
```

Para conferir qual o seu interpretador de linha de comando padrão, execute
```bash
echo $SHELL
```
Se não for o zsh, torne-o padrão executando
```bash
chsh -s $(which zsh)
```
Pode ser necessário reiniciar o computador para as alterações serem aplicadas.

Para instalar o oh my zsh, execute
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Para instalar os plugins e temas, execute
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

Para instalar a fonte utilizada pelos temas do oh my zsh, execute
```
sudo apt-get install fonts-powerline
```
Adicione ela as fontes do terminal do VSCode: `'PowerlineSymbols'`.

Para configurar o oh my zsh, execute
```
nano ~/.zshrc
```

Adicione/modifique as seguintes variáveis no arquivo
```
ZSH_THEME="powerlevel9k/powerlevel9k"
POWERLEVEL9K_SHORTEN_DIR_LENGTH=2
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(dir virtualenv vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status root_indicator background_jobs)

plugins=(
git
zsh-syntax-highlighting
zsh-autosuggestions
)
```

Para aplicar as alterações, execute
```bash
source ~/.zshrc
```

Para configurar o tema, execute
```
nano .oh-my-zsh/custom/themes/powerlevel9k/powerlevel9k.zsh-theme
```

Adicione a seguinte linha ao final da função `left_prompt_end()`
```bash
echo "\n ➜ ";
```

Para aplicar as alterações, execute
```bash
source .oh-my-zsh/custom/themes/powerlevel9k/powerlevel9k.zsh-theme
```

## Comandos

Este material é apenas um resumo, para ver a lista completa de comandos, execute
```bash
help
info
man man
```
Comando `help` funciona apenas no bash, não no zsh. Para acessar o bash no zsh, execute `bash`. Para acessar o zsh no bash, execute `zsh`.

Para abrir o Terminal, execute
```
Ctrl+Alt+T
```

Para limpar as saídas do Terminal, execute
```bash
clear
Ctrl+L
```

Para listar pastas e arquivos no nível do diretório que se encontra, execute
```bash
ls
```

Para trocar de diretório (**C**hange **D**irectory), execute
```bash
cd <caminho>
cd
cd ..
```
Use a tecla `Tab` para mostrar e completar as opções. Há distinção de maiúsculas e minúsculas.

Para criar um arquivo, execute
```bah
touch <arquivo>
```

Para criar uma pasta (**M**a**k**e **Dir**ectory), execute
```bash
mkdir <pasta>
```

Para copiar um arquivo (**C**o**p**y), execute
```bash
cp <arquivo> <destino>
```

Para copiar uma pasta, execute
```bash
cp -r <pasta> <destino>
```
Opção `-r` de `--recursive`.

Para apagar um arquivo (**R**e**m**ove), execute
```bash
rm <arquivo>
```

Para apagar uma pasta, execute
```bash
rm -r <pasta>
```
Opção `-r` de `--recursive`.

Para mostrar caminho absoluto do diretório atual (**P**rint **W**orking **D**irectory), execute
```bash
pwd
```

Para fechar o Terminal, execute
```bash
exit
Ctrl+D
```

Para listar os comandos executados, execute
```bash
history
```

Para listar as conexões de rede ativas, execute
```bash
sudo netstat -atunp
```
Opções `-a` de `all`; `-t` de `tcp`; `-u` de `udp`; `-n` de `numeric`; `-p` de `programs`.

Para listar processos que correspondem a um padrão, execute
```bash
pgrep -a <padrão>
```
Opção `-a` de `--list-full`. Para listar processos que correspondem ao comando completo, use a opção `-f` (de `--full`).

Para parar um processo pelo seu PID, execute
```bash
kill <PID>
```

Para parar processos pelo seu padrão, execute
```bash
pkill <padrão>
```
Para parar processos que correspondem ao comando completo, use a opção `-f` (de `--full`).

Ambos comandos anteriores aceitam a opção `-9` (de `SIGKILL`).

Para buscar ocorrências de um padrão em uma pasta, execute
```bash
grep -Inr <padrão> <pasta>
```
Opções `-I` atalho para `--binary-files=without-match`; `-n` de `--line-number`; `-r` de `recursive`. Para excluir certas extensões de arquivos da busca, use a opção `--exclude=\*.nome` ou ``--exclude=\*.{nome1, nome2, ..., nomeN}`.

Para baixar um arquivo da internet, execute
```bash
wget <url>
```

Para criar um link simbólico (**L**i**n**k), execute
```bash
ln -s <executável> <atalho>
```
Opção `-s` de `--symbolic`. Atalho costuma ser `usr/local/bin/comando` ou `usr/bin/comando`.
