Bienvenue sur le guide d'utilisation de GitHub à l'UL.

# Première connexion
Afin d'utiliser GitHub, vous aurez besoin de créer un compte personnel dans GitHub. Votre administrateur aura besoin de votre identifiant afin de vous inviter dans la bonne organisation.

Une fois avoir confirmé l'invitation, vous devrez lier votre compte personnel à votre IDUL grâce au lien suivant:

https://github.com/enterprises/universit-laval/sso

Si votre unité de possède pas d'organisation, vous pouvez en faire la demande via le canal le canal de support (voir plus bas).

# Installation du poste de travail
Si vous utilisez Windows, il est recommandé d'utiliser "Git for windows" afin d'éviter d'avoir à resaisir votre mot de passe: https://gitforwindows.org/

Afin de pouvoir tirer ou pousser des changements, vous aurez besoin de créer un "Personnal access token" en allant au lien suivant: https://github.com/settings/tokens
Une fois le jeton créé, vous aurez besoin de sélectionner pour quelle organisation vous désirez vous en servir en cliquant sur "Enable SSO".

Ce jeton devient votre mot de passe à configurer dans votre client préféré.

# Support et nouvelles

Le premier niveau de support se fait via l'administrateur de votre organisation.

En cas de problème ou question ne pouvant être répondu, vous pouvez utiliser le canal "Support Dev" situé dans le Teams "RI - Communauté RI" de manière à partager la connaissance et l'expertise.

Voir https://ulavaldti.sharepoint.com/sites/MAGE/SitePages/CdP-2.0.aspx

Tous changements ou nouvelles relatives au service seront communiqués via le canal de la communauté DevOps.

Nous vous encourageons d'ailleurs à observer et contribuer à ces deux canaux.

# Niveau d'accès et partage du code
Chaque référentiel est lié un niveau de sécurité. Trois valeurs existent qu'il est important de bien comprendre:
- **public**: Accessible en lecture seule au monde entier
- **interne**: Accessible en lecture seule à tous les employés en RI de l'UL incluant les chaires de recherche (les étudiants sont exclus de cette catégorie)
- **privé**: Accessible uniquement aux membres/équipes sélectionnés

Dans l'objectif de facilité le partage d'expertise à l'UL, nous vous encourageons à utiliser le niveau "interne" le plus possible.

Pour donner accès à des contributeurs n'ayant pas d'IDUL employé, vous pouvez utiliser la fonctionnalité de contributeur externe. 

# Nomenclature des noms de référentiels

Nous demandons à tous de respecter la nomenclature suivante dans le nom des référentiels. L'objectif de cette nomenclature est de permettre à tout employé en RI de l'UL de comprendre rapidement ce que peut contenir un référentiel.

\<sigle\>-\<role\>-\<description\>
  
\<sigle\>: Le sigle du produit ou de l'unité. Par exemple: mpo ou bpei.

\<role\>: Le rôle principal que joue ce référentiel. Voici la liste des rôles normalisés:
- **api**: Application offrant un API, par exemple REST ou SOAP
- **app**: Mono-repo contenant une application entière
- **bd**: Script de base de données
- **cms**: Code pour une solution de gestion de contenu, par exemple Wordpress
- **demo**: Référentiel servant à démontrer une technologie
- **devops**: Scripts servant à déployer une application
- **doc**: Documentation
- **docker**: Référentiel servant à construire une image docker à partir d'un Dockerfile
- **etl**: Application de transfert de données ("Extract-Transform-Load")
- **job**: Application s'exécutant en background et réagissant à un trigger (CRON, message, événement)
- **poc**: Preuve de concept
- **scripts**: Scripts d'infrastructure
- **tests**: Suite de tests automatisés
- **ui**: Application front-end, par exemple avec Vue.js
- **web**: Application web, par exemple une application Vaadin

\<description\>: Courte description du référentiel (optionnel)
  
Quelques exemples:

- **sir-web**: Application Web pour la composante SIR
- **sas-etl-banner**: Application permettant d'intégrer les données de Banner avec SAS
- **bpei-doc**: Documentation lié à l'unité BPEI
- **fsg-poc-vuejs**: Preuve de concept de vuejs réalisé par la FSG
- **ena-app**: Mono-repo de l'application ENA incluant les apis, les applications web, les jobs, etc. 

# Sécurité

## SAML
Afin de faciliter la gestion des accès à l'intérieur de GitHub, tous les membres doivent être liés à un IDUL valide (employé RI). Ce lien peut être réalisé en cliquant sur le lien suivant:

https://github.com/enterprises/universit-laval/sso

Un admin peut défaire ce lien au besoin.

## Accès admin
Chaque unité ou chaire de recherche possède son organisation dans GitHub et chacun doit donc identifier ses administrateurs. La responsabilité des administrateurs est d'assurer la gestion des accès, la configuration, la formation, le support et de s'assurer du fonctionnement de son unité.

Au départ, certains administrateurs de la DTI seront aussi administrateurs des organisations des unités. Nous vous demandons de ne pas retirer les accès aux administrateurs de la DTI.

## Gestion des Teams via des groupes Azure AD
Il exite une fonctionnalité permettant de lier des Teams GitHub à des groupes dans Azure AD. Nous vous demandons d'exploiter au maximum cette fonctionnalité.

## Dependabot
Si applicable, nous vous recommmandons d'activer l'outil Dependabot sur vos référentiels pour vérifier périodiquement les vulnérabilités sur vos dépendances.
