# CartoVeille — version 1.0.0

Application PWA statique, en français, pour la veille du cartonnage. Le dossier peut être publié tel quel à la racine d'un dépôt GitHub Pages ou dans un dossier de projet Pages. Aucun serveur personnel, compte payant, clé API ni carte bancaire n'est requis pour son fonctionnement de base.

## Fichiers

- `index.html`, `style.css`, `app.js` : interface et logique applicative.
- `manifest.webmanifest`, `icon.svg`, `sw.js` : installation sur l'écran d'accueil et cache des fichiers de l'application.
- `vendor/` : Leaflet 1.9.4 et sa licence BSD-2-Clause. Les tuiles du fond de carte sont chargées depuis OpenStreetMap lorsque l'appareil est connecté.

Publier **toute l'arborescence** sans modifier les chemins. Ne publiez jamais un export JSON contenant des données confidentielles dans un dépôt public.

## Mise en ligne sur GitHub Pages

1. Connectez-vous à GitHub depuis Safari sur iPad ou depuis un ordinateur. Créez un dépôt, par exemple `cartoveille`, de préférence public si vous utilisez l'offre Pages gratuite. Ne chargez que les fichiers du dossier `CartoVeille`, jamais vos sauvegardes.
2. Décompressez l'archive. Transférez les fichiers dans le dépôt en conservant les sous-dossiers `vendor/` et `vendor/images/`. L'interface GitHub « Add file → Upload files » accepte des fichiers ; sur iPad, si elle ne conserve pas l'arborescence, créez les dossiers dans le dépôt puis transférez leur contenu séparément. Pour une opération plus simple, un ordinateur peut servir **une seule fois** au transfert : il n'a ensuite pas besoin de rester allumé. L'archive ZIP elle-même ne peut pas être publiée telle quelle par Pages.
3. Dans le dépôt : **Settings → Pages → Build and deployment → Deploy from a branch**. Sélectionnez la branche principale et le dossier `/ (root)`, puis enregistrez. Attendez que GitHub affiche l'URL publiée, normalement `https://<identifiant>.github.io/cartoveille/`.
4. Ouvrez l'URL : vérifiez le tableau de bord, la carte et l'absence d'erreurs visibles. En cas de page 404, contrôlez la présence de `index.html` à la racine et la configuration Pages.

GitHub peut faire évoluer ses menus ou les conditions de Pages : suivez l'interface actuelle en cas d'écart. Aucun accès à votre compte GitHub n'est fourni à cette livraison ; la publication réelle reste à effectuer dans votre dépôt.

## Installer sur iPhone ou iPad

1. Ouvrez l'URL GitHub Pages **dans Safari**, avec une connexion Internet pour le premier chargement.
2. Touchez **Partager → Sur l'écran d'accueil → Ajouter**. Lancez CartoVeille depuis son icône.
3. La carte utilise des tuiles en ligne. Hors connexion, son fond peut être absent même si les repères et les fiches déjà enregistrés restent consultables. Le géocodage exige également Internet.
4. Sur iPhone et iPad, chaque installation possède son propre stockage. Pour déplacer vos données, utilisez **Paramètres → Exporter JSON**, conservez le fichier dans Fichiers/iCloud Drive, puis **Importer JSON** sur l'autre appareil.

## Utilisation

- **Entreprises et concurrents** : créez une raison sociale, distinguez les informations du groupe de celles de la filiale et indiquez la source et l'exercice des données financières.
- **Fiche concurrent** : ajoutez séparément chaque usine ou siège. Touchez « Voir / localiser », puis « Rechercher la localisation ». Vérifiez la proposition et Google Maps avant « Confirmer cette position ». Une saisie manuelle des coordonnées est également possible dans « Modifier ».
- **Carte** : zoomez au doigt et filtrez par nom, type de site, groupe ou région/département. Le cercle vert désigne une usine, le carré bleu un siège. Touchez un repère, puis « Fiche concurrent ». Seuls les sites avec coordonnées confirmées s'affichent.
- **Veille** : ajoutez manuellement des faits avec date, URL, fiabilité et qualification « Fait publié », « Analyse » ou « Hypothèse » ; reliez-les à l'entreprise et au site si possible.
- **Prix du marché** : saisissez exclusivement des prix réels, leur statut, unité, date, quantité, caractéristiques et justificatif. Les données privées restent locales.
- **Conseil Prix** : entrez produit et quantité. L'application sélectionne les prix de même type, unité et devise EUR, puis signale les écarts techniques, logistiques, temporels et de volume. Elle affiche la plage des prix utilisables et une médiane basse comme cible uniquement avec au moins deux références proches, dont une sans écart. Le seuil de marge utilise les coûts saisis : `(coût de production + transport) / (1 − marge cible)`. Aucun indice d'actualisation ou ajustement de volume fictif n'est appliqué. La marge estimée est calculée au prix cible si les coûts sont renseignés.
- **Alertes** : règles locales appliquées aux actualités que vous avez saisies. Les notifications et la recherche automatique ne sont pas actives.
- **Recherche** : recherche textuelle transversale dans les fiches enregistrées.
- **Paramètres** : devis gagnés/perdus et sauvegardes.

