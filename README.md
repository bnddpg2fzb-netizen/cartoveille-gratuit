# CartoVeille — édition gratuite iPad / iPhone

**Aucun serveur, aucune base de données payante et aucune carte bancaire nécessaire pour cette version.**

## Installation sur GitHub Pages

1. Créer un dépôt GitHub **privé** nommé `cartoveille` (GitHub Pages peut publier un site depuis un dépôt privé selon les droits et l'offre du compte ; si GitHub indique qu'il faut payer pour publier depuis un dépôt privé, créer un dépôt public **uniquement pour ces fichiers d'application**, qui ne contiennent aucune donnée commerciale ni aucun mot de passe). Vérifier les conditions du compte.
2. Dans le dépôt, sélectionner **Add file → Upload files**, puis envoyer le **contenu** du dossier extrait, sans dossier supplémentaire : `index.html`, `app.js`, `style.css`, `manifest.webmanifest`, `service-worker.js`, `icon-180.png`, `icon-192.png`, `icon-512.png`, `README.md`, `.nojekyll`.
3. Valider avec **Commit changes**.
4. Dans le dépôt, aller dans **Settings → Pages**. Sous **Build and deployment**, sélectionner **Deploy from a branch**, puis **main** et **/(root)**. Enregistrer.
5. Attendre l'URL indiquée par GitHub Pages, généralement `https://VOTRE_IDENTIFIANT.github.io/cartoveille/`.
6. Ouvrir l'URL dans **Safari** sur iPad/iPhone, puis **Partager → Sur l'écran d'accueil → Ajouter**.

## Données et confidentialité

Les données sont enregistrées dans `localStorage` sur l'appareil et le navigateur utilisés. Elles ne sont **jamais** envoyées à GitHub Pages. Un iPad et un iPhone ont chacun leur propre base locale. Exporter une sauvegarde JSON dans **Paramètres**, puis l'importer sur l'autre appareil si nécessaire. Les données peuvent être effacées par Safari ou lors de la suppression du site : sauvegardes régulières indispensables.

**Ne jamais mettre de données commerciales, de mots de passe, de clés API ou de sauvegardes JSON dans le dépôt GitHub.** Même si le dépôt est privé, le site GitHub Pages publié est accessible par son URL. L'application ne comporte pas de connexion utilisateur.

## Limites

Cette édition ne collecte pas automatiquement la presse, ne synchronise pas les appareils et ne propose pas de serveur central. L'interface et les données déjà enregistrées peuvent être disponibles hors connexion après une première ouverture HTTPS, mais les liens externes vers les sources et OpenStreetMap nécessitent Internet. L'estimation de prix est une moyenne descriptive de comparables documentés, pas une recommandation commerciale.


## Nouveau : fiches concurrents détaillées
Dans « Entreprises », créez d'abord la fiche d'un concurrent. Dans « Fiches concurrents », ajoutez ensuite des données financières, commerciales, industrielles et de gouvernance, avec leur source, date, périmètre, statut et URL. Les événements déjà saisis dans « Veille » sont présentés dans la chronologie de la fiche lorsqu'ils sont liés à cette entreprise. Les nouvelles informations sont incluses dans les exports/imports JSON. Cette version ne recherche pas automatiquement sur Internet.

Pour mettre à jour GitHub Pages : remplacez les fichiers du dépôt par ceux contenus dans ce ZIP, en conservant `index.html` à la racine. Ne téléversez pas le ZIP lui-même.


## Carte interactive et fiches concurrents (mise à jour)
- Onglet Géographie : carte de France Leaflet/OpenStreetMap, filtre région, repères cliquables et ouverture directe des fiches concurrents.
- Onglet Entreprises : ajouter une entreprise et, si nécessaire, plusieurs établissements avec leurs coordonnées GPS.
- Onglet Fiches concurrents : informations financières, commerciales, industrielles et historique des sources pour chaque entreprise ; implantations rattachées.
- Les repères n'apparaissent que si des coordonnées GPS valides ont été saisies. Aucune position ni information concurrentielle n'est inventée.
- Fond de carte Leaflet et tuiles OpenStreetMap : connexion Internet requise. La version GitHub Pages reste gratuite et les données sont stockées localement sur chaque appareil.
- Mettre à jour GitHub Pages en remplaçant les fichiers existants à la racine du dépôt ; conserver une sauvegarde JSON avant la mise à jour.
