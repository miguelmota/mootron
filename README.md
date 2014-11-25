# MOOTRON

A [Tron](http://en.wikipedia.org/wiki/Tron:_Legacy) like terminal theme.

![](https://github.com/miguelmota/mootron/blob/master/screenshot.png)

# Instructions (Mac OSX)

- Install font
- Go to `Terminal -> Preferences -> Settings`, click cog at the bottom and import `Mootron.terminal`.
- Go to `Window` tab and set background color to black 90% opacity and choose background image.
- If you want to be hardcore, then on the `Text` tab uncheck `Display ANSI colors`.

# Vim theme

Copy `warez.vim` to `~/.vim/colors`, and enable theme in `~/.vimrc`:

```bash
syntax enable
colorscheme warez
```

# Prompt

Light cyan prompt color with git status, add in `~/.bashrc`:

```bash
function parse_git_dirty {
  [[ $(git status 2> /dev/null | tail -n1) != "nothing to commit (working directory clean)" ]] && echo "*"
}
function parse_git_branch {
  git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e "s/* \(.*\)/[\1$(parse_git_dirty)]/"
}

export PS1='\n\n\[\033[0;36m\]\u@$(hostname)\[\033[00m\]\[\033[0;96m\] : \w\[\033[00m\] \[\033[00;96m\]$(parse_git_branch)\n\[\033[00;96m\]\$\[\033[00m\] '
export PS2="\[\033[0;96m\]>\[\033[00m\] "
```

Take effect:

```bash
source ~/.bashrc
```

# Other stuff

I also have [tmux](http://tmux.sourceforge.net/) and [Powerline](https://github.com/Lokaltog/powerline) installed. I can't gurantee that it will look exactly the same for you because of all the other stuff I have installed. If you're curious here are all my [dotfiles](https://github.com/miguelmota/dotfiles) and [vim config](https://github.com/miguelmota/dotvim).

# Sources

- [Warez Vim theme source](https://github.com/vim-scripts/warez-colorscheme/blob/master/colors/warez.vim)
- [Bitstream font source](http://www.dafont.com/bitstream-vera-mono.font)
- [Circuit wallpaper source](http://wallpaperswide.com/circuit_board_art-wallpapers.html)

# License

MIT
