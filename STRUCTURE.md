# Organisation du code

```text
DDChill/
├── index.html
├── stats.html
├── team.html
├── programme.html
├── players.html
├── news.html
├── partner.html
├── css/
│   ├── base.css          # Composants et styles communs issus de la V2
│   ├── modern.css        # Navigation, catégories, transitions et sous-pages
│   ├── team.css          # Groupes de l’équipe et compteurs de la bannière
│   ├── stats.css         # Formulaire, indicateurs et listes RavenKoG
│   └── theme.css         # Palette V1, cartes, responsive et accessibilité
├── js/
│   ├── translations.js   # Dictionnaire et traduction de l’accueil
│   ├── home.js           # Répertoire d’accueil, ancien profil, menu, pétales
│   ├── proposals.js      # Formulaire et propositions modérées
│   ├── discord-news.js   # Compteurs et état des annonces (accueil)
│   ├── news-page.js      # Compteurs de la page Actualités
│   ├── discord-auth.js   # Connexion Discord et profil avec niveau modéré
│   ├── kog-stats.js      # Recherche et affichage RavenKoG
│   ├── directory.js      # Répertoire dédié : recherche et filtres
│   ├── modern.js         # Navigation, langues et animations communes
│   └── preferences.js    # Préférence d’animation partagée entre pages
├── assets/
│   ├── hero.webp         # Bannière V2
│   └── favicon.svg       # Icône V1
├── docs/INTEGRATIONS.md
├── tests/check_project.py
├── package.json
├── vercel.json
└── README.md
```

Le thème est appliqué par `css/theme.css` sur toutes les pages. Les classes HTML et identifiants nécessaires aux scripts ont été conservés. Les scripts extraits de l'accueil conservent leur ordre de chargement afin de ne pas casser les dépendances historiques.
