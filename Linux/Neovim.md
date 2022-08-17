# Neovim

## Installation
### Installation from source
Installing neovim v0.7.0 from the oficial repo: https://github.com/neovim/neovim/releases/tag/v0.7.0

#### Debian Package
[[Install .deb file| Check debian file installation for  more reference]]

1.  Download **nvim-linux64.deb** [here](https://github.com/neovim/neovim/releases/download/v0.7.0/nvim-linux64.deb)
2.  Install the package using `sudo apt install ./nvim-linux64.deb`
3.  Run `nvim`

## Creation of the configuration folder
```sh
mkdir -p ~/.config/nvim
```
## Creation of  the  simbolic link
>  Check for the path pointing to vim, this is only created to replace vim command for neovim and  remove necessity  of typing nvim on command line
[[Simbolic Links#^dba451 | Check simbolic links for more reference]]

```sh
ln -s $(which nvim) /usr/bin/vim
```