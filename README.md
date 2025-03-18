# Adaboards

Ce projet a pour objectif de servir de **fil rouge** pour préparer la certification **RNCP 7**. Il s'agit de réaliser, sous la forme d'une application fullstack, un clone de [Trello](http://trello.com/).

Nous te proposons une **stack suggérée pour le front** :

- ⚡️ Vite : pour lancer et build le site
- ⚛️ React : comme framework front-end de composants
- 🎨 TailwindCSS : pour faciliter l'utilisation du css avec React
- 🟦 TypeScript :
- 🔗 React Query (useQuery) : Pour gérer les requêtes API
- 📡 OpenAPI Fetch : Pour typer les requêtes API à partir de la documentation swagger

> **💡 Remarque :** Tu es libre d'utiliser ou d'ajouter d'autres bibliothèques et frameworks si tu es plus à l'aise avec

---

## 🐙 Utilisation de Git

Une fois ton projet initialisé, crée une branche par jour `day-1`, `day-2`, etc.

Ensuite tu peux créer une branche à partir de la branche du jour pour développer une ou un petit groupe de fonctionnalités, par exemple `day-1/implementation_design`.

Une fois que tu as fini (ou suffisament avancé) la fonctionnalité, tu peux faire une PR (`day-1` ⬅️ `day-1/implementation_design`), ce qui te permet d'avoir une review de l'encadrant⋅e sur ton code.

Si tout es bon tu peux merger ta branche sur la branche du jour.

À la fin de la journée on fait une PR `main` ⬅️ `day-1` afin de permettre à l'encadrant⋅e de review le lendemain matin le travail qui a été fait et vérifier les objectifs qui ont été remplis.

Et le lendemain on recommence :

```
git checkout main
git checkout -b day-2 && git push -u origin day-2
git checkout -b day-2/login && git push -u origin day-2/login
```

## 🚀 Déroulement du projet

Le projet est découpé en **4 journées**, chacune avec un ensemble d'objectifs.  
Ton objectif est de réaliser un maximum d'objectifs chaque jour pour développer les compétences attendues au **RNCP 7**.

- ✅ **Objectifs requis** : à réaliser en priorité.
- ⭐️ **Objectifs bonus** : pour aller plus loin, selon ton avancement.

> **ℹ️ Important :** Si certains objectifs requis ne sont pas atteints, **prends le temps d'y revenir** après cette semaine.

---

## ⚙️ Installation initiale

Pour commencer, crée un projet Vite :

```bash
pnpm create vite # Choisis "react" et "typescript"
```

Ajoute ensuite les autres dépendances dont tu as besoin pour réaliser le projet (tailwind, react-query, etc.).

---

## 📅 Jour 1 : Implémentation du front et utilisation de l'API (sans gestion des utilisateur·ices)

Cette journée porte sur le front-end du projet. Ton but est d'intégrer le design figma (fourni ci-dessous), le plus fidèlement possible. Ensuite, de récupérer certaines données depuis l'API (swagger fourni ci-dessous) pour le moment, sans prendre en compte le système d'utilisateur⋅ice.

### 📁 Ressources utiles

> - [🎨 Figma](https://www.figma.com/community/file/1483932077241643794) : design à implémenter
> - [📚 Swagger](TODO) : liste des routes API disponibles

### 🎯 Objectifs du jour

#### ✅ Objectifs principaux

- [ ] Implémenter le design de la **landing page**
- [ ] Implémenter le design de la **page d'accueil (home)**
- [ ] Implémenter le design de la **page d'une board**
- [ ] Charger les boards sur la home via `GET /boards` (affichage du **titre** uniquement)
- [ ] Gérer la navigation vers une board depuis la home (au clic)
- [ ] Ajouter une nouvelle board via `POST /boards`
- [ ] Supprimer une board via `DELETE /boards`
- [ ] Implémenter le design de la **page de connexion (login)**
- [ ] Implémenter le design de la **page d'inscription (signup)**
- [ ] Vérifier l’**accessibilité** et les **performances** (objectif : **100% Lighthouse**)
- [ ] Adapter le design pour qu'il soit **responsive** (min-width: **320px**)
- [ ] Ajoute une nouvelle tâche au clic sur le bouton (+) avec un texte par défaut ("Something to do" par exemple) via _TODO route_
- [ ] Modifie le texte de la tâche (input onChange) puis appelle automatiquement la route _TODO route_
- [ ] Supprime la tâche au clic sur le bouton 🗑️ en appelant _TODO route_
- [ ] Change une tâche de colonne avec les boutons ⬅️ et ➡️. Attention, le bouton gauche n'existe pas sur la colonne "To Do", et le droit n'existe pas sur la colonne "Done".

#### ⭐️ Objectifs bonus

- [ ] Mettre en place le **drag & drop** des tâches entre les colonnes et dans une même colonne
- [ ] Changer la **couleur** d'une tâche en fonction de sa colonne
- [ ] Ajouter un **mode clair/sombre (light/dark mode)**
- [ ] Sauvegarder les boards en **localStorage** et synchroniser avec le réseau
- [ ] Add cool animations

## 📅 Jour 2 : Gestion des utilisateur·ices sur le front

Aujourd'hui on va s'occuper d'intégrer la gestion des utilisateur⋅ice dans le frontend. Si jamais tu dois rattraper quelques fonctionnalités du jour 1, c'est aussi le moment !

### 🎯 Objectifs du jour

#### ✅ Objectifs principaux

- [ ] Implémenter l'**authentification côté client**
- [ ] Protéger les routes `/home` et `/boards/[id]` : redirection vers **/login** si l'utilisateur·ice n'est pas connecté·e
- [ ] Rediriger vers `/home` depuis la landing page si l'utilisateur·ice est connecté·e
- [ ] Écrire en **TDD avec Vitest** une fonction pour afficher la **date relative** (ex : "maintenant", "il y a 2 minutes", etc.)
- [ ] Afficher sur la home les informations de **date** et d'**utilisateur·ice** pour chaque board (voir Figma)
- [ ] Ajouter une **modal** pour inviter un·e membre sur une board

#### ⭐️ Objectifs bonus

- [ ] Implémenter une fonction de **recherche "fuzzySearch"** (comme dans VSCode), en **TDD**, et l'utiliser pour filtrer les tâches d'une board
- [ ] Gérer les **avatars** des utilisateur·ices
