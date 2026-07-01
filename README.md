# HerdTech

## Description

HerdTech est une plateforme de suivi agricole conçue en HTML, CSS et Tailwind CSS. Elle propose un tableau de bord de gestion de ferme avec des pages dédiées au cheptel, au stockage, au suivi des animaux, aux tâches et aux notifications.

L'objectif est de fournir une interface moderne et responsive pour les gestionnaires agricoles, avec des éléments graphiques soignés et une navigation claire.

## Technologies utilisées

- HTML5
- CSS3
- Tailwind CSS 4.3.1
- SVG pour les icônes et graphiques vectoriels
- Architecture de pages statiques

## Structure du projet

- `index.html` : page d'accueil / tableau de bord principal
- `src/pages/carte/carte.html` : page de la carte de la ferme
- `src/pages/cheptel/cheptel.html` : page de gestion du cheptel
- `src/pages/stockage/stockage.html` : page de gestion du stockage
- `src/pages/suivi/suivi.html` : page de suivi du bétail
- `src/pages/taches/taches.html` : page de tâches agricoles
- `src/pages/notifications/notifications.html` : page de notifications
- `src/pages/login/login.html` : page de connexion
- `src/pages/signup/signup.html` : page d'inscription
- `src/styles/input/input.css` : source Tailwind CSS
- `src/styles/output/output.css` : fichier CSS généré
- `assets/icon/` : icônes SVG utilisées pour la navigation et l'interface

## Objectif du projet

Le projet vise à offrir une interface de suivi agricole adaptée aux besoins d'un gestionnaire de ferme :

- visualiser le cheptel et sa gestion
- suivre le stockage des céréales et aliments
- gérer les tâches quotidiennes
- recevoir et consulter des notifications
- appliquer des styles responsive sur mobile et desktop

## Utilisation de Tailwind CSS

Tailwind CSS est utilisé pour styliser rapidement les composants avec des classes utilitaires. Cela permet de créer :

- des grilles responsives (`grid`, `grid-cols-7`, `md:grid-cols-2`)
- des cartes et sections arrondies (`rounded-lg`, `shadow-lg`)
- des boutons et interactions (`hover:scale-105`, `transition-all`, `duration-300`)
- des thèmes clairs et un design cohérent

### Compilation Tailwind

Même si `package.json` contient Tailwind dans les dépendances, vous pouvez générer le CSS avec la commande CLI :

```bash
npm install
npx tailwindcss -i ./src/styles/input/input.css -o ./src/styles/output/output.css --watch
```

## Comprendre le format SVG et sa personnalisation

Le format SVG (Scalable Vector Graphics) est un format vectoriel idéal pour les icônes et logos car il reste net quelle que soit la taille.

### SVG dans ce projet

- Le logo principal de la page d'accueil est un SVG inline dans `index.html`.
- Les icônes de navigation sont souvent des fichiers SVG dans `assets/icon/` affichés avec `<img src="..." />`.
- Certains SVG utilisent `fill="currentColor"`, ce qui permet de les colorer avec la couleur du texte ou des classes Tailwind.

### Pourquoi utiliser SVG ?

- scalable sans perte de qualité
- fichier léger pour des icônes
- facile à styliser avec CSS
- modifiable directement depuis le code HTML

### Personnaliser un SVG

1. `viewBox`: définit le canevas de dessin du SVG.
2. `width` / `height`: contrôle la taille finale.
3. `fill` et `stroke`: modifient les couleurs de remplissage et du contour.
4. `currentColor`: laisse l'icône hériter de la couleur du texte.

Exemple d'icône SVG inline :

```html
<svg xmlns="http://www.w3.org/2000/svg" width="35" height="35" fill="currentColor" viewBox="0 0 16 16">
  <path d="..." />
</svg>
```

### Styliser un SVG avec Tailwind

Pour appliquer des couleurs Tailwind à un SVG inline :

```html
<svg class="text-green-600" fill="currentColor" viewBox="0 0 16 16">
  <path d="..." />
</svg>
```

Pour un SVG utilisé via `<img>`, vous pouvez remplacer le fichier ou utiliser une version inline si vous avez besoin de le colorer dynamiquement.

### Modifier un fichier SVG externe

Un fichier externe `.svg` contient des balises similaires à ce qui est écrit inline. Par exemple :

- `path` pour les formes
- `circle`, `rect`, `line` pour les éléments de dessin
- `transform` pour la rotation et le positionnement

Il suffit d'ouvrir le fichier dans un éditeur de texte et de changer les valeurs `fill`, `stroke` ou `viewBox`.

## Conseils de personnalisation

- Préférez `fill="currentColor"` quand vous voulez que l'icône suive la couleur du texte.
- Ajoutez des classes Tailwind comme `text-white`, `text-gray-700`, `hover:text-green-600`.
- Utilisez des `group` et `group-hover:` pour des effets lors du survol.
- Pour un rendu responsive, adaptez `width`, `height` et `viewBox`.

## Conclusion

HerdTech est construit comme une application statique moderne, basée sur HTML/CSS et une architecture de pages claires. Le recours aux SVG renforce la qualité visuelle du projet et permet des personnalisations flexibles grâce à Tailwind CSS.
