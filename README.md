# MySetup
mac setup



## GIT
https://git-scm.com/downloads 


#### git branch name to prompt
```cat ~/.bash_profile```

```parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}```


## MyZshell
https://github.com/robbyrussell/oh-my-zsh
<br />
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

~/.zshrc

ZSH_THEME=""
autoload -U promptinit; promptinit
prompt pure

plugins=(
  git,
  zsh-syntax-highlighting,
  z,
  git-open,
  emoji,
  thefuck,
  npm,
  yarn,
  docker,
  macos,
  pure,
  zsh-history-substring-search
)

export PATH="$HOME/.npm-packages/bin:$PATH"<br/>
export PATH="$(yarn global bin):$PATH"<br/>
export PATH="./node_modules/.bin:$PATH"<br/>
export PATH="../node_modules/.bin:$PATH"<br/>
export PATH="/Users/username/MyProj/web/node_modules/.bin:$PATH"

export NODE_OPTIONS=--max_old_space_size=8192



## Iterm
https://www.iterm2.com/version3.html
<a href="https://iterm2.com/downloads/stable/latest">Download it here.</a>



## VSCODE
https://code.visualstudio.com/

Theme - NightOwl 

https://marketplace.visualstudio.com/items?itemName=sdras.night-owl



## PHPSTORM
https://www.jetbrains.com/phpstorm/download/#section=mac

Theme - NightOwl

https://plugins.jetbrains.com/plugin/10936-night-owl-theme/update/73432



## FONT
https://github.com/tonsky/FiraCode
Fira code



## UTILITY

Spectacle (windows resizing/arrangements)
https://www.spectacleapp.com/


Lightshot (screenshots markups)
https://app.prntscr.com/en/index.html

