# mac copy current path to clipboard in terminal
In order to copy the current path to the clipboard you can use the following command.
```
pwd|pbcopy
```
In order to execute the above command more conveniently, you can put it in your configuration(`.bashrc` or `.zshrc`) file.
```
alias cppath='pwd|pbcopy'
```

EOF