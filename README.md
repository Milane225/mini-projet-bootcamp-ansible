# Playbook Ansible : Déploiement de Site Web dans un Conteneur Apache à partir d'un rôle

Ce playbook Ansible utilise un rôle pour installer un conteneur Apache et y déployer un site web. Le contenu du site est récupéré depuis les templates définis dans le rôle.

## Prérequis

- Ansible 2.0 ou version supérieure.
- Docker installé sur la machine cible pour exécuter le conteneur Apache.
- Le rôle Ansible requis pour l'installation et le déploiement du site : `ansible-role-webapp`

## Pre-Tasks

- Installation des paquets EPEL, git et wget.
- éléchargement du script d'installation de `pip`.
- Installation de pip pour Python 2.7
- Installation de `docker-py` via `pip`

## Encryptez le fichier credentials.vault contenu dans le dossier files à l’aide de la commande ansible-vault encrypt
```
ansible-vault encrypt files/secrets/credentials.vault
```

## Pour vérifier que le fichier credentials.vault a été bien encrypté
```
cat files/secrets/credentials.vault
```

## Récupération des rôles Ansible
```
ansible-galaxy install -r roles/requirements.yml
```
## Bien renseigner l'IP de votre client dans le fichier hosts.yml
Ip à renseigner dans le fichier `hosts.yml`

## Lancez votre PlayBook
```
ansible-playbook -i hosts.yml --ask-vault-pass -vvv tests.yml
```

## Vérifiez que le site a été bien deployé chez le client
Ouvrez le port `80`
