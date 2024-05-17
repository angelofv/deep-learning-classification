# Projet Classification d'Images de Visages

## Contexte
Ce mini-projet a été réalisé lors de ma dernière année en tant qu'étudiant ingénieur spécialisé en Intelligence Artificielle et Data Science à l'[ESIEA](https://www.esiea.fr/), une école d'ingénieurs basée à Paris.

## Objectif
Il s’agit d’un problème de classification d’images de visages. Le critère de classification n’est pas décrit ici, il est défini de façon implicite par les labels de la base d’apprentissage. Néanmoins, il s’agit d’une combinaison de caractéristiques « softbio » (barbe, moustache ou non, forme du menton, couleur des yeux, chapeau ou pas, etc.). En plus d’une bonne performance de classification, on cherche à équilibrer les performances entre femmes et hommes. Pour cela, pour chaque image de la base d’apprentissage, on fournit les labels de genre.

## Evaluation
La métrique finale, retenue pour évaluer chaque modèle, sera la moyenne des performances de classification entre hommes et femmes, à laquelle on soustrait le double de la différence des performances entre hommes et femmes (en valeur absolue). Pour obtenir une bonne métrique finale, il faut donc obtenir une bonne performance de classification sur la population totale (hommes + femmes) et, en même temps, avoir des performances de classification similaires entre hommes et femmes.

## Data
Les données sont les suivantes :
- **Base d’apprentissage** : un dossier `train` contenant 192,576 images de visage, numérotées de 000000 à 192575. Les fichiers sont au format jpg, les images font 80x80 et sont en couleur.
- **Labels d’apprentissage** : un fichier nommé `train.txt`, contenant trois colonnes. La première liste les noms des 192,576  images de la base d’apprentissage. La deuxième colonne liste les labels à prédire (-1 ou 1) de la base d’apprentissage, tandis que la troisième liste les genres binaires (-1 : femme, 1 : homme) correspondants.
- **Base de test** : un dossier `test` contenant 9,999 images de visage, au même format que la base d’apprentissage.

Le rendu devra être organisé comme le fichier `train.txt`, sans la colonne du label de genre. Ce sera donc un fichier texte à deux colonnes : la première indiquant le nom de l’image de la base de test, la deuxième indiquant la prédiction du label à prédire.

## Hint
- La labélisation n’est pas parfaite. Une fonction de coût robuste pourrait aider lors de l’apprentissage.

### Répondre aux questions suivantes
1. Quel type d’architecture avez-vous utilisé, pourquoi ?
2. Combien de convolutions contient votre architecture, pourquoi ?
3. Comment vous êtes-vous préoccupé de l’overfitting ?
4. Est-ce que l’asymétrie de la base d’apprentissage est un problème ? Si oui, comment l'avez-vous traité ?
5. Est-ce que le fait que les labels soient bruités a posé problème ? Comment l’avez-vous géré ?
6. Pour les images de la base de test, à partir de la sortie de votre réseau, comment attribuez-vous le label ?
7. Comment avez-vous pris en compte les problèmes d’équité de l’algorithme ?
8. J’ai précisé que le label correspondait à une combinaison de caractéristiques « softbio » et non image. Qu’est-ce que cela change pour vous ?
9. Avez-vous tenté d’utiliser un modèle pré-entraîné ? Que vous l’ayez fait ou non, comment procéderiez-vous pour choisir le modèle et déterminer ce qu'il faut apprendre ?
10. Avec un mois supplémentaire pour travailler, que feriez-vous pour améliorer vos résultats ?
11. Question non notée : À quoi correspond le label recherché ?

## Structure du projet
```plaintext
/nlp-topic-modeling-project
│
├── train                                  # Dossier contenant les images du jeu de données
├── train.txt                              # Fichier contenant les labels softbio et les genres
├── test                                   # Dossier contenant les images pour l'inférence
├── model_cnn_faces.keras                  # Fichier du modèle CNN entraîné
├── model_history.json                     # Fichier contenant l'historique de l'entraînement du modèle (perte, accuracy, etc.)
├── cnn_classification_softbio.ipynb       # Notebook du modèle
├── generate_predictions.ipynb             # Notebook pour l'inférence sur la base de test
├── predictions.txt                        # predictions du label à prédire
└── rapport_projet_cnn_classification.pdf  # Rapport du projet
```
