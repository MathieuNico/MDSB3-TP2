
# Git Flow

Gitflow est un modèle de branching Git alternatif qui utilise des branches de fonctionnalité et plusieurs branches primaires. Il a été publié et popularisé pour la première fois par Vincent Driessen de chez nvie. Comparé au développement basé sur le tronc, Gitflow dispose de davantage de branches plus longues et de commits plus importants.

# Fonctionnement

Au lieu d'une seule branche main, ce workflow utilise deux branches pour sauvegarder l'historique du projet. La branche main stocke l'historique officiel des versions, et la branche develop sert de branche d'intégration pour les fonctionnalités.

## Branche de fonctionnalité

Il convient de créer une branche pour chaque fonctionnalité. Ces branches seront ensuite pushées vers le dépôt centralisé en vue d'une sauvegarde/collaboration. Cependant, au lieu de créer une branche à partir de main, les branches de fonctionnalité (feature) utilisent develop comme une branche parente. Lorsqu'une fonctionnalité est terminée, elle est à nouveau mergée dans la branche de développement. Les fonctionnalités ne communiquent jamais directement avec la branche principale (main).

## Branche de livraison

Une fois que develop aura acquis assez de fonctionnalités en vue d'une livraison (ou qu'une date de livraison prédéfinie approche), faites un fork d'une branche de version (release) à partir de develop.

# Exemple

Voici un exemple complet illustrant le workflow de branche de fonctionnalité : imaginons une configuration de dépôt avec une branche main.

```bash
    git checkout main
    git checkout -b develop
    git checkout -b feature_branch
    # work happens on feature branch
    git checkout develop
    git merge feature_branch
    git checkout main
    git merge develop
    git branch -d feature_branch
```


## En savoir plus

[En savoir plus](https://www.atlassian.com/fr/git/tutorials/comparing-workflows/gitflow-workflow)

