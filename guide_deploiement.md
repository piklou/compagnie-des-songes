# Déploiement de Hugo avec Netlify - Guide technique

Ce document explique comment déployer votre site Hugo sur Netlify et configurer votre nom de domaine.

## Prérequis

1. Un compte GitHub (pour héberger le code source)
2. Un compte Netlify (pour le déploiement)

## Étapes de déploiement

### 1. Création d'un dépôt GitHub

1. Créez un compte sur [GitHub](https://github.com/) si vous n'en avez pas déjà un
2. Créez un nouveau dépôt (repository) nommé "compagnie-des-songes"
3. Suivez les instructions pour pousser votre code vers ce dépôt :
   ```bash
   git init
   git add .
   git commit -m "Premier commit"
   git branch -M main
   git remote add origin https://github.com/VOTRE-NOM-UTILISATEUR/compagnie-des-songes.git
   git push -u origin main
   ```

### 2. Déploiement sur Netlify

1. Créez un compte sur [Netlify](https://www.netlify.com/) si vous n'en avez pas déjà un
2. Cliquez sur "New site from Git"
3. Choisissez GitHub comme fournisseur de Git
4. Autorisez Netlify à accéder à vos dépôts GitHub
5. Sélectionnez le dépôt "compagnie-des-songes"
6. Dans les paramètres de build, configurez :
   - Build command: `hugo --gc --minify`
   - Publish directory: `public`
   - Variables d'environnement : ajoutez `HUGO_VERSION` avec la valeur `0.92.2`
7. Cliquez sur "Deploy site"

### 3. Configuration de l'authentification Netlify Identity

1. Dans le tableau de bord de votre site Netlify, allez dans "Site settings" > "Identity"
2. Cliquez sur "Enable Identity"
3. Sous "Registration preferences", choisissez "Invite only"
4. Sous "External providers", vous pouvez activer la connexion via Google, GitHub, etc. (optionnel)
5. Sous "Services" > "Git Gateway", cliquez sur "Enable Git Gateway"
6. Allez dans l'onglet "Identity" de votre tableau de bord
7. Cliquez sur "Invite users" et entrez votre adresse email
8. Vous recevrez un email d'invitation, suivez le lien pour définir votre mot de passe

### 4. Configuration de votre nom de domaine

1. Dans le tableau de bord de votre site Netlify, allez dans "Site settings" > "Domain management"
2. Cliquez sur "Add custom domain"
3. Entrez votre domaine "compagniedessonges.fr" et cliquez sur "Verify"
4. Choisissez "Yes, add domain"
5. Vous avez deux options pour configurer votre domaine :
   
   **Option 1 : Utiliser les serveurs DNS de Netlify (recommandé)**
   - Cliquez sur "Set up Netlify DNS"
   - Suivez les instructions pour ajouter les serveurs de noms (nameservers) de Netlify chez votre registrar (OVH)
   
   **Option 2 : Garder les DNS chez OVH**
   - Créez un enregistrement CNAME chez OVH pointant vers votre nom de domaine Netlify
   - Créez un enregistrement A pour l'apex du domaine (@ ou domaine nu) pointant vers l'IP de Netlify

6. Attendez que la propagation DNS soit terminée (cela peut prendre jusqu'à 48 heures)
7. Activez HTTPS en cliquant sur "Verify DNS configuration" puis "Let's Encrypt certificate"

## Mise à jour du site

Une fois le site déployé, toute modification effectuée via l'interface d'administration Netlify CMS sera automatiquement publiée sur votre site.

Si vous souhaitez mettre à jour le code du site lui-même :

1. Effectuez vos modifications localement
2. Poussez les changements vers GitHub :
   ```bash
   git add .
   git commit -m "Description des modifications"
   git push
   ```
3. Netlify détectera automatiquement les changements et redéploiera votre site

## Ressources utiles

- [Documentation Hugo](https://gohugo.io/documentation/)
- [Documentation Netlify](https://docs.netlify.com/)
- [Documentation Netlify CMS](https://www.netlifycms.org/docs/intro/)