## Sauvegarde, restauration, mise à jour

1. Avant chaque mise à jour importante, choisissez **Paramètres → Exporter JSON**. Vérifiez que le fichier a été enregistré dans Fichiers ou iCloud Drive. Répétez cette sauvegarde régulièrement : aucune sauvegarde automatique hors de l'appareil n'est effectuée.
2. Remplacez les fichiers publics du dépôt en conservant **la même URL et le même nom de dépôt**. Les données IndexedDB restent normalement sur le même appareil et la même origine ; le service worker installe les nouveaux fichiers. Fermez puis rouvrez l'application. Si nécessaire, actualisez dans Safari.
3. En cas de perte ou lors d'un changement d'appareil, choisissez **Paramètres → Importer JSON** et sélectionnez la sauvegarde. L'import vérifie le format et la version ; il **remplace toutes les données locales** après confirmation. Effectuez donc un export avant l'import. Version de schéma acceptée : `1`.
4. **Exporter CSV** crée six fichiers de tables distincts. Sur Safari, des téléchargements multiples peuvent nécessiter une autorisation du navigateur. Le JSON est le format recommandé pour restaurer les liens entre fiches.
5. Évitez « Effacer l'historique et les données de sites web » dans Safari pour ce site : cela peut supprimer IndexedDB. Ne mettez pas de données privées dans GitHub, dans les captures publiques ou dans des tickets.

## Fonctionnalités et limites réellement livrées

| Fonction | V1 |
| --- | --- |
| PWA française, menu et interface tactile | Oui ; les fichiers de l'application sont mis en cache après un chargement en ligne |
| Fiches d'entreprises et établissements, édition, archivage, fusion | Oui ; la fusion transfère sites, prix, actualités et alertes, puis supprime la fiche source |
| Carte intégrée avec repères propres à chaque établissement | Oui ; fond OpenStreetMap tributaire d'Internet et de la disponibilité du service |
| Géocodage | Recherche ponctuelle via Géoplateforme, validation manuelle avant enregistrement ; une commune seule ne localise pas une usine |
| Veille et alertes | Saisie et correspondances locales uniquement |
| Base de prix, devis et Conseil Prix | Oui ; recommandation prudente fondée sur comparables présents, sans modèle prédictif ni ajustements chiffrés inventés |
| Recherche transversale, export JSON/CSV, import JSON | Oui |
| Répertoire sectoriel exhaustif et données concurrentielles préchargées | Non ; la base commence vide afin de ne pas introduire de données ou positions non vérifiées |
| Collecte quotidienne, synthèses automatiques, Exa/Firecrawl, notifications | Non ; infrastructure serveur requise |
| Synchronisation iPhone–iPad, comptes utilisateur, sauvegarde distante | Non ; infrastructure sécurisée requise |
| Téléchargement et indexation automatique des documents | Non ; conservation de leurs références et URL uniquement |

## Évolutions proposées

1. **V2 — collecte et base centrale** : backend privé, comptes et rôles, base relationnelle, sauvegardes chiffrées, synchronisation, jobs planifiés, files de collecte RSS/Exa/Firecrawl, qualification humaine et déduplication, synthèses et alertes. Évaluer les contrats et quotas des sources avant intégration ; ne jamais intégrer de secrets dans JavaScript public.
2. **V3 — modèle tarifaire** : normalisation technique des produits et des unités, index matières et transport documentés, comparaison contrôlée par volume/date/zone, historique devis et résultats, validation statistique et suivi des erreurs. Définir la gouvernance et la confidentialité des prix concurrents avant centralisation.

## Vérifications effectuées pour cette livraison

- Analyse syntaxique de `app.js` avec Node.
- Essai automatisé du démarrage IndexedDB, création d'entreprise, création d'établissement, proposition de géocodage simulée puis confirmation, création de repère Leaflet simulé, saisie de prix, refus d'une cible tarifaire avec une seule référence, navigation et conservation locale des fiches.
- Le service réel de géocodage, le chargement des tuiles OpenStreetMap et Safari iPhone/iPad ne sont **pas** vérifiés en conditions réelles dans cet environnement. Les tests ont utilisé une réponse géographique simulée et un moteur de carte simulé. La première publication doit inclure une vérification sur les appareils cibles.

Sources techniques : [service officiel de géocodage Géoplateforme](https://cartes.gouv.fr/aide/fr/guides-utilisateur/utiliser-les-services-de-la-geoplateforme/geocodage/), [Leaflet](https://leafletjs.com/), [OpenStreetMap](https://www.openstreetmap.org/copyright).
