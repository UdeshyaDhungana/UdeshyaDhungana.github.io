+++
date = "2020-08-12"
title = "Using Neovim for programming"
+++

As a programmer, I have this never ending thirst for productivity. On
the journey of quinching this thirst, a few months ago, I stumbled
upon a fantastic
[lecture](https://www.youtube.com/watch?v=a6Q8Na575qc) on YouTube
about Vim. After that, I started to use Vim. It wasn't my first
introduction to Vim though. I first came to know about it about an
year ago. Still, I hadn't been able to use it as my main editor,
because of one big problem: the learning curve. Vim is not easy to
learn, but once you get the hang of it, it starts to pay you off. It
took me about 20 days to become comfortable with it. So, if you're
planning on using it, don't be frustrated in the beginning. It'll test
your patience, but you must stand your ground. I assume you are on a
Linux system. Let's begin.

## Learning

Type `vimtutor` on your terminal to open Vim tutorial. It's a short
interactive guide that teaches you the basics of Vim. Take as much
time as you want. It's short but you need to memorize the
commands. After completing the tutorial, your brain will have known
the basic functionalities of Vim, but your fingers won't have. So,
here comes the most difficult task: make your fingers learn Vim. Use
it as your main editor for next couple of weeks, or even a month. The
point is, you need to be comfortable with it. It won't be easy. You'll
struggle. You may even want to break your keyboard at some
point. You'll beg yourself to stop and go back to VSCode. But, please
don't. Here's a little motivation from Bojack Horseman:

> It gets easier. Every day it gets a little easier. But you gotta do
> it every day, that's the hard part. But it does get easier.

## Making Neovim your IDE

After you're comfortable with moving around, inserting, selecting and
other fundamental tasks, you should now work on making Vim your
IDE. There is a better variant of Vim, called Neovim which is a Vim
based text editor. It comes with all the functionalities of vim, along
with many added features. So, you may want to use it instead of
original one. Head over to [Neovim Homepage](https://neovim.io/) to
download it. Once you have installed it, create a `init.vim` file
inside the directory `~/.config/nvim`. If any of the folders in the
given path do not exist, create it.

`init.vim` is the configuration file for Neovim. You can set different
options here, from font family to indentation length, and thousands
more.  But, it will be nearly impossible to write your own config file
as a beginner. So, grab a well commented config file from Github and
copy the contents to your own config file. Here is
[mine](https://github.com/UdeshyaDhungana/dotfiles/blob/master/nvim/init.vim). Don't
just bulk copy the contents. Understand what each line is doing. Use
[Vim Wiki](https://vim.fandom.com/wiki/Vim_Tips_Wiki) as a
reference. You may want to change some of those configuration later.

## Using plugins

Now, it's time to fully unleash Neovim's power. That's when plugins come handy. There are thousands of open source plugins available online, made by developers, for developers. To install plugin, you will need a plugin manager. Some popular plugin managers are [vim-plug](https://github.com/junegunn/vim-plug), [pathogen](https://github.com/tpope/vim-pathogen), and [Vundle](https://github.com/VundleVim/Vundle.vim). I use vim-plug. You'll find installation instructions on the given Github links.

Everything is easy from here on. Find a plugin, install it using your plugin manager. Additionally, you can configure plugins as per your desire. Almost all popular plugins have a well written documentation. So, don't worry about getting lost. Believe me, you'll figure things out.

Here are the plugins I use:

  - [Conquerer of Completion](https://github.com/neoclide/coc.nvim)
      - For code autocompletion
      - Install language extensions for the languages you use.

  - [Polyglot](https://github.com/sheerun/vim-polyglot)
      - Syntax highlighting

  - [Lightline](https://github.com/vim-airline/vim-airline)
      - An amazing status bar for neovim

  - [Highlighted
    Yank](https://github.com/machakann/vim-highlightedyank)
      - Highlight the copied(yanked) text

  - [NERDTree](https://github.com/preservim/nerdtree)
      - File explorer for Vim

  - [Multiple
    Cursors](https://github.com/terryma/vim-multiple-cursors)
      - Name speaks for itself

  - [Vim Surround](https://github.com/tpope/vim-surround)
      - Surround text with tags, braces or quotation

  - [FZF](https://github.com/junegunn/fzf)
      - A fast File finder

  - [Gruvbox](https://github.com/morhetz/gruvbox)
      - Colorscheme with light and dark mode


You may install other plugins too, there are language or framework
specific plugins which you may find useful. One thing though, just
don't bloat your setup with a bunch of plugins that you won't use,
because plugins have significant impact on startup time. Keep only the
necessary ones. Good luck on your Vim journey.

Vim is a powerful and fast text editor. Though learning it may require
some time and extra effort, it's knowledge will certainly pay you off
with increased productivity.
