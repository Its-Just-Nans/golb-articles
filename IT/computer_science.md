# Computer science

## OS

- Le `BIOS`: C'est le premier système d'exploitation qui s'execute au démarrage de I'ordinateur. Il permet de voir les caractéristiques des composants et de changer leurs propriétés.
- Le `GRUB`: C'est le système d’amorçage permettant de faire le lien entre le noyau Linux et les systèmes d'exploitation situes sur le disque dur.

## Les ports applicatifs

Différence des ports :

- port __materiel__ : désigne I'interface physique à laquelle un cable doit être branche
- port __logiciel__ : point d'entrer dans une communication utilisant un protocole particulier

Le port logiciel est aussi appelé port applicatif car il fait correspondre un numero code sur `16` bits (allant de `1` à `65536`) avec une application.

Principaux ports :

- Port `21` : le protocole `FTP`. C'est un protocole d'échange de fichiers.
- Port `22` : le protocole `SSH`. Il est utilisé dans la quasi-totalité des connexions à des machines distantes. II permet de crypter les échanges et de rendre illisibles les informations si celles-ci venaient à être interceptées.
- Port `25`, `465`, `587` : le protocole `SMTP`. II s'agit d'un protocole permettant I'envoi de message.
- Port `53` : le protocole `DNS`. Sa fonction est de faire correspondre une adresse IP et un nom de domaine, et réciproquement.
- Port `67` (serveur), `68` (client) : le protocole `DHCP`. II permet d'attribuer une adresse IP (ainsi que les configurations d'adressage associées comme le masque, I'adresse de passerelle) de manière automatique à un noeud du reseau qui en fait la demande.

## Le Protocole SMTP

Le protocole SMTP est le protocole à configurer lors de la creation et la configuration d'un serveur de gestion d'e-mails (envoi). Son port par défaut est le `25`.

Afin de recevoir des emails sur un client (comme Thunderbird ou Outlook), il est possible d'utiliser les protocoles suivants:

- `IMAP4`: Il permet de visualiser et d'apporter les modifications directement sur le serveur de messagerie a partir du client. Seuls les entêtes des messages sont téléchargées. Son port par défaut est le `143`.
- `POP3`: Le protocole télécharge une copie des messages sur I'ordinateur. Cela permet notamment de travailler sans connexion Internet. Cependant une connexion est nécessaire pour synchroniser les nouveaux messages. Il communique sur le port `110`.

## DNS

Le service DNS (Domain Name System) est indispensable pour aller sur Internet. Des lors que I'on ne connaît I'adresse IP d'un site web, le DNS va convertir le nom de domaine en adresse IP et réciproquement.

Les `TLD` (`Top Level Domain`) correspondent aux extensions mises a la fin d'une URL permettant d'identifier de manière unique un `FQDN`. Le `FQDN` (Fully Qualified Domain Name) correspond au nom complet (avec I'extension inclue) du nom de domaine. II existe plusieurs types d'entree DNS:

- `A`: Effectue une correspondance entre une adresse IPv4 et un nom de domaine
- `AAAA`: Effectue une correspondance entre une adresse IPv6 et un nom de domaine
- `CNAME`: Il s'agit d'un alias, a savoir un mécanisme qui effectue une correspondance entre un nom et un compte avec un nom généralement plus long ou plus complique a retenir
- `MX`: Les enregistrements de type `MX` désignent Mail Exchanger. Ils font le lien entre le nom donne et le serveur d'envoi de mail. - `VNC` (a ne pas confondre avec VLC media player) est une solution complete avec des paramètres détaillés permettant de prendre la main pour dépanner une machine distante.
