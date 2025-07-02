
# 👥 Workflow Git collaboratif – Équipe Plateforme de Positionnement Produits

Cornillon Amandine - Traore Sy Lucien - Leunkeu Leaticia

Ce document décrit notre méthode de travail en équipe sur GitHub avec Git, VS Code et branches fonctionnelles.


## 🔀 Structure des branches

main (production/en utilisation)
│
├── branch1 (intégration des features validées)
│   ├── formulaire
│   ├── test
│   └── 


- `main` : production uniquement, stable, utilisée par les utilisateurs finaux.
- `branch1` : branche de développement, toutes les features y sont intégrées après test.
- `xxx` : 1 branche par fonctionnalité en cours de développement.

## Petits rappels de notions:

| Commande        | Rôle                                           | Où ça agit ?               | Exemple                         |
|------------------|------------------------------------------------|------------------------------|----------------------------------|
| `git pull`       | Récupère les nouveautés du dépôt distant       | GitHub → ton ordi            | `git pull origin branch1`       |
| `git add .`      | Prépare les fichiers pour un commit           | Local                        | `git add .`                     |
| `git commit -m`  | Enregistre les modifs localement              | Local                        | `git commit -m "feat: ..."`     |
| `git push`       | Envoie les commits sur GitHub                 | Ton ordi → GitHub            | `git push origin ma-branche`    |
| `git merge`      | Fusionne une branche dans une autre           | Local ou GitHub              | `git merge feature/formulaire`  |


## 🌱 UTILISATION 1 : Créer sa branche pour développer

> À faire **au début** d’une nouvelle fonctionnalité

```bash
git checkout branch1                    # Se placer sur la bonne base
git pull                                # S'assurer d'avoir la dernière version
git checkout -b feature/ma-feature      # Créer et passer sur ta propre branche

## 🌱 UTILISATION 2 : Travailler et envoyer ses changements

> À faire pendant et après le développement 
git pull    origin/ma-feature                            # Importer les modifications des autres developpeurs
# Ajouter vos modifications aux fichiers
git add .                                               # Préparer les fichiers modifiés
git commit -m "feat: ajout de la fonctionnalité xxx"    # Enregistrer les modifications localement
git push -u origin feature/ma-feature                   # Envoyer la branche sur GitHub

--> Possibilité de le faire manuellement sur VSCode


📬 Ouvrir une Pull Request ()
Lorsqu'une version d'un fichier/ d'une fonctionnalité est pre^te et validée par chacun, il est possible de réaliser 
un Pull Request pour envoyer cette version de la branche sur Github
(Quand ta fonctionnalité est prête à être relue et intégrée à branch1)
Le Pull Request permet d'ajouter une fonctionnalité

Va sur GitHub : https://github.com/Ton_Pseudo/Plateforme_Positionnement_Produits
Clique sur "Compare & pull request" (ou vas dans l’onglet “Pull Requests”)
Vérifie :
    base = branch1
    compare = ta branche (feature/xxx)
Rédige un titre et une description claire
Clique sur “Create Pull Request”


🔄 Quand tout est prêt → Fusionner vers main
Un Merge permet de fusionner plusiurs branches/ fonctionnalités sur un même projet 
(exemple: les 4 banches formulaires, test, analyse données et gestion d'accès peuvent être Merge pour fusionner en un projet opérationnel sur branch1)
Si la branche1 est opérationnelle une fois toutes les fonctionnalités ajoutées, ellle peut être fusionnées et envoyée sur le main (en production)
Une fois que branch1 contient toutes les features testées :

Option 1 — via le terminal

bash
git checkout main
git pull
git merge branch1
git push
Option 2 — via GitHub

Ouvre une Pull Request de branch1 vers main
Test utilisateur recommandé avant de merger








