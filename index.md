# cURL - Pour l'envoie ou la récupération de données depuis/vers un Serveur.

## Presentation 

`cURL` est un logiciel en ligne de commande destiné a effectué des requetes vers des URL. Il supporte plusieurs protocoles tel que: `DICT` `file` `FTP` `FTPS` `Gopher` `HTTP` `HTTPS` `IMAP` `IMAPS` `LDAP` `LDAPS` `POP3` `POP3S` `RTSP` `SCP` `SFTP` `SMB` `SMBS` `SMTP` `SMTPS` `Telnet` et `TFTP`.
Il est a été créé en 1997 par Daniel Stenberg.
Il constitue une alternative gratuite au célèbre logiciel `Postman` pour l'envoie de données vers une API.
[Lien Github du dépot cURL](https://github.com/curl/curl).

## Installation

Sous Linux on peut installer curl grace à la commande 
```bash
apt-get install curl
```
ou

```bash
yum install curl
```

## Utilisation

### Envoie de requete vers un serveur (Protocoles HTTP/HTTPS)

Par défaut pour utiliser `cURL` pour envoyer des données vers un serveur, on utilise la commande `curl` suivit de l'adresse de destination:

```bash
curl http://www.example.com
```
La méthode utilisée par défaut pour ce type de requete est la méthode `GET`

Cette de requète renverra le contenu du fichier html du site web situé à l'adresse `www.example.com`

Le resultat d'une requete peut etre envoyer vers un fichier. 
Par exemple si nous voulons stocker le résultat de notre requete dans un fichier html:

```bash
curl www.example.com > site.html
```

On peut aussi utliser plusieurs autres types de requetes notemment:

`POST` : Pour envoyer des données au serveur.

`GET` : Pour récuperer des données depuis un serveur.

`PUT` : Pour modifier des données sur un serveur.

`DELETE` : Pour supprimer des données sur un serveur.

Pour envoyer une requete de type `POST` vers un serveur

```bash
curl --request POST --url "http://www.example.com"
```

`--request` : permet de spécifier le type de requete envoyé au serveur

`--url` : permet de spécifier l'adresse du serveur à contacté.

On peut aussi préciser le type de données envoyé au serveur grace à l'argument `--header`  

L'option `-d` permet de lister les données à envoyer au serveur.

En résumé, si nous voulons par exemples envoyer une requete de type `POST` avec des données d'un utilisateur.

```bash
curl --request POST  --header "Content-Type : application/json" --url  "http://www.example.com" -d 'name=test'
```

Pour en savoir d'avantage sur le logiciel `cURL` : [Manuel d'utilisation de cURL](https://curl.se/docs/manpage.html)
