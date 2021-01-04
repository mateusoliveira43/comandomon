# Comandos Linha de Comando

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
```bash
zsh --version
```
Se não, intale-o executando
```bash
sudo apt-get install zsh
```

Para conferir qual o seu intrepertador de linha de comando padrão, execute
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
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

Para instalar a fonte utilizada pelos temas do oh my zsh, execute
```bash
sudo apt-get install fonts-powerline
```
Adicione ela as fontes do terminal do VSCode: `'PowerlineSymbols'`.

Para configurar o oh my zsh, execute
```bash
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
```bash
nano .oh-my-zsh/custom/themes/powerlevel9k/powerlevel9k.zsh-theme
```

Adicione a seguinte linha ao final da função `left_prompt_end()`
```
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
Comando `help` funciona apenas no bash, não no zsh. Para acessar o bash no zsh, execute `bash`. Para sair do bash e voltar ao zsh, execute `Ctrl+D`.

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
cd ~
cd ..
```
Use a tecla `Tab` para mostrar e cmpletar as opções. Há destinção de maiúsculas e minúsculas.

Para criar um arquivo, execute
```bah
touch <arquivo>
```

Para criar uma pasta (**M**a**k**e **Dir**ectory), execute
```bash
mkdir <pasta>
```

Para apagar um arquivo (**R**e**m**ove), execute
```bash
rm <arquivo>
```

Para apagar uma pasta, execute
```bash
rm -r <pasta>
```

Para mostrar caminho absoluto do diretório atual (**P**rint **W**orking **D**irectory), execute
```bash
pwd
```

Para fechar o Terminal, execute
```bash
exit
Ctrl+D
```