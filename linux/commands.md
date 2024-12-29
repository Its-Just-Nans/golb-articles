# Useful commands on Linux

- [https://github.com/you-dont-need/You-Dont-Need-GUI](https://github.com/you-dont-need/You-Dont-Need-GUI)
- [https://github.com/jlevy/the-art-of-command-line](https://github.com/jlevy/the-art-of-command-line)

## Cool commands

```sh
!! # last command
sudo !! # last command as root

mkdir -p /mnt/ram; mount -t tmpfs tmpfs /mnt/ram -o size=4096M # create a ram disk

ls # with a trailing space -> not in history
disown -a && exit # leave terminal but don't kill running processes
```

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
zip
# zip ARCHIVE.zip FILE
gzip
gunzip
# gzip FILE
bzip2
# bzip2 FILE
```

### get information about a file

```sh
file
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

## Redirection

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

### Pipes

```sh
CMD_1 | CMD_2
```

### Multiple commands

```sh
CMD_1 ; CMD_2 ; CMD_3
```

### Background task

```sg
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

## Switch between background and foreground

```sh
command &
fg # change to foreground
# pause with CTRL+Z
bg # sent it to background
```
