# Brick Breaker

Casse-briques arcade en 2D (HTML5 / Construct 2).

## Description
Renvoie la balle avec la raquette pour détruire toutes les briques du niveau. Enchaîne les rebonds, attrape les bonus qui tombent et vide l'écran avant de perdre toutes les vies.

## Contrôles
- **Souris / Tactile** : déplacer la raquette (glisser horizontalement)
- **Clic / Tap** : lancer la balle au départ, relancer après une vie perdue
- **P** ou bouton Pause : mettre en pause / reprendre
- **M** : couper / remettre le son et la musique
- **F** : plein écran (si disponible)

## Stack
- `c2runtime.js` + `data.js` (Construct 2), `jquery-2.1.1.min.js`
- `images/` : sprites du jeu
- `media/` : effets sonores

> Nettoyage : SDK pub GameDistribution et trackers supprimés, remplacés par un stub local `window.gdsdk` (aucun appel externe). Fichiers `offlineClient.js` et `loading-logo.png` inutiles retirés, manifest/icônes morts supprimés de `index.html`.
