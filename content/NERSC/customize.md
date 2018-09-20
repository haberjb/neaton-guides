---
title: "Customize"
date: 2018-09-18T23:06:01-07:00
weight: 3
draft: true
---

Those familiar with the Unix operating system have likely encountered 
_dot files_ before (.ssh, .bashrc, .vimrc, .matplotlibrc, etc...). These
dot files essentially allow users 

## Setting up ~/.ssh/config
Logging in to NERSC with the same ssh command every time will get old 
very quickly. We can automate the process in a couple ways.

On your local machine, you should have a file called:

~/.ssh/config

if you dont have one, you can create one with:

    touch ~/.ssh/config

every time you use the ssh command your system looks in this file 
(atleast thats what the [man pages](https://linux.die.net/man/5/ssh_config) 
say. To be honest, I have no idea how any of this stuff works. Anyway the 
point is you can make your life easier by providing some information in

Open your config file (with vim, emacs, nano etc.) and add the following lines:

## A suggested file system

## Modifying .bashrc.ext

## Optional: vimrc
