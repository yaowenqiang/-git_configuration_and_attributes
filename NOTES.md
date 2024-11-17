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

> git config --local user.email 'jacky.email'

Additional Configuration Capabilities

+ Environment Variables
  + GIT_AUTHOR_EMAIL ( Not recommended)
+ Additional levels
  + includeIf









