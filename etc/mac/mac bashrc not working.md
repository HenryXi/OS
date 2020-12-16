# mac bashrc not working
I want to use `ll` command in my MacBook. I try to add .bashrc file in my MacBook and its content is like following.
```
alias ll='ls -lh'
``` 
I close the terminal and reopen it again. `ll` is not working.

**reason**

`.bashrc` and `.bash_profile` is config file for bash. You need to make sure your shell is bash.

Use following command to show your shell name.
```
$ echo $SHELL
/bin/zsh
```

The default shell in my MacBook is zsh. For zsh its config file is `.zshrc` instead of `.bashrc`.

EOF