# Linux alias command permanent
The command `alias` helps us us short command instead of long command and parameters. The problem is when you next time login the
shortcut is disappeared. You need to change the `.bashrc` file to define your specific aliases. The path of `.bashrc` is 
`~/.bashrc`. For example, you want us vim instead of vi command. Edit your `.bashrc` file like following.
```
# .bashrc

# User specific aliases and functions

alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'
alias vi='vim'

# Source global definitions
if [ -f /etc/bashrc ]; then
        . /etc/bashrc
fi
```