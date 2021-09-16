## Abra o Terminal

sudo apt install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev

sudo apt update && sudo apt upgrade

git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.8.1

### SABER O TIPO DE SHELL
echo $SHELL

## SE FOR <bash>
code ~/.bashrc

### adicione isso no aquivo
. $HOME/.asdf/asdf.sh

. $HOME/.asdf/completions/asdf.bash

### volte ao terminal
source ~/.bashrc

## SE FOR <Zsh>

code ~/.zshrc

### adicione isso no aquivo
. $HOME/.asdf/asdf.sh

plugins=(
  git
  sudo
  ubuntu
  yarn
  asdf
  python
  tmux
  autopep8
  )

## VOLTE AO TERMINAL
source ~/.zshrc

# ADSF

asdf plugin-add python

asdf install python 3.9.6

asdf global python 3.9.6

# SEMPRE QUE INSTALAR UMA LIB NOVA NO ASDF
asdf reshim

