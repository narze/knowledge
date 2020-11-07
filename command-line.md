# Command Line

## Zsh

I use [Zsh](https://www.zsh.org/) as my main shell, with [Zplug](https://github.com/zplug/zplug) as a plugin manager \(Previously used [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) and [Prezto](https://github.com/sorin-ionescu/prezto)\)

### Dotfiles

I maintain my own dotfiles within [my laptop script](https://github.com/narze/laptop). If you're new to dotfiles I highly recommended forking [Holman's](https://github.com/holman/dotfiles) or [Mathiasbynen's](https://github.com/mathiasbynens/dotfiles)

### Homebrew

Almost any command line apps \(and even macOS apps\) can be installed through [Homebrew](https://brew.sh/). My list of [command line apps](https://github.com/narze/laptop/blob/master/ansible/roles/packages/tasks/homebrew.yml) and [macOS apps](https://github.com/narze/laptop/blob/master/ansible/roles/packages/tasks/cask.yml) are listed in my Ansible playbooks which runs `brew install` and `brew cask install` through the list.

## Links
- [The Linux Commands Handbook](https://www.freecodecamp.org/news/the-linux-commands-handbook) - 60 core `bash` commands

