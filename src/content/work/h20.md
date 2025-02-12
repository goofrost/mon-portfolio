---
title: Gestion des Transactions avec Symfony 6
publishDate: 2025-02-12 00:00:00
img: /assets/symfony.jpg
img_alt: Interface de gestion d'un service de paiement sous Symfony


description: |
  Ce projet est une application web développée avec Symfony 6 permettant aux utilisateurs de gérer leurs transactions en ligne. Il inclut un module de gestion des utilisateurs, une administration des produits et services, ainsi qu'un service d'échange d'argent via Stripe. Pensée pour être sécurisée et évolutive, l'application s'intègre parfaitement avec des outils modernes et suit les bonnes pratiques du développement web.

tags:
  - Web Development
  - Symfony 6
  - PHP
  - API Integration
  - Stripe
  - Bootstrap
  - MySQL
---

## Présentation du projet
Ce projet Symfony 6 est conçu pour offrir une plateforme complète de gestion des utilisateurs et de leurs transactions en ligne. Il propose un système d'authentification, un tableau de bord pour administrer les données, ainsi qu'un module de paiement sécurisé permettant de gérer les échanges d'argent.

L'application est développée avec Symfony 6 et suit l'architecture MVC (Modèle-Vue-Contrôleur) pour assurer une bonne séparation des responsabilités. L'interface utilisateur est construite avec Bootstrap, garantissant une expérience fluide et réactive sur différents appareils.

## Fonctionnalités principales

### 🔑 Authentification et gestion des utilisateurs
- **Inscription et connexion sécurisées** avec gestion de session
- **Rôles et permissions** (utilisateur, administrateur)
- **Persistance des sessions** pour garder l’utilisateur connecté sur toutes les pages

### 📊 Gestion des produits et services
- **Ajout, modification et suppression** de produits/services via un tableau de bord
- **Affichage détaillé** des produits disponibles
- **Catégorisation et filtrage** pour une navigation simplifiée

### 💸 Système de paiement intégré (Stripe)
- **Paiement sécurisé** via l’API Stripe
- **Gestion des transactions** avec suivi des paiements
- **Historique des échanges** stocké en base de données
- **Gestion des erreurs et notifications** en cas de problème de transaction

### 🛠️ Technologies utilisées
- **Backend** : Symfony 6, PHP 8, MySQL
- **Frontend** : Bootstrap, Twig, JavaScript
- **Sécurité** : JWT pour l’authentification, HTTPS, protection CSRF
- **API** : Stripe pour la gestion des paiements

## Aperçu du code
### Authentification avec Symfony Security
```php
// src/Controller/SecurityController.php
namespace App\Controller;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\Security\Http\Authentication\AuthenticationUtils;
use Symfony\Component\Routing\Annotation\Route;

class SecurityController extends AbstractController
{
    #[Route('/login', name: 'app_login')]
    public function login(AuthenticationUtils $authenticationUtils): Response
    {
        $error = $authenticationUtils->getLastAuthenticationError();
        $lastUsername = $authenticationUtils->getLastUsername();
        return $this->render('security/login.html.twig', [
            'last_username' => $lastUsername,
            'error' => $error
        ]);
    }
}
```

## Comment utiliser ?
1. **Installer les dépendances**
   ```sh
   composer install
   npm install
   ```
2. **Configurer la base de données**
   ```sh
   symfony console doctrine:database:create
   symfony console doctrine:migrations:migrate
   ```
3. **Lancer le serveur Symfony**
   ```sh
   symfony serve
   ```
4. **Accéder à l'application** via `http://symfony6.test`

## Démonstration
![Interface de l'application](/assets/symfony_dashboard.jpg)

## Liens utiles
- [Documentation Symfony](https://symfony.com/doc/current/index.html)
- [Stripe API](https://stripe.com/docs/api)
- [GitHub du projet](#) [*(Symfony Project)*](https://github.com/goofrost/Portfolio-GARONNE-Quentin/tree/main/Projets/symfony6)

## Auteur
**Quentin Garonne** - Développeur Web et étudiant en Bac+2 à IPI Toulouse

