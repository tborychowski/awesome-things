# CLI apps

- [bat](#bat)
- [ctop](#ctop)
- [imgcat](#imgcat)
- [exa](#exa)
- [fisher](#fisher)
- [fzf](#fzf)
- [fzy](#fzy)
- [httpie](#httpie)
- [icdiff](#icdiff)
- [jp](#jp)
- [massren](#massren)
- [tldr](#tldr)
- [trash](#trash)
- [z.lua](#zlua)






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



## [ctop](https://github.com/bcicen/ctop)
htop for docker
install
```sh
sudo wget https://github.com/bcicen/ctop/releases/download/v0.7.3/ctop-0.7.3-linux-amd64 -O ~/bin/ctop
sudo chmod +x ~/bin/ctop
```
use
```sh
ctop
```



## [imgcat](https://github.com/eddieantonio/imgcat)
cat for images
install
```sh
brew tap eddieantonio/eddieantonio
brew install imgcat
```
use
```sh
imgcat image.png
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


## [trash](http://hasseg.org/trash/)
Delete files/folders to trash.
install
```sh
brew install trash
```
in `.bashrc`
```sh
alias del="trash"
```
use
```sh
del file.txt
```

## [z.lua](https://github.com/skywind3000/z.lua)
  Must be downloaded manually from GH repo.
