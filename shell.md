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
	zsh-autosuggestions
	zsh-syntax-highlighting
	docker
	docker-compose
	kubectl
	zsh-kubectl-prompt
	terraform
	ansible
        aws
	command-not-found
	vagrant)

# --- Increase History Size
export HISTFILESIZE=1000000
export HISTSIZE=1000000

# --- Immediate Append History
setopt INC_APPEND_HISTORY
export HISTTIMEFORMAT="[%F %T] "

# --- Handling Duplicate Commands
setopt HIST_FIND_NO_DUPS
setopt HIST_IGNORE_ALL_DUPS

# --- Turn off power status when using spaceship prompt
export SPACESHIP_BATTERY_SHOW=false

# --- PBCopy and PBPaste - xclip
alias pbcopy='xclip -selection clipboard'
alias pbpaste='xclip -selection clipboard -o'

# --- TFEnv - Terraform Version Manager
export PATH="$PATH:/home/ewerton/.tfenv/bin"

# --- zsh-kubectl-prompt
RPROMPT='%{$fg[blue]%}($ZSH_KUBECTL_PROMPT)%{$reset_color%}'
zstyle ':zsh-kubectl-prompt:' namespace false

# --- Krew - Plugin manager for kubectl command-line tool
export PATH="${KREW_ROOT:-$HOME/.krew}/bin:$PATH"

# --- A Command-line Fuzzy Finder
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
```


No terminal e demais editores de texto sempre utilizo o conjunto de fontes [`FiraCode`](https://github.com/tonsky/FiraCode).
```bash
sudo dnf install fira-code-fonts -y
```
**Font:**  Fira Code Light  
**Size**: 14