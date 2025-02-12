---
title: Simulation de Combat avec DrivedMech
publishDate: 2025-02-12 00:00:00
img: /assets/Grandmechanicalarena.jpg
img_alt: Simulation de combat entre personnages et mechas
description: |
  Ce projet est une simulation de combat mettant en œuvre des personnages, des mechas et des entités combinées appelées DrivedMech. Chaque entité possède des points de vie et une puissance d'attaque, et la bataille se déroule de manière interactive jusqu'à ce qu'un seul survivant demeure.
tags:
  - C++
  - Programmation Orientée Objet
  - Simulation
  - Jeux Vidéo
  - Algorithmes
---
---

## Fonctionnalités
- **Gestion des entités** : Personnages, Mechas et DrivedMech peuvent interagir dans une simulation de combat.
- **Système d'attaque** : Chaque entité peut attaquer une autre, infligeant des dégâts basés sur sa puissance d'attaque.
- **Vérification des morts** : Une entité avec 0 HP est considérée comme morte et ne peut plus attaquer.
- **Affichage dynamique** : L'état du combat est mis à jour après chaque tour.

## Technologies utilisées
- **Langage** : C++
- **Paradigme** : Programmation orientée objet
- **Smart Pointers** : Utilisation de `std::shared_ptr` pour gérer la mémoire dynamiquement
- **Gestion des classes** : Classes `Character`, `Mech`, `DrivedMech` et `Game` pour orchestrer la simulation

## Aperçu du code
```cpp
void Game::startBattle() {
    while (!isGameOver()) {
        for (auto &attacker : elements) {
            if (!attacker->getIsDead()) {
                std::shared_ptr<Element> target = findTarget();
                if (target) {
                    attacker->attack(target);
                }
            }
        }
        displayStatus();
    }
    std::cout << "\nAll elements are dead! Battle over." << std::endl;
}
```

## Comment utiliser ?
1. **Instancier les entités** (`Character`, `Mech`, `DrivedMech`).
2. **Ajouter les entités** à la simulation avec `Game.addElement()`.
3. **Démarrer la bataille** avec `Game.startBattle()`.
4. **Observer les résultats** via la console.

## Extrait de simulation attendue
```
Mech1 attacks Character2 for 10 damage!
Character2 is dead!
Mech2 attacks Character1 for 10 damage!
Character1 is dead!

Current status:
Character1 - HP: 0, Attack: 0 (Dead)
Character2 - HP: 0, Attack: 0 (Dead)
Mech1 - HP: 50, Attack: 10
Mech2 - HP: 50, Attack: 10
```

## Liens utiles
- [Documentation C++](https://cplusplus.com)
- [GitHub du projet](#) *[Grand Mechanical Arena](https://github.com/goofrost/Portfolio-GARONNE-Quentin/tree/main/Projets/GRAND%20MECHANICAL%20ARENA)*

## Auteur
**Quentin Garonne** - Développeur C++ et étudiant en Bac+2 à IPI Toulouse

