## Configuração do ZSH e OhMyZSH.

Instalação do [`zsh`](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH). (Z shell).
```bash
sudo dnf install zsh util-linux-user -y
chsh -s $(which zsh)
```
`logout` para persistir a mudança do shell do usuário corrente.

Instalação do [`OhMyZSH`](https://ohmyz.sh/#install).
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Arquivo de configuração `~/.zshrc`.
```
# Stamp shown in the history command output.
HIST_STAMPS="dd.mm.yyyy"

# Plugins Enabled
plugins=(git
        docker
        docker-compose
        kubectl
        ansible
        vagrant
        terraform
        aws
        zsh-syntax-highlighting
        zsh-autosuggestions
        command-not-found)

# --- Increase History Size
export HISTFILESIZE=1000000
export HISTSIZE=1000000

# --- Immediate Append History
setopt INC_APPEND_HISTORY
export HISTTIMEFORMAT="[%F %T] "

# --- Handling Duplicate Commands
setopt HIST_FIND_NO_DUPS
setopt HIST_IGNORE_ALL_DUPS
```


No terminal e demais editores de texto sempre utilizo o conjunto de fontes [`FiraCode`](https://github.com/tonsky/FiraCode).
```bash
sudo dnf install fira-code-fonts -y
```
**Font:**  Fira Code Light  
**Size**: 14