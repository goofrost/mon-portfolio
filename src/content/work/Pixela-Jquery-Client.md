---
title: Pixela jQuery Client
publishDate: 2025-02-12 00:00:00
img: /assets/pixel_jquery_client_1.jpg
img_alt: Iridescent ripples of a bright blue and pink liquid
description: |
  Pixela jQuery Client est une application web permettant aux utilisateurs de gérer leurs graphes sur la plateforme Pixela via une interface intuitive construite avec jQuery et Bootstrap. Elle offre la possibilité de créer un compte, d'ajouter des graphes, et de suivre visuellement ses progrès grâce aux graphes générés dynamiquement.
tags:
  - Web Development
  - JavaScript
  - API Integration
  - jQuery
  - Bootstrap
---
---

## Fonctionnalités
- **Inscription et connexion** : Les utilisateurs peuvent s'inscrire et se connecter à leur compte Pixela en stockant leurs informations de manière sécurisée en local.
- **Gestion des graphes** : Création, récupération et affichage des graphes existants avec des images générées dynamiquement.
- **Ajout et suppression de pixels** : Les utilisateurs peuvent enregistrer des données quotidiennes sous forme de pixels sur leurs graphes.
- **Interface responsive** : Utilisation de Bootstrap et Water.css pour une mise en page fluide et moderne.

## Technologies utilisées
- **Frontend** : jQuery, Bootstrap, Water.css
- **Backend API** : [Pixela API](https://pixe.la)
- **Stockage local** : localStorage pour conserver les identifiants des utilisateurs

## Aperçu du code
```javascript
// Lorsque la page est chargée, vérifie si l'utilisateur est déjà connecté
$(document).ready(function () {
    const username = localStorage.getItem("username");
    const token = localStorage.getItem("token");

    if (username && token) {
        $("#auth-section").hide();
        $("#dashboard").show();
        loadGraphs();
    }
});
```

## Comment utiliser ?
1. **S'inscrire ou se connecter** avec un nom d'utilisateur et un token API Pixela.
2. **Créer un graphe** en fournissant un identifiant et un nom.
3. **Ajouter ou supprimer des pixels** pour enregistrer ses activités quotidiennes.
4. **Visualiser ses données** directement via les graphes générés par Pixela.

## Démonstration
![Pixela Client Screenshot](/assets/pixel_jquery_client_2.jpg)

## Liens utiles
- [Pixela API](https://pixe.la)
- [GitHub du projet](#) [*(Pixela jquery client projet)*](https://github.com/goofrost/Portfolio-GARONNE-Quentin/tree/main/Projets/Pixela%20Jquery%20Client)

## Auteur
**Quentin Garonne** - Développeur Web et étudiant en Bac+2 à IPI Toulouse

