# Delta

Quelques minutes de calcul mental par jour, orienté finance : additions, multiplications, divisions, pourcentages, puissances et intérêts composés, fractions et ratios. La difficulté s’adapte à tes résultats et une série de jours consécutifs te pousse à revenir chaque jour.

![Icône](icon-512.png)

## Contenu du dossier

```
delta/
├── index.html                L’application complète (HTML, CSS et JS dans un seul fichier)
├── manifest.webmanifest      Nom, couleurs et icônes quand l’app est installée
├── sw.js                     Service worker : fonctionnement hors ligne
├── apple-touch-icon.png      Icône de l’iPhone (180 × 180)
├── icon.svg                  Icône source (vectorielle)
├── icon-192.png
├── icon-512.png
├── icon-maskable-512.png     Version avec marges pour Android
├── icon-1024.png             Grand format
├── .nojekyll                 Indique à GitHub Pages de servir les fichiers tels quels
├── LICENSE
└── README.md
```

Tous les fichiers sont à la racine : aucun sous-dossier à recréer sur GitHub.

## Mettre l’app en ligne avec GitHub Pages (gratuit)

1. Crée un nouveau dépôt sur GitHub, par exemple `delta`. Il peut être public ; sur un compte gratuit, GitHub Pages nécessite un dépôt public.
2. Envoie tous les fichiers de ce dossier à la racine du dépôt. Le plus simple : sur la page du dépôt, « Add file » puis « Upload files », et glisse le contenu du dossier (pas le dossier lui‑même). En ligne de commande :

   ```bash
   cd delta
   git init
   git add .
   git commit -m "Première version de Delta"
   git branch -M main
   git remote add origin https://github.com/TON-PSEUDO/delta.git
   git push -u origin main
   ```

3. Dans le dépôt : **Settings → Pages**. Sous « Build and deployment », choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
4. Après une à deux minutes, l’app est disponible à l’adresse `https://TON-PSEUDO.github.io/delta/`.

## L’installer sur l’iPhone

Avant tout, vérifie que l’icône est bien en ligne : ouvre `https://TON-PSEUDO.github.io/delta/apple-touch-icon.png` dans Safari. Tu dois voir l’icône Delta. Si tu obtiens une page 404, le fichier n’a pas été envoyé sur GitHub ou le déploiement n’est pas terminé.


1. Ouvre l’adresse ci‑dessus dans **Safari** (pas Chrome : seul Safari permet l’installation sur iOS).
2. Touche le bouton **Partager** (le carré avec la flèche), puis **Sur l’écran d’accueil**.
3. Valide : l’icône Delta apparaît sur ton écran d’accueil. L’app s’ouvre en plein écran, sans barre d’adresse, et fonctionne même hors ligne après la première ouverture.

## Le rappel quotidien

Dans l’app, ouvre les **Réglages**, choisis une heure, puis touche **Ajouter à l’agenda**. Un fichier `.ics` est créé : ouvre‑le et accepte l’ajout. Ton agenda te notifiera tous les jours à cette heure.

Variante plus intégrée : l’app **Raccourcis** d’iOS, onglet **Automatisation**, « Heure de la journée », action « Ouvrir l’URL » avec l’adresse de ton app.

## Tes données

Tout est stocké localement sur ton téléphone (dans le stockage de Safari). Rien n’est envoyé nulle part. Attention : supprimer l’icône de l’écran d’accueil ou effacer les données de Safari efface aussi ta série et tes statistiques.

## Mettre à jour l’app

Modifie les fichiers, envoie‑les sur GitHub, puis change la valeur de `VERSION` en haut de `sw.js` (par exemple `delta-v3`). À l’ouverture suivante (parfois la deuxième), l’app installée récupère la nouvelle version.

## Tester en local

Le service worker ne fonctionne pas en ouvrant `index.html` directement. Lance un petit serveur :

```bash
cd delta
python3 -m http.server 8000
```

puis ouvre `http://localhost:8000`.
