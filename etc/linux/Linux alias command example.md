# Linux alias command example
`alias` can help you make long command as a shortcut. For example, you have to type `mysql -h host_address -u user_name -p`
when you need access mysql remotely. `alias` can make this efficiently. Create a shortcut for remote accessing by using the command below.
Next time when you want to access database just type `mysql-remote`.
```bash 
> alias mysql-remote='mysql -h host_address -u user_name -p'
```
Using `alias` without any parameter can list all shortcut commands. One of the most famous shortcut commands is `ll`.
It is the shortcut of `ls -l`.
```bash
> alias
alias cp='cp -i'
alias l.='ls -d .* --color=auto'
alias ll='ls -l --color=auto'
alias ls='ls --color=auto'
alias mv='mv -i'
alias rm='rm -i'
alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
```
 
