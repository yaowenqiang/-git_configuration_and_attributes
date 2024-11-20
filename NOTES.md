# git Configuration Hierarchy

+ System
+ Per user
+ Local

## Syste-wide Configuration

+ Affectes all users on a computer
+ Offen located in [git install]/etc/gitconfig
+ Accessed using --system flag
+ Not ofen used


> git branch

> git config --system core.pager /usr/local/bin/less


## Used-specific Configuration

+ Good place for most Configuration
+ Often located in [home directory]/.gitconfig
+ Access using --global flag

> git config --global user.name 'jacky.yao'

## Repository Configuration

+ Affects a signle copy of a Repository
+ Located in [repository]/.git/config
+ Not pushed or pulled
+ Access using --local (or no) flag

> exif image.jpeg


~/.gitconfig

[diff 'jpeg']
    textconv = exif

.gitattributes
*.jpeg -text -diff

.git/info/attributes

*.jpeg diff=jpeg

### End of line Attributes


.gitignore 

*.js text
*.ps1 eol=crlf
*.sh eol=lf


### git Filter Attribute


.git/info/attributes

*.ex filter=myfilter

~/.gitconfig

[filter 'myfilter']
    clean =
    smudge = 

~/.gitconfig

[filter 'mix-format']
    clean = mix format -
    smudge = cat


A Better Way to Auto-format

Git Hooks


Process Filters
1. first
2. second
3. third



> git config --local user.email 'jacky.email'

Additional Configuration Capabilities

+ Environment Variables
  + GIT_AUTHOR_EMAIL ( Not recommended)
+ Additional levels
  + includeIf

> git config --global user.name 'user name'

> check config 

> git config --global user.name 


> cat ~/.gitconfig

> git config --system core.editor 

> git config --local user.email useremail 

> push.autoSetupRemote

> init.defaultBranch

> git config --list

> git config --list | sort

> git config --list --show-origin

> git config --list --show-origin --show-scope


> git config --local --unset user.name

> git config --local --remove-section user


## Managing Files with Attributes


### Git Attributes Hierarchy

+ system [install]/etc/gitattributes
+ global core.atrributeFile
+ local .git/info/attributes
+ .gitattributes

### Setting Git Attributes

Avoid changing end-of-line characters

.gitattributes or images/.gitattributes

> cat image.jpeg | hexdump -C

*.jpeg -text -diff
*.jpeg binary


> git diff

https://github.com/gitattributes/gitattributes

https://github.com/olivierverdier/zsh-git-prompt

https://github.com/magicmonty/bash-git-prompt

> git reset-staging

## Alias

### Shell Alias

+ alias g='git status'
+ alias ga='git add'
+ alias gc='git commit --verbose'
+ alias gs='git switch'
+ alias gpf='git push --force-with-lease'

### Git Alias

[alias]
    a = add
    b = branch
    ci = commit
    co = checkout
    st = status
    stash-all = stash save --include-untracked
    undo = reset --soft ^HEAD
    glog = log --graph --pretty=format:...
    unstage = reset HEAD --

    push-staging = push origin +HEAD:staging
    reset-staging = push origin +refs/remotes/origin/main:refs/heads/staging
    quick-commit = '!f() { git add . && git commit --verbose; }; f'





https://blog.scottnonnenberg.com/better-git-configuration/

https://writeabout.net/2020/12/03/gitvent-a-git-tip-every-day/

Defined in Git configuration





