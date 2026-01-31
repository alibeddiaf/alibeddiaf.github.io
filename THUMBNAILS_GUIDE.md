# Guide: Adding Thumbnails and Materials Pages

## 📸 Structure des Fichiers

Votre repository devrait avoir cette structure :

```
votre-username.github.io/
├── index.html
├── style.css
├── script.js
├── README.md
├── images/
│   ├── photo.jpg
│   └── publications/
│       ├── pbr-fluids.png
│       ├── splat-raytracing.png
│       ├── texture-mapping.png
│       └── ... (autres vignettes)
└── materials/
    ├── pbr-fluids.html
    ├── splat-raytracing-2015.html
    └── ... (autres pages de matériaux)
```

## 🖼️ Étape 1 : Ajouter les Vignettes de Publications

### Créer les dossiers
1. Dans votre repo, créez le dossier `images/publications/`
2. Uploadez une image pour chaque publication

### Recommandations pour les images
- **Format** : PNG ou JPG
- **Taille** : 400x300 pixels (ratio 4:3)
- **Contenu** : 
  - Screenshot de votre article
  - Figure principale de votre papier
  - Graphique représentatif
  - Résultat visuel de votre recherche

### Nommage des fichiers
```
pbr-fluids.png          → Pour l'article sur les fluides
splat-raytracing.png    → Pour l'article sur le ray tracing
texture-mapping.png     → Pour l'article sur le texture mapping
etc.
```

## 📝 Étape 2 : Mettre à Jour index.html

Pour chaque publication, remplacez cette structure :

### AVANT (avec icône simple) :
```html
<article class="publication-item">
    <div class="pub-thumbnail">
        <div class="pub-icon">C</div>
    </div>
    <div class="pub-content">
        <h4 class="pub-title">Titre de la publication</h4>
        <p class="pub-authors"><strong>A. Beddiaf</strong>, Co-auteurs</p>
        <p class="pub-venue"><em>Conférence</em>, Lieu, Année</p>
    </div>
</article>
```

### APRÈS (avec vignette cliquable) :
```html
<article class="publication-item">
    <a href="materials/nom-de-la-page.html" class="pub-thumbnail-link">
        <div class="pub-thumbnail">
            <img src="images/publications/votre-image.png" alt="Titre" class="pub-image">
            <div class="pub-overlay">
                <span class="view-materials">View Materials</span>
            </div>
        </div>
    </a>
    <div class="pub-content">
        <h4 class="pub-title">
            <a href="materials/nom-de-la-page.html" class="pub-title-link">Titre de la publication</a>
        </h4>
        <p class="pub-authors"><strong>A. Beddiaf</strong>, Co-auteurs</p>
        <p class="pub-venue"><em>Conférence</em>, Lieu, Année</p>
        <div class="pub-links">
            <a href="materials/nom-de-la-page.html" class="pub-link">Materials</a>
            <a href="fichier.pdf" class="pub-link">PDF</a>
            <a href="https://doi.org/..." class="pub-link">DOI</a>
        </div>
    </div>
</article>
```

## 📄 Étape 3 : Créer les Pages Materials

### Option A : Copier le template
1. Utilisez `pbr-fluids.html` comme template
2. Créez une copie pour chaque publication
3. Modifiez le contenu

### Option B : Créer manuellement
Chaque page materials doit contenir :
- Titre complet de la publication
- Auteurs et venue
- Abstract
- Liens de téléchargement (PDF, slides, code, etc.)
- Résultats visuels
- Citation BibTeX
- Liens externes (publisher, DOI, etc.)

### Structure d'une page materials :
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Titre - Materials</title>
    <link rel="stylesheet" href="../style.css">
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">...</nav>
    
    <!-- Hero avec titre -->
    <section class="materials-hero">...</section>
    
    <!-- Contenu -->
    <section class="materials-content">
        <!-- Abstract -->
        <!-- Downloads -->
        <!-- Visual Results -->
        <!-- BibTeX -->
        <!-- Links -->
    </section>
    
    <!-- Footer -->
    <footer class="footer">...</footer>
</body>
</html>
```

## 🎨 Effets Visuels

### Hover sur la vignette
Quand on survole la vignette :
- L'image zoom légèrement (scale 1.1)
- Un overlay apparaît avec "View Materials"
- L'overlay a un fond doré semi-transparent

### Liens cliquables
- La vignette entière est cliquable
- Le titre est aussi cliquable
- Boutons "Materials", "PDF", "DOI" sous chaque publication

## 📋 Checklist par Publication

Pour chaque publication, assurez-vous d'avoir :
- [ ] Image de vignette uploadée dans `images/publications/`
- [ ] HTML mis à jour avec le lien vers la vignette
- [ ] Page materials créée dans `materials/`
- [ ] Liens vers PDF, DOI, etc. (si disponibles)
- [ ] Abstract ajouté sur la page materials
- [ ] Citation BibTeX correcte

## 🔧 Personnalisation Avancée

### Changer la taille des vignettes
Dans `style.css`, modifiez :
```css
.pub-thumbnail {
    width: 200px;  /* Largeur */
    height: 150px; /* Hauteur */
}
```

### Changer la couleur de l'overlay
Dans `style.css` :
```css
.pub-overlay {
    background: rgba(199, 149, 109, 0.95); /* Changez cette couleur */
}
```

### Ajouter d'autres types de liens
Dans le HTML, ajoutez dans `.pub-links` :
```html
<a href="lien-vers-video" class="pub-link">Video</a>
<a href="lien-vers-code" class="pub-link">Code</a>
<a href="lien-vers-slides" class="pub-link">Slides</a>
```

## 🚀 Exemple Rapide

Pour ajouter une vignette à votre première publication :

1. **Prenez un screenshot** de votre article ou créez une image représentative
2. **Uploadez-la** dans `images/publications/pbr-fluids.png`
3. **Le HTML est déjà configuré** dans les fichiers que je vous ai donnés !
4. **Créez la page materials** en copiant `pbr-fluids.html` dans un dossier `materials/`

## 💡 Conseils

- **Images haute qualité** : Utilisez des images nettes et professionnelles
- **Cohérence visuelle** : Gardez le même ratio pour toutes les vignettes
- **Optimisation** : Compressez vos images (< 200KB par image)
- **Accessibilité** : Ajoutez des attributs `alt` descriptifs
- **Progressive enhancement** : Si une image ne charge pas, le texte reste lisible

## ❓ FAQ

**Q : Puis-je avoir des publications sans vignette ?**
A : Oui, gardez simplement l'ancienne structure avec `<div class="pub-icon">C</div>`

**Q : Comment créer une vignette à partir de mon PDF ?**
A : 
1. Ouvrez votre PDF
2. Prenez un screenshot de la première page ou d'une figure
3. Recadrez à 400x300 pixels
4. Sauvegardez en PNG

**Q : Les pages materials sont-elles obligatoires ?**
A : Non, vous pouvez lier directement au PDF si vous préférez :
```html
<a href="papers/mon-article.pdf" class="pub-thumbnail-link">
```

**Q : Comment ajouter une vidéo YouTube ?**
A : Dans votre page materials, ajoutez :
```html
<div class="video-container">
    <iframe width="560" height="315" 
            src="https://www.youtube.com/embed/VIDEO_ID" 
            frameborder="0" allowfullscreen>
    </iframe>
</div>
```

---

**Besoin d'aide ?** Consultez le fichier `pbr-fluids.html` pour un exemple complet !
