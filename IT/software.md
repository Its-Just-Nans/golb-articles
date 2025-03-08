# Software

## VLC

Subtitle delay shortcut: `g` and `h`

## Thunar sftp connection

```sh
sudo apt install gvfs-backends
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
