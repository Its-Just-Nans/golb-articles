---
title: Linux Commands
description: A list of useful Linux commands
keywords: linux, commands, shell, terminal
---

# Commands

<!-- One command per paragraph -->

## Basic commands

### create a file

```sh
touch
# touch FILE
```

### create a folder

```sh
mkdir
# mkdir DIR
```

### delete a folder

```sh
rmdir
# rmdir DIR
rm -r
# rm -r DIR
```

### compare file

```sh
diff
# diff FILE_1 FILE_2
cmp
# cmp FILE_1 FILE_2
comm
# comm FILE_1 FILE_2
```

### compression

```sh
gzip
gunzip
# gzip FILE
bzip2
# bzip2 FILE
```

### get information about a file

```sh
file <file>
# file temp.txt
```

### delete duplicate lines

```sh
uniq
```

### get limits of the OS

```sg
ulimit -a
```

### fusion files

```sh
cat
# cat FILE_1 FILE_2
paste
# paste FILE_1 FILE_2
```

### set file mode creation mask

```sh
umask
```

### Redirection

```sh
# override to FILE
cmd > FILE
# append to FILE
cmd >> FILE
```

```sh
cmd >& FILE
```

```sh
cmd &> FILE
```

> redirect stdout and stderr to FILE

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

## See kill signals

```sh
# show all signals
kill -L
kill -SIGKILL <PID>
kill -9 <PID>
```

## Others

```sh
pstree
kill
crontab
nice
write
mesg
telnet
ssh
ftp
```

## Shell tricks

```sh
!! # last command
 ls # with a trailing space -> not in history

disown -a && exit # leave terminal but don't kill running processes
```

## Switch between background and foreground

```sh
command &
fg # change to foreground
# pause with CTRL+Z
bg # sent it to background
```

## tar && untar

```sh
# create
# -c create -v verbose -z gzip -f archivename
tar -cvzf archive.tar.gz directory

# extract
# -x extract -v verbose -f archivename -C directory
tar -xvf archive.tar.gz -C extracted
```

## zip && unzip

```sh
# create
zip -r archivename.zip directory

# extract
unzip archivename.zip -d extracted
```

## Grep everything

```sh
grep -rni "pandoc" *
grep -rni "pandoc" ./**/Makefile # in specific file

# or use ripgrep https://github.com/BurntSushi/ripgrep
```

## systemctl and journalctl

```sh
SERVICE=service_name.service
systemctl start $SERVICE
journalctl -u $SERVICE -f
```

## Get disk space with `df`

```sh
df -h

# also know type of partition
df -Th
```

> - `-T` : `--print-type`
> - `-h` : `--human-readable`

## Get size of files with `du` or `dust`

```sh
cargo install du-dust

dust
# or
du -d 1 -h | sort -h
```

## screen command

```sh
# start new "infinite" shell - read the manual for more info
# CTRL + A then "D" to leave
screen

# list screens shell
screen -ls

# resume screen shell
screen -r <screen_id>
```

Alternatives:

- [https://www.byobu.org/](https://www.byobu.org/)
- [https://github.com/tmux/tmux](https://github.com/tmux/tmux)

## IPs

Args

- `-c` : colored output
- `-j` : json output
- `-j -p` : json indented output
- `-d` : more information

| Command `net-tools` | Command `iproute2` | Description             |
| ------------------- | ------------------ | ----------------------- |
| `ifconfig -a`       | `ip addr`          | Show IP address         |
| `arp -a`            | `ip neigh`         | Show ARP table          |
| `route`             | `ip route`         | Show network interfaces |
| `netstat -g`        | `ip maddress`      | multicast               |

## Search path of a command

```sh
which <command>
whereis <command>
type <command>
command -v <command>
```
