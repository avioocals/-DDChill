# DDChill — V2 intégrée

> Import en cours : la documentation est présente, le code et les ressources de la V2 restent à déposer avant tout déploiement.

Site communautaire DDRaceNetwork. Cette version fusionne le thème sombre violet du premier projet reconstruit avec les pages, fonctionnalités et ressources du ZIP V2 fourni. La V2 est la base fonctionnelle ; le mode local de la V1 ne remplace pas les données partagées.

## Démarrage

Depuis la racine du projet :

```bash
python -m http.server 8000
```

Ouvrir `http://localhost:8000`. Un serveur statique permet de consulter les pages. Pour tester les statistiques RavenKoG avec les véritables données, utiliser un environnement Vercel qui applique la réécriture définie dans `vercel.json` (par exemple `vercel dev` avec le projet autorisé). La connexion Discord exige aussi que l'URL de retour soit autorisée dans Supabase. Les scripts appellent les services publics configurés dans la V2 ; un test de soumission ou de profil peut modifier les données réelles. Utiliser un environnement de test pour ces opérations.

## Interfaces

- `index.html` : accueil, bannière, catégories, aperçu statistiques, programme, partenaire, Discord, équipe, actualités, propositions et profils.
- `stats.html` : recherche RavenKoG, points, rang, maps, sept difficultés, derniers finishes et progression des points.
- `players.html` : recherche de joueurs et filtres par niveau.
- `team.html` : fondateurs et co-fondateurs.
- `programme.html` : activités de la communauté.
- `news.html` : compteurs Discord.
- `partner.html` : Nova Client.

## Architecture

Voir [STRUCTURE.md](STRUCTURE.md) pour les fichiers et [docs/INTEGRATIONS.md](docs/INTEGRATIONS.md) pour les dépendances externes et les limites. Les scripts de l'accueil restent des scripts classiques, chargés dans un ordre volontaire : traduction, accueil, propositions, compteurs, stats, auth, navigation et préférences. Ils partagent quelques fonctions historiques de la V2. Ne pas ajouter `type="module"` sans refactoriser ces dépendances.

## Vérifications

```bash
python tests/check_project.py
```

Ce contrôle exige Python 3 et Node.js. Il vérifie les sept pages, les liens et ancres internes, les identifiants uniques, et la syntaxe des dix scripts. Les contrôles ont réussi. La navigation Chromium a été bloquée par l'environnement de vérification : rendu visuel et parcours interactifs non validés. Aucun appel d'écriture vers les services en ligne, aucun déploiement, ni modification de base de données n'a été effectué.
