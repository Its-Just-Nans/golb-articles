# Linux utils

## Links

- [https://cspotcode.com/posts/polyglot-powershell-and-bash-script](https://cspotcode.com/posts/polyglot-powershell-and-bash-script)
- [http://www-igm.univ-mlv.fr/~dr/NCS/CS2004.pdf](http://www-igm.univ-mlv.fr/~dr/NCS/CS2004.pdf) - cours système
- [https://www-igm.univ-mlv.fr/~dr/NCS/CS2004.pdf](https://www-igm.univ-mlv.fr/~dr/NCS/CS2004.pdf)
- [https://perso.telecom-paristech.fr/apvrille/](https://perso.telecom-paristech.fr/apvrille/)

## Learn multiplications

```sh
for i in {5..7}; do  for e in {5..7}; do echo "$i*$e=$(bc<<<$i*$e)" | spd-say -e ;sleep 2; done; done
```

## Get sound update

```sh
watch -n 10 'mycommand && spd-say done || echo "no"'
```

## Know type of partition

```sh
df -Th
```

> Legend :
>
> - `-T` : `--print-type`
> - `-h` : `--human-readable`

## Change partition

```sh
fdisk /dev/sda

# touch d for delete partition

# touch n for new partition
```

## Format partition

```sh
mkfs.vfat /dev/sda1
```

## Use dd to copy an ISO

```sh
dd if=file.iso of=/dev/sda bs=1M status=progress
```

> Legend :
>
> - `if` : input file
> - `of` : output file
> - `bs` : block size

## Copy file to clipboard

```sh
xclip -sel c < input_file
```

> Reference: [https://stackoverflow.com/a/62168635](https://stackoverflow.com/a/62168635)

## Show listening ports

```sh
ss -ptulwn | grep LISTEN
```

## Change the pager

Change the pager of `man` :

```sh
export PAGER=less
```

## Download urls

```sh
cat a | while read f; do curl -L -b 'cookie=value' -O -J "${f}"; done
```

## Cron helper

- [https://crontab.guru/](https://crontab.guru/)

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

## iftop

```sh
sudo iftop -s wlp0
# change to your interface
```

## slock

```sh
slock
```

## aspell

```sh
aspell -l en -c file.txt
```

## qemu

- [https://wiki.debian.org/KVM](https://wiki.debian.org/KVM)

```sh
apt install qemu-system libvirt-daemon-system
adduser $USER libvirt
apt install virt-manager # nice GUI
```

## Utils

```sh
# IPv4 addresses:
cat /proc/net/fib_trie

# hex-encoded port data:
cat /proc/net/tcp
```

## ngrok alternative

- [https://ngrok.com/](https://ngrok.com/)
- [https://localtunnel.github.io/www/](https://localtunnel.github.io/www/)

```sh
# ngrock (need install)
ngrok http 80

# localtunnel package (npx of bunx)
npx localtunnel --port 8000
bunx localtunnel --port 8000
```
