# lxw

## LXC wrapper with bash-completion

There are reasons why Docker is not solving all our problems ... so LXC to the rescue!

This wrapper allows you to use LXC with better cli interface IMHO. There are other wrappers in the wild, but they are:

* not written in shell script (you have to have runtime installed or compile them),
* not protecting me against my lack of knowledge,
* without automatic bash completion.

The best feature of this wrapper is ... **bash autocompletion**!

### Examples for people new to completion:

```shell
lxw <TAB>        #for all actions
lxw info <TAB>   #will list all containers
lxw kill <TAB>   #will list only running containers
```

### Installation:

You need **lxc** in version 3.0 or newer installed.

```shell
$ git clone https://github.com/ernierasta/lxw && cd lxw
$ ./install
```
Optionally you can make alias to always run with sudo:
```shell
$ # command below will add alias to .bash_aliases if exist, otherwise to .bashrc
$ [ -f ~/.bash_aliases ] && echo -e "alias lxw='sudo lxw'\n" >> ~/.bash_aliases || echo -e "alias lxw='sudo lxw'" >> ~/.bashrc
```
Then open new terminal window.

### Update:

```shell
$ cd lxw
$ git pull
$ ./install
```

### Usage:

```shell
$ lxw new mycontainer
$ lxw net mycontainer # WARNING! This is experimental feature, will be improved or removed in future.
$ lxw frestart mycontainer # or restart
$ lxw attach mycontainer
$ lxw run mycontainer "ls -al"
$ lxw del mycontainer
```

For full help run:
```shell
$ lxw
```

### Motivation:

I generally find multi-binary interfaces not very convenient. Especially when there is not good autocompletion.

### Todo:

- look at default lxc installation in Debian, Ubuntu, Fedora, ... only Void Linux is tested,
- improve, fix net command,
- better testing
- add more commands if needed, some options if needed ...

