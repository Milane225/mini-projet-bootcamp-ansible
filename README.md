# Playbook Ansible : Déploiement de Site Web dans un Conteneur Apache

Ce playbook Ansible utilise un rôle pour installer un conteneur Apache et y déployer un site web. Le contenu du site est récupéré depuis les templates définis dans le rôle.

## Prérequis

- Ansible 2.0 ou version supérieure.
- Docker installé sur la machine cible pour exécuter le conteneur Apache.
- Le rôle Ansible requis pour l'installation et le déploiement du site : `ansible-role-webapp`