---
title: Bash
---

- <https://github.com/dylanaraps/pure-bash-bible>

### Redirection

```sh
# override to FILE
cmd > FILE
# append to FILE
cmd >> FILE
```

```sh
cmd &> FILE

cmd >& FILE
```

> redirect stdout and stderr to FILE

```sh
cmd | cmd2
```

> The standard output of cmd is connected via a pipe to the standard input of cmd2.

```sh
cmd |& cmd2
```

> cmd's standard error, in addition to its standard output, is connected to cmd2's standard input through the pipe

### Standard input

```sh
cmd < FILE
cmd <<< "string"
```

### Pipe

```sh
CMD_1 | CMD_2
```

### Multiple commands

```sh
CMD_1 ; CMD_2 ; CMD_3
```

### Background task

```sh
CMD &
```

### Conditional commands

```sh
CMD_1 && CMD_2
CMD_1 || CMD_2
```

## Shell tricks

```sh
!! # last command
 ls # with a trailing space -> not in history

disown -a && exit # leave terminal but don't kill running processes
```

## Basic command completion

```sh
_my_cmd(){
    local cur opts
    # Current word being completed
    cur="${COMP_WORDS[COMP_CWORD]}"

    # The words you want to complete
    opts='run copy $(ls)' # or however you want to list them

    # Fill COMPREPLY with matches
    COMPREPLY=( $(compgen -W "${opts}" -- "$cur") )
}

# some completion for my_cmd
if [[ -v BASH_VERSINFO && "$BASH" == */bash ]]; then
    complete -F _my_cmd my_cmd
fi
```
