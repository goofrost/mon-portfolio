---
title: Application de Gestion de Conteneurs en Angular
publishDate: 2025-02-12 00:00:00
img: /assets/container.jpg
img_alt: Interface moderne d'une application de gestion de conteneurs
description: |
  Cette application Angular permet de gérer des conteneurs informatiques de manière intuitive. Elle propose un tableau interactif affichant les conteneurs existants, avec la possibilité d'en ajouter, de les supprimer et de visualiser leurs logs. La gestion des utilisateurs est également intégrée avec un système d'authentification JWT pour différencier les rôles d'admin et d'utilisateur.
tags:
- Web Development
- Angular
- TypeScript
- API REST
- Docker
- Authentication
---
---

## Fonctionnalités Principales

### Gestion des Conteneurs

- **Affichage des conteneurs** : Présentation des conteneurs sous forme de tableau interactif avec leurs noms, dates de création, statuts et options de gestion.
- **Ajout de conteneurs** : Possibilité de créer un nouveau conteneur Docker via l'interface.
- **Suppression et redémarrage** : Suppression et redémarrage des conteneurs existants avec confirmation utilisateur.
- **Affichage des logs** : Récupération et affichage des logs des conteneurs pour suivre leur activité.

### Gestion des Utilisateurs

- **Authentification avec JWT** : Sécurisation de l'application avec un système de token JWT pour gérer les sessions utilisateur.
- **Rôles utilisateur et admin** :
  - *Utilisateur* : Accès en lecture aux conteneurs.
  - *Administrateur* : Accès en modification (ajout, suppression, redémarrage de conteneurs).

### Interface Moderne

- **Page d'accueil intuitive** : Propose plusieurs actions principales comme la gestion des conteneurs, l'historique et la description du projet.
- **Utilisation de Bootstrap** : Interface fluide et responsive adaptée aux écrans mobiles et desktop.
- **Thème sombre** : Fond noir pour un affichage agréable et contrasté.

## Technologies Utilisées

- **Frontend** : Angular, TypeScript, Bootstrap
- **Backend** : API REST (externe ou locale pour communiquer avec Docker)
- **Authentification** : JWT pour la gestion sécurisée des utilisateurs
- **Stockage temporaire** : Utilisation de services Angular pour conserver l'état des conteneurs durant la session

## Aperçu du Code

### Exemple de Service pour la Gestion des Conteneurs

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({ providedIn: 'root' })
export class ContainerService {
  private apiUrl = 'http://localhost:3000/containers';

  constructor(private http: HttpClient) {}

  getContainers(): Observable<any> {
    return this.http.get(`${this.apiUrl}`);
  }

  createContainer(name: string): Observable<any> {
    return this.http.post(`${this.apiUrl}/create`, { name });
  }

  deleteContainer(id: string): Observable<any> {
    return this.http.delete(`${this.apiUrl}/delete/${id}`);
  }
}
```

### Exemple de Composant pour Afficher la Liste des Conteneurs

```html
<div class="container-list">
  <h2>Consulter les Conteneurs</h2>
  <table>
    <thead>
      <tr>
        <th>Nom</th>
        <th>Date</th>
        <th>Status</th>
        <th>Connexion</th>
        <th>Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr *ngFor="let container of containers">
        <td>{{ container.name }}</td>
        <td>{{ container.date }}</td>
        <td>{{ container.status }}</td>
        <td>{{ container.connection }}</td>
        <td>
          <button (click)="deleteContainer(container.id)">Supprimer</button>
          <button (click)="restartContainer(container.id)">Redémarrer</button>
          <button (click)="viewLogs(container.id)">Logs</button>
        </td>
      </tr>
    </tbody>
  </table>
  <button (click)="addContainer()">Ajouter un Conteneur</button>
</div>
```

## Comment Utiliser ?

1. **Se connecter** avec un compte utilisateur ou administrateur.
2. **Accéder au tableau des conteneurs** pour consulter leur état.
3. **Gérer les conteneurs** (ajout, suppression, redémarrage) selon les permissions.
4. **Consulter les logs** des conteneurs directement via l'application.

## Liens Utiles

- [Angular Documentation](https://angular.io/docs)
- [Docker API](https://docs.docker.com/engine/api/)
- [GitHub du Projet](#) *([Appli Angular container app](https://github.com/goofrost/Portfolio-GARONNE-Quentin/tree/main/Projets/Projet%20labo%202%20container-app))*

## Auteur

**Quentin Garonne** - Développeur Web et étudiant en Bac+2 à IPI Toulouse

