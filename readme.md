# Guide installation WordPress

##  Créer une base de données

## Télécharger Wordpress 

```bash
wget https://fr.wordpress.org/latest-fr_FR.zip
```

```bash 
unzip latest-fr_FR.zip
```

## Stocker le chemin absolu vers notre WP

```bash 
pwd
```


## Se déplacer dans le dossier de configuration Apache

```bash
cd /etc/apache2/sites-available
```

## Créer un nouveau fichier de config pour notre Virtual Host

```bash
sudo cp 000-default.conf 'nomDeMonSite'.conf
```

## Editer ce fichier de configuration

 Editer ce fichier de configuration avec ```sudo-nano``` : 

 - Décommenter la ligne ```ServerName ``` et ajouter après ``ServerName `` : ``"nomDeMonSite".local``
 - Ajouter après ``DocumentRoot`` le chemin absolu vers notre WP
 - Pour sauvegarder les modifications faites : ``ctrl+o``, ``enter``, ``ctrl+x``

## Activer le fichier de configuration 

```bash
sudo a2ensite 'nomDeMonSite'.conf
```

Relancer ensuite le service Apache2 avec la commande :
```bash 
sudo service apache2 reload
```

## Editer le fichier ``hosts``

```bash
sudo nano /etc/hosts
```

Ajouter une ligne correspondant à notre projet : 
```bash
127.0.0.1 "nomDeMonSite".local
```

 - Pour sauvegarder les modifications faites : ``ctrl+o``, ``enter``, ``ctrl+x``

## Accéder à l'URL d'installation dans le navigateur 

`` http://"monDeMonSite".local``

## Changer le propriétaire du dossier de notre WordPress 

```bash 
sudo chown -R www-data:www-data ./wordpress
```

## Changer les droits 

```bash
sudo chmod -R 777 wordpress/
```

