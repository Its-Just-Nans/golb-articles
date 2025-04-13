# Software

<!-- commands related to specific 'no-default' package -->

## VLC

Subtitle delay shortcut: `g` and `h`

## Thunar sftp connection

```sh
sudo apt install gvfs-backends
```

## Mongo Config on Windows

These commands are for Windows user - [Documentation](https://docs.mongodb.com/manual/reference/configuration-options/)

If you want to change the moogoDB config, for example, the `bindIp`

- Stop the daemon

```powershell
net stop mongodb # You need to run it as admin
```

- Change your config - located in `<install directory>\bin\mongod.cfg`

Remember it's a YAML file, so you need to produce a correct file. **no tabs but spaces !**. You need to have admin rights to change the config file

- Start the mongoDB daemon

```powershell
net start mongodb # You need to run it as admin
```

## Manually get the fingerprint of a certificate from a browser

- Download the certificate from the browser
- The certificate is in PEM format, a human readable format (base64) but also sometimes with CRLF line endings
- Convert the certificate to a DER format (binary)

    ```sh
    openssl x509 -in certificate.pem -out certificate.der -outform DER
    ```

- Run sha256sum on the DER file

    ```sh
    sha256sum certificate.der
    ```

- Compare the hash with the one from the browser

- Now the public key (which is inside the certificate)
- Extract the public key from the certificate

    ```sh
    openssl x509 -in certificate.der -pubkey -noout | openssl enc -base64 -d > publickey.der
    ```

- Run sha256sum on the public key

    ```sh
    sha256sum publickey.der
    ```

- Compare the hash with the one from the browser

## Locales

```sh
apt install console-data
```

## Remove noise sound when Jack is connected but there is no music

- this is caused by a `power_save` setting, so we need to disable it

```sh
sudo su
echo 0 > /sys/module/snd_hda_intel/parameters/power_save
echo "options snd_hda_intel power_save=0" | sudo tee -a /etc/modprobe.d/audio_disable_powersave.conf # make it persit
```

> - Reference : [https://askubuntu.com/a/1230834](https://askubuntu.com/a/1230834)

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

## Apache not forwarding `Authorization` header to PHP

You need to add in your `.htaccess` :

```bash
CGIPassAuth On
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

## Polyglot powershell and bash script

```sh
echo `# <#`
# bash code
exit
#> > $null
# powershell code
```

> - [https://cspotcode.com/posts/polyglot-powershell-and-bash-script](https://cspotcode.com/posts/polyglot-powershell-and-bash-script)
