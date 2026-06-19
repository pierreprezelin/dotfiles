# Dotfiles

## Introduction

The dotfiles in this repository are installed using a **bare Git repository**. This method does not use symlinks (like most other dotfile repositories).

After the installation, all the dotfiles will be physically present in your home folder, yet, you will still have them under full version control.

## Installation

- Go to your $HOME directory and clone it with `git clone --bare git@github.com:pierreprezelin/dotfiles.git $HOME/.dotfiles`
- Move your existing dotfiles to `~/.dotfiles.backup`
- Check out all the dotfiles (and dot-directories) to your home directory

If you don't need your old dotfiles anymore, you can safely delete the `~/.dotfiles.backup` directory.

## Usage

Now all the dotfiles from the repository are installed in your home directory. However, as mentioned, you still have them under full version control via the bare Git repository in `~/.dotfiles`.

To interact with the bare Git repository, you need the following alias:
```
alias dotfiles='git --git-dir=$HOME/.dotfiles --work-tree=$HOME'
```

With the `dotfiles` alias, you can now manage the dotfiles via the bare Git repository, just as you would with the `git` command:

Edited your dotfiles? No problem, commit and push the changes:
```
dotfiles add ~/.vimrc
dotfiles commit -m "Edit .vimrc"
dotfiles push
```

Pushed changes to the remote repository from another machine? Easy, just pull down the new version:
```
dotfiles pull
```

Want to know what's going on?
```
dotfiles status
```

Don't want to see untracked files:
```
dotfiles config status.showUntrackedFiles no
```

## References

Using a bare Git repository is described here:

- Ask HN: What do you use to manage dotfiles?
- https://harfangk.github.io/2016/09/18/manage-dotfiles-with-a-git-bare-repository.html
- https://developer.atlassian.com/blog/2016/02/best-way-to-store-dotfiles-git-bare-repo/

This README.md is a simplified version of https://gist.github.com/weibeld/869f723063811e5088708a9386bf52bf
