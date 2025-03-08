# Utils to debug

## Remove noise sound when Jack is connected but there is no music

- this is caused by a `power_save` setting, so we need to disable it

```sh
sudo su
echo 0 > /sys/module/snd_hda_intel/parameters/power_save
echo "options snd_hda_intel power_save=0" | sudo tee -a /etc/modprobe.d/audio_disable_powersave.conf # make it persit
```

> - Reference : [https://askubuntu.com/a/1230834](https://askubuntu.com/a/1230834)

## Utilisation de `su` sur Linux (Debian)

La commande `su` permet de changer s'utilisateur pour le temps d'une session (après avoir saisi le mot de passe, s'il y en a un), pour l'utiliser, on écrit :

```sh
su UTILISATEUR
```

On peut aussi l'utiliser pour devenir root simplement en écrivant :

```sh
su
```

Pour devenir superutilisateur sur Linux, on peut faire la commande `su`. Mais parfois, cela ne suffit pas, nous n'avons toujours pas les droits, c'est normal : nous n'avons pas chargé les variables d'environnement du superutilisateur.

Pour ce faire faites simplement

```sh
su -l
#ou encore
su -
#dans ce dernier cas, s'il y a plusieurs options, il faut que le tiret soit la dernière option, avant le pseudo
```

Reference : [manpages.debian](https://manpages.debian.org/stretch/login/su.1.fr.html)

Add a user to sudoers

```sh
sudo adduser USERNAME sudo
```

## nginx configuration

Useful commands

```sh
# check nginx config before restart
nginx -t
server nginx restart
```

Conf example

```conf
  merge_slashes off; # useful for a reverse proxy
  location / {
      proxy_pass          http://localhost:4200/;
  }
```

## webook package

The [webhook package](https://github.com/adnanh/webhook) is a useful utility package which create a server listening on 9000 and allow you to create responses to webhook.

Useful commands for the package

```sh
# edit the default conf file, can be yaml or json
nano /etc/webhook.conf

# to debug
# edit the service file
nano /etc/systemd/system/multi-user.target.wants/webhook.service
# add -verbose to ExecStart
# restart
systemctl restart webhook
# get verbose output
systemctl status webhook
```
