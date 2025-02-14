# Useful commands

## Grep everything

```sh
grep -rni "pandoc" *
grep -rni "pandoc" ./**/Makefile # in specific file
```

## systemctl and journalctl

```sh
SERVICE=service_name.service
systemctl start $SERVICE
journalctl -u $SERVICE -f
```

## tar && zip

```sh
# create
# -c create -v verbose -z gzip -f archivename
tar -cvzf archive.tar.gz directory
zip -r archivename.zip directory

# extract
# -x extract -v verbose -f archivename -C directory
tar -xvf archive.tar.gz -C extracted
unzip archivename.zip -d extracted
```

## Swap

```sh
# Turn swap off
sudo swapoff -a

# Create an empty swapfile 10GB
sudo dd if=/dev/zero of=/swapfile bs=1G count=10

sudo chmod 0600 /swapfile
sudo mkswap /swapfile  # Set up a Linux swap area
sudo swapon /swapfile  # Turn the swap on
```

> <https://askubuntu.com/a/1177939>

## One-liner favicon.ico generator

```sh
TO_ICONIFY=IMAGE.png
for i in 48 96 144 192; do convert $TO_ICONIFY -resize ${i}x${i} favicon-${i}x${i}.png; done; convert favicon-* favicon.ico
```

## txt to pdf

```sh
apt install paps

paps file.txt | ps2pdf - file.pdf
```

## exiftool rename

```sh
exiftool -d '%Y-%m-%d_%H-%M%-S%%-c.%%e' '-filename<CreateDate' .
```

> Reference <https://blog.wxm.be/2024/07/26/exiftool-rename-from-date.html>
