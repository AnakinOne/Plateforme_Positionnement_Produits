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

Commande      | Rôle	                                                | Où ça agit ?	            | Exemple d’usage
git pull	  | Récupère les dernières modifications du dépôt distant	| Depuis GitHub → ton ordi	| git pull origin branch1 pour récupérer les nouveautés
git add .     | Prépare les fichiers à être commités	                | Local	                    | git add . pour ajouter tous les fichiers modifiés
git commit -m |	Sauvegarde localement un instantané du travail	        | Local	                    | git commit -m "feat: ajout du formulaire"
git push	  | Envoie tes commits sur GitHub	                        | Ton ordi → GitHub	        | git push origin ma-branche pour partager ton travail
git merge     |	Fusionne le contenu de deux branches	                | Local ou GitHub	        | git merge feature/formulaire pour intégrer une branche

## 🚧 Cycle de développement

1. Depuis `branch1`, créez une branche feature :
   ```bash
    git checkout branch1          # Se placer sur branch1
    git pull                      # Mettre à jour branch1 localement
    git checkout -b feature/ma-feature  # Créer et basculer sur une nouvelle branche

2. Travaillez sur votre branche :
    git add .                                    # Ajouter tous les fichiers modifiés
    git commit -m "feat: ajout de la fonctionnalité xxx"  # Message clair et structuré

3. Synchronisez avec GitHub :
   git push -u origin feature/ma-feature  # Pousser la nouvelle branche sur GitHub

4. Une fois terminé, ouvrez une Pull Request sur GitHub vers branch1
    Via GitHub :
    Aller sur https://github.com/Ton_Pseudo/Plateforme_Positionnement_Produits
    Cliquer sur "Compare & pull request"
    Vérifier que la base est branch1 et la branche source est feature/ma-feature
    Rédiger un titre et une description, puis cliquer sur "Create pull request"

5. Test et review par un membre de l’équipe avant de merger.

6. Quand branch1 est stable et complet → Pull Request vers main. ( réaliser un test utilisateur au préalable ?)
    git checkout main
    git pull
    git merge branch1
    git push

    Soit via GitHub :
    Ouvrir une Pull Request de branch1 vers main
    Vérifications finales → Merge

🧭 Rappel du flux de travail
    🔄 Tirer les changements avant de commencer : git pull

    🧑‍💻 Coder, puis sauvegarder :
    bash
    git add .
    git commit -m "feat: ..."

    📤 Pousser ton travail sur GitHub : git push

    📬 Créer une Pull Request sur GitHub pour demander la fusion

    ✅ Fusionner (merge) vers la branche d’intégration (branch1)

    🚀 Quand branch1 est stable → Fusion dans main (prod)



✅ Bonnes pratiques à retenir
    Toujours faire git pull avant de commencer à travailler

    Des commits clairs, réguliers et significatifs

    Tester avant chaque Pull Request

    Une Pull Request par fonctionnalité

    Ne jamais merger sans review (sauf urgence validée)