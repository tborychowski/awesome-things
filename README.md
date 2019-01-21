# Awesome Things

A list of awesome tools, repos, apps and other shit.

- [Editor](#editor)
- [Editor Plugins](#editor-plugins)
- [Font](#font)
- [Colours](#colours)
- [Terminal](#terminal)
	- [Terminal emulators](#terminal-emulators)
	- [Shell](#shell)
- [CLI apps](#cli-apps)
	- [autojump](#autojump)
	- [bat](#bat)
	- [exa](#exa)
	- [fasd](#fasd)
	- [fisher](#fisher)
	- [fzf](#fzf)
	- [fzy](#fzy)
	- [httpie](#httpie)
	- [icdiff](#icdiff)
	- [jp](#jp)
	- [massren](#massren)
	- [tldr](#tldr)
	- [z](#z)
- [CLI apps development](#cli-apps-development)
- [Web Development](#web-development)
	- [svelte](#svelte)
	- [sequelize](#sequelize)
	- [express](#express)
	- [jest](#jest)
- [Self-hosted](#self-hosted)
	- [miniflux](#miniflux)
	- [kanboard](#kanboard)
	- [gogs](#gogs)



## Editor

- [VSCode](https://code.visualstudio.com/) - Code editing. Redefined.
  - [awesome-vscode](https://github.com/viatsko/awesome-vscode#readme)
  - [VS Code can do that?!](https://vscodecandothat.com/)
- [Micro](https://github.com/zyedidia/micro) - A modern and intuitive terminal-based text editor


## Editor Plugins
- [bracket-pair-colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
- [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- [eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [html-css](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) - Handles css in html styling.
- [language-stylus](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) - Stylus css preprocessor support.
- [markdown-all-in-one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) - Useful markdown toolkit.
- [nord](https://marketplace.visualstudio.com/items?itemName=arcticicestudio.nord-visual-studio-code) - Nord theme for VSCode.
- [npm-script](https://marketplace.visualstudio.com/items?itemName=eg2.vscode-npm-script) - Runs npm scripts defined in `package.json` and validates installed modules against dependencies defined in `package.json`.
- [open-in-finder](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-open-in-finder)
- [open-in-terminal](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-open-in-terminal)
- [path-autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)
- [prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - Code formatter
- [projects-plus](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-projects-plus) - Best project manager
- [settings-sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync) - Sync settings to gist.
- [versionlens](https://marketplace.visualstudio.com/items?itemName=pflannery.vscode-versionlens) - See packages versions stats in `package.json`
- [great-icons](https://marketplace.visualstudio.com/items?itemName=emmanuelbeziat.vscode-great-icons) - Best icons
- [whiteviz](https://marketplace.visualstudio.com/items?itemName=spywhere.whiteviz) - Show whitespace in selection only (sublimetext-like)


## Font
- [FiraCode nerd font](https://github.com/ryanoasis/nerd-fonts/releases/tag/v2.0.0) - Nerd font patcher fira code.


## Colours
- [Nord](https://github.com/arcticicestudio/nord)
- [nord-visual-studio-code](https://github.com/arcticicestudio/nord-visual-studio-code)
- [nord-iterm2](https://github.com/arcticicestudio/nord-iterm2)
- [nord-hyper](https://github.com/arcticicestudio/nord-hyper)
- [nord-slack](https://github.com/arcticicestudio/nord-slack)
- [vivaldi-nord](https://github.com/arcticicestudio/nord/issues/100)
  or:
  - background: #2f343f
  - foreground: #eceff4
  - highlight: #4d5668
  - accent: #4d5668



## Terminal
### Terminal emulators
- [iTerm](https://iterm2.com/) - Bestest
  - [Tweaking iTerm](https://www.felixjung.io/posts/pretty-iterm2-with-a-modern-titlebar/)
- [Hyper](https://hyper.is/) - Electron based pluggable terminal emulator
- [upterm](https://github.com/railsware/upterm)


### Shell
- [fish](https://fishshell.com/) - Smart and user-friendly command line shell for Linux, macOS, and the rest of the family.




## CLI apps

### [autojump](https://github.com/wting/autojump)
A better "cd". [cd-is-wasting-your-time](https://olivierlacan.com/posts/cd-is-wasting-your-time/)
install
```sh
brew install autojump
```
in `.bashrc`
```sh
[ -f /usr/local/etc/profile.d/autojump.sh ] && . /usr/local/etc/profile.d/autojump.sh
```
use
```sh
# cd to folders and then:
j p
```


### [bat](https://github.com/sharkdp/bat)
A better cat
install
```sh
brew install bat
```
use
```sh
bat file.js
```


### [exa](https://github.com/ogham/exa)
A better "ls"
install
```sh
brew install exa
```
use
```sh
alias ll='exa --all --header --long --group-directories-first --git --time-style long-iso'
```


### [fasd](https://github.com/clvv/fasd)
Even better cd
install
```sh
brew install fasd
```
in `.bashrc`
```sh
eval "$(fasd --init auto)"   # this goes to .bashrc

function c() {
	if [ $# -eq 0 ]; then
		code .;
	else
		fasd -ae code "$@";
	fi;
}
```
use
```sh
z no   #  cd ~/Projects/_playground/noter
c t    # code ~/Projects/_playground/tim
```



### [fisher](https://github.com/jorgebucaran/fisher)
A package manager for fish shell plugins
install
```sh
curl https://git.io/fisher --create-dirs -sLo ~/.config/fish/functions/fisher.fish
```



### [fzf](https://github.com/junegunn/fzf#installation)
A fuzzy finder (for history)
install
```sh
brew install fzf
brew install fd
$(brew --prefix)/opt/fzf/install
```
config
```sh
# .bash_aliases
alias preview="fzf --preview 'bat {}' --layout reverse --preview-window=right:50%"
# .bashrc
source ~/.fzf.bash
complete -F _fzf_path_completion -o default -o bashdefault bat
complete -F _fzf_path_completion -o default -o bashdefault fd
# .bash_exports
export FZF_DEFAULT_COMMAND='fd --type f'
export FZF_CTRL_T_COMMAND="$FZF_DEFAULT_COMMAND"
export FZF_DEFAULT_OPTS="--bind='ctrl-o:execute(code {})+abort'"
```
use
```sh
ctrl+r    - fuzzy search history
ctrl+t    - fuzzy search file
preview   - file previewer
```



### [fzy](https://github.com/jhawthorn/fzy)
A better fuzzy finder
install
```sh
brew install fzy
```
in `.bashrc`
```sh
function g() {
	cd $(find . -maxdepth 3 -type d | fzy)
}
proj() {
	cd $(find ~/Projects ~/Projects/_playground -maxdepth 1 -type d | fzy)
}
```
use
```sh
g [enter]      # get a list of all subfolders
proj [enter]   # get a list of all projects
```



### [httpie](https://github.com/jakubroztocil/httpie)
A user-friendly curl alternative with intuitive UI, JSON support, syntax highlighting
install
```sh
brew install httpie
```
use
```sh
http httpie.org
http --download example.org/file
# https://httpie.org/doc#usage
```



### [icdiff](https://www.jefftk.com/icdiff)
A better diff
install
```sh
brew install icdiff
```
use
```sh
icdiff file1 file2
```



### [jp](https://github.com/jmespath/jp)
A json parser
install
```sh
brew tap jmespath/jmespath
brew install jp
```
use
```sh
cat package.json | jp scripts.start
```



### [massren](https://github.com/laurent22/massren)
A batch rename files as text in any editor
install
```sh
brew install massren
```
in `.bashrc`
```sh
massren --config editor code
alias ren="massren"
```
use
```sh
ren [enter]
```



### [tldr](https://tldr.sh/#installation)
A better "man"
install
```sh
brew install tldr
```
in `.bashrc`
```sh
alias help='tldr'
```
use
```sh
help ls
```



### z
- [bash implementation](https://github.com/rupa/z)
- [fish implementation](https://github.com/jethrokuan/z)
  install
  ```sh
  fisher add jethrokuan/z
  ```


## CLI apps development
- [Inquirer](https://github.com/SBoudrias/Inquirer.js) - A collection of common interactive command line user interfaces.
- [Signale](https://github.com/klaussinani/signale) - A hackable console logger
- [Ora](https://github.com/sindresorhus/ora) - Terminal spinner
- [progress-estimator](https://github.com/bvaughn/progress-estimator) - Logs a progress bar and estimation for how long a Promise will take to omplete
- [chalk](https://github.com/chalk/chalk) - Terminal string styling done right.


##  Web Development

### svelte
The magical disappearing UI framework.
- [github](https://github.com/sveltejs/svelte)
- [guide](https://svelte.technology/guide)

### sequelize
A promise-based ORM for Node. Supports PostgreSQL, MySQL, SQLite and MSSQL.
- [docs](http://docs.sequelizejs.com/)
- [github](https://github.com/sequelize/sequelize)

### express
Fast, unopinionated, minimalist web framework for Node.js.
- [homepage](https://expressjs.com/)

### jest
Delightful JavaScript Testing.
- [docs](https://jestjs.io/docs/en/getting-started)
- [github](https://github.com/facebook/jest)


## Self-hosted

### miniflux
A minimalist and opinionated feed reader.
- [homepage](https://miniflux.app/)
- [github](https://github.com/miniflux/miniflux)

### kanboard
Free and open source Kanban project management software.
- [homepage](https://kanboard.org/)
- [github](https://github.com/kanboard/kanboard)

### gogs
Gogs is a painless self-hosted Git service.
- [homepage](https://gogs.io/)
- [github](https://github.com/gogs/gogs)


