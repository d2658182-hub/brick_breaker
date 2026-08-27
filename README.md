# Brick Breaker — Nettoyé

Jeu 2D de casse-briques (HTML5 / Construct 2).

## Moteur détecté
- **Construct 2** (`c2runtime.js`, `data.js`, jQuery 2.1.1)
- Canvas WebGL/2D, rendu plein écran responsif
- Boucle interne Construct 2 (`cr_createRuntime`)

## Architecture générale
- `index.html` — entrée, `<canvas id="c2canvas">`, balises meta viewport
- `c2runtime.js` — moteur Construct 2 (minifié)
- `data.js` — données du projet (layouts, objets, images, sons)
- `jquery-2.1.1.min.js` — requis par Construct 2
- `images/` — sprites (sheet0)
- `media/` — sons (ogg)

## Nettoyage effectué
- Retiré : SDK publicitaire GameDistribution (`html5.api.gamedistribution.com/main.min.js`)
  et tous ses trackers (gamedock, atom.dmp, google analytics, headerlift, improvedigital…)
- Injecté **stub local `window.gdsdk`** dans `c2runtime.js` qui émet les events
  `SDK_READY` + `SDK_GAME_START` (le jeu démarre sans le CDN de pub)
- `viewport` déjà correct (`user-scalable=no`, fond `#000`)
- Copie physique de tous les assets (aucun symlink)

## Test
- Chargement OK, 0 erreur JS, 0 ressource manquante (Xvfb Chromium)
- Desktop 1280×720 et mobile portrait 390×844 : canvas actif, pas de white bar / scroll horizontal
- Les 6 fichiers audio absents du serveur d'origine (shot/speedball/startgame/time/totalscore/)
  sont gérés en silence par Construct 2 (aucun impact au jeu)
