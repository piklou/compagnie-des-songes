# Site Hugo Corrigé - La Compagnie des Songes

Ce dépôt contient une version corrigée du site web de La Compagnie des Songes, avec les modifications suivantes :

## Corrections apportées

1. **Menu de navigation mis à jour** :
   - "Nos Univers" renommé en "Nos Créations"
   - "Notre Essence" renommé en "Notre Univers"

2. **Structure d'images organisée** :
   - `/static/images/spectacles/` - Images pour les spectacles
   - `/static/images/projets/` - Images pour les projets
   - `/static/images/equipe/` - Photos des membres de l'équipe
   - `/static/images/partenaires/` - Logos des partenaires
   - `/static/images/logo_cds.png` - Logo principal

3. **Images génériques** :
   - Des images génériques ont été créées pour tous les contenus
   - Ces images sont à remplacer par vos propres visuels

## Comment utiliser cette archive

### 1. Remplacer les images

Remplacez les images génériques par vos propres images en conservant les mêmes noms de fichiers :

- **Spectacles** : `/static/images/spectacles/le_etre.jpg`, `/static/images/spectacles/les_chamanos.jpg`
- **Projets** : `/static/images/projets/lattrape-reves.jpg`, `/static/images/projets/la_yourte_lamuse.jpg`
- **Équipe** : `/static/images/equipe/membre_1.jpg`, `/static/images/equipe/membre_2.jpg`, `/static/images/equipe/membre_3.jpg`
- **Partenaires** : Tous les logos dans `/static/images/partenaires/`
- **Logo principal** : `/static/images/logo_cds.png`

### 2. Modifier les contenus

Les contenus sont gérés via Netlify CMS. Connectez-vous à l'interface d'administration à l'adresse :
`https://votre-site.netlify.app/admin/`

Vous pourrez y modifier :
- Les textes de présentation
- Les informations sur les spectacles et projets
- Les détails des membres de l'équipe
- Les informations des partenaires

### 3. Déployer sur Netlify

Pour déployer cette version corrigée :

1. Téléversez tous les fichiers dans votre dépôt GitHub
2. Connectez-vous à votre tableau de bord Netlify
3. Si nécessaire, déclenchez un nouveau déploiement

## Structure des données

### Spectacles et projets (`content/nos-univers.md`)

```yaml
---
title: "Nos Créations : Projets & Spectacles"
spectacles:
  - titre: Le Être
    image: images/spectacles/le_etre.jpg
    description: Description du spectacle...
  - titre: Les Chamanos
    image: images/spectacles/les_chamanos.jpg
    description: Description du spectacle...
projets:
  - titre: L'Attrape-Rêves
    image: images/projets/lattrape-reves.jpg
    description: Description du projet...
  - titre: La Yourte l'Amuse
    image: images/projets/la_yourte_lamuse.jpg
    description: Description du projet...
---
```

### Approche pédagogique (`content/notre-essence.md`)

```yaml
---
title: "Notre Univers"
approche_pedagogique:
  - titre: Titre de l'approche
    image: images/approche_1.jpg
    description: Description de l'approche...
---
```

### Équipe (`content/equipe.md`)

```yaml
---
title: "L'Équipe"
membres:
  - nom: Nom du membre
    role: Rôle dans la compagnie
    photo: images/equipe/membre_1.jpg
    bio: Biographie du membre...
---
```

### Partenaires (`data/partenaires.yaml`)

```yaml
- nom: "Nom du partenaire"
  logo: "images/partenaires/logo_partenaire.png"
  url: "https://site-du-partenaire.fr"
```

## Besoin d'aide ?

Si vous avez des questions ou rencontrez des difficultés, n'hésitez pas à contacter votre développeur.
