# MySetup
mac setup



## GIT
https://git-scm.com/downloads 


#### git branch name to prompt
cat ~/.bash_profile

parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}



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





/**
 * Convert an array of items to a map for fast lookups.
 * Takes an array and a function which extracts a key to reference each T.
 */
export function toMap<T, K extends string | number>(
  arr: T[],
  fun: (x: T) => K
): Record<K, T> {
  return arr.reduce((a, c) => ({ ...a, [fun(c)]: c }), {} as Record<K, T>);
}






/**
 * Tool to encode or decode rgb values into java ints
 * e.g. node color.js e ff0000 00ff6e
 * or node color.js d 317856
 */
const action = process.argv[2];
if (action === "e") {
  const hex = process.argv.slice(3);
  const ints = hex.map((h) => {
    const ints = h.match(/.{1,2}/g).map((x) => parseInt(x, 16));
    return getIntFromColor(...ints);
  });
  console.log(ints);
} else if (action === "d") {
  const ints = process.argv.slice(3);
  const hexs = ints.map((int) => {
    const i = +int;
    const a = (i >> 24) & 0xff;
    const r = (i >> 16) & 0xff;
    const g = (i >> 8) & 0xff;
    const b = i & 0xff;
    return `${r},${g},${b},${a}`;
  });
  console.log(hexs);
} else {
  console.log("Invalid action");
}
function getIntFromColor(r, g, b) {
  const red = (r << 16) & 0x00ff0000; //Shift red 16-bits and mask out other stuff
  const green = (g << 8) & 0x0000ff00; //Shift Green 8-bits and mask out other stuff
  const blue = b & 0x000000ff; //Mask out anything not blue.
  return 0xff000000 | red | green | blue; //0xFF000000 for 100% Alpha. Bitwise OR everything together.
}
