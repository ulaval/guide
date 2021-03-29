# Intégration de GitHub avec le Jenkins de la DTI

Pour permettre à Jenkins de faire des "pull" et de communiquer le statut des builds à GitHub, il est important de bien configurer la relation de confiance entre les deux outils.

Pour ce faire, le plus simple est d'utiliser une "GitHub App" qui va permettre de créer une identité propre à Jenkins.

- Aller dans les settings de votre organisation / Developper settings / GitHub Apps
- Cliquer sur "New GitHub apps"
- Saisir les informations demandées
  -	Callback url: https://jenkins.svc.ulaval.ca/securityRealm/finishLogin
  -	Disable webhook
  -	Authorizations
    - Checks: Read-Write
    - Commit statuses : Read-Write
    -	Contents: Read-Only
    - Deployments: Read-Write
- Créer l'application
- Prendre en note la valeur du champ "App ID"
- Dans le bas, cliquer sur "Generate a private key"
- Télécharger la clé générée dans un dossier sur votre poste
- Ouvrir "Git Bash"
- Taper la commande:
> openssl pkcs8 -topk8 -inform PEM -outform PEM -in key-in-your-downloads-folder.pem -out converted-github-app.pem -nocrypt

- Cliquer sur "Install App" dans le menu de gauche et installer l’application sur les bons référentiels

Dans Jenkins
- Ajouter les credentials de type « GitHub App » dans le bon dossier (éviter l'utilisation de credentials globaux)
- Saisir un ID pour les credentials
- Saisir le App ID pris en note précédemment
- Utiliser le contenu du fichier PEM converti comme clé
- Tester la connexion


**Supprimer les 2 fichiers PEM**

Pour plus d'informations:
> https://github.com/jenkinsci/github-branch-source-plugin/blob/master/docs/github-app.adoc
