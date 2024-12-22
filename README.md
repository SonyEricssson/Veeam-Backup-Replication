# Installation de Veeam Backup & Replication 

<img src="https://github.com/user-attachments/assets/2cc256a3-5f62-4b75-a8e8-4685a0f27e5d" alt="veeam" width="100">

## Introduction

Ce document décrit les étapes d'installation et de configuration de Veeam Backup & Replication pour un environnement Ericsson. Il couvre l'installation sur Windows ainsi que la sauvegarde de serveurs Linux (GestSup).


## Prérequis

- Un serveur Windows pour installer Veeam Backup & Replication.

- Un serveur Linux (GestSup) avec accès SSH.

- Droits d'administration sur les serveurs concernés.
---

## Installation de Veeam Backup & Replication

**Téléchargement et installation :**

- Télécharge la version gratuite depuis le [site officiel de Veeam.](https://www.veeam.com/products/free/backup-recovery.html)

- Exécute le fichier d'installation et suis les instructions pour installer Veeam sur le serveur Windows.

## Ajout du serveur Linux (GestSup)

**Ajout d'un serveur Linux :**

- Accède à **"Backup Infrastructure"** dans le menu de gauche.

- Sélectionne** "Managed Servers".**

- Clique sur **"Add Server"** > **"Linux".**

- Saisis le nom DNS ou **l'adresse IP du serveur Linux GestSup** (exemple : 10.10.1.10).

**Authentification SSH :**

- Clique sur **"Add..." > "SSH credentials".**

**Renseigne :**

- **Nom d'utilisateur** : utilisateur avec droits sudo ou root.

- **Mot de passe** : mot de passe associé.

- Valide en cliquant sur **OK** ou Next.

## Création d'un Job de sauvegarde

**Création du job :**

- Va dans l'onglet **"Home".**

- Clique sur **"Backup Job" > "Linux".**

- Ajoute l'hôte Linux GestSup précédemment configuré.

- Saisis l'adresse IP **(ex : 10.10.2.101).**

- Donne un nom au job **(ex : Backup_GestSup).**

- Spécifie le chemin à sauvegarder **(ex : /var/lib/mysql).**

**Traitement des applications (facultatif) :**

- Coche "Enable application-aware processing" pour assurer une sauvegarde cohérente des applications (SQL Server, Exchange, etc.).

- Pour une sauvegarde basique, décoche cette option.

- Pour MySQL, prévois un script d'arrêt temporaire avant la sauvegarde.

## Vérification des backups

**Consulter l'historique des jobs :**

- Ouvre l'interface de Veeam Backup & Replication.

- Clique sur **"History" pour visualiser l'état des sauvegardes (terminé, en échec, etc.).**

**Répertoires de sauvegarde :**

Accède à **"Backup Infrastructure" > "Backup Repositories"** pour vérifier les détails des sauvegardes.

