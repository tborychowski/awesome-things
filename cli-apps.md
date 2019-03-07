# Awesome Things - CLI apps

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



## [autojump](https://github.com/wting/autojump)
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


## [bat](https://github.com/sharkdp/bat)
A better cat
install
```sh
brew install bat
```
use
```sh
bat file.js
```


## [exa](https://github.com/ogham/exa)
A better "ls"
install
```sh
brew install exa
```
use
```sh
alias ll='exa --all --header --long --group-directories-first --git --time-style long-iso'
```


## [fasd](https://github.com/clvv/fasd)
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



## [fisher](https://github.com/jorgebucaran/fisher)
A package manager for fish shell plugins
install
```sh
curl https://git.io/fisher --create-dirs -sLo ~/.config/fish/functions/fisher.fish
```



## [fzf](https://github.com/junegunn/fzf#installation)
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



## [fzy](https://github.com/jhawthorn/fzy)
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



## [httpie](https://github.com/jakubroztocil/httpie)
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



## [icdiff](https://www.jefftk.com/icdiff)
A better diff
install
```sh
brew install icdiff
```
use
```sh
icdiff file1 file2
```



## [jp](https://github.com/jmespath/jp)
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



## [massren](https://github.com/laurent22/massren)
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



## [tldr](https://tldr.sh/#installation)
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



## z
- [bash implementation](https://github.com/rupa/z)
- [fish implementation](https://github.com/jethrokuan/z)
  install
  ```sh
  fisher add jethrokuan/z
  ```
