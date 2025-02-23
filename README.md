# SpatialRelation
Identifying Spatial Relations in Images using Convolutional Neural Networks
## Description du projet 
Ce projet est une implémentation du texte ci dessous: (https://arxiv.org/pdf/1706.04215) pour modéliser et prédire les relations spatiales entre objets dans des images

![screenshot](images_git/paper.JPG)

## Pipeline
1. Pré-traitement
Pré-traitement des images avec réduction à 4 relations spatiales "en haut","en bas","à droite","à gauche"

![screenshot](images_git/bbox.JPG)

2. implémentation du document
implémentation du document avec vggNET 

3. Entrainement d'un MLP
Calcul de prédiction des relatins spatiales directionnelles en passant directement par le MLP


![screenshot](images_git/pipeline.png)
### Notre cas
test d'implémentation du document avec 2 autres modèles en plus (vggNET,squeezeNET et ViT)

![screenshot](images_git/model_image.png)

## Notebooks
**Remarque** : Les chemins vers les dossiers, images et modèles dans les notebooks doivent être adaptés en fonction de votre configuration locale pour un usage correct. ce sont des notebook fait kaggle, Car kaggle fourni plus de temps d'utilisation de GPU que google, si vous voulez l'adaptez, veuillez changez annotations_path et extracted_images_path dans la racine de votre projet (si vous lancez sur kaggle, il n'y auras pas de problème si le ficher se trouve en racine du projet)


### VggNet

**Fichier** : vggNET.ipybn

**Description** : Ce notebook utilise vggNet comme structure pour l'apprentissage des relations spatiales et resort la matrice de confusion des prédicats ainsi que les cartes de chaleurs sur les relations spatiales.

**Résultats** :
![screenshot](images_git/vgg.PNG)
![screenshot](images_git/vggM.PNG)

### SqueezeNET

**Fichier** : squeezeNET.ipybn

**Description** : Ce notebook utilise squeezeNET comme structure pour l'apprentissage des relations spatiales et resort la matrice de confusion des prédicats ainsi que les cartes de chaleurs sur les relations spatiales.

**Résultats** : 
![screenshot](images_git/squeeze.PNG)
![screenshot](images_git/squeezeM.PNG)

### ViT

**Fichier** : ViT.ipybn

**Description** : Ce notebook utilise ViT comme structure pour l'apprentissage des relations spatiales et resort la matrice de confusion des prédicats ainsi que les cartes de chaleurs sur les relations spatiales (via EigenCAM).

**Résultats** :

![screenshot](images_git/ViT.PNG)
![screenshot](images_git/ViTM.PNG)

**Test sur tout les prédicats**
Plusieurs problèmes apparaissent dès que nous introduisont de la porfondeur dans la images et en sachant que le dataset n'est pas forcément "parfait", nous obtenons des problèmes d'apprentissages .
![screenshot](images_git/9predicates.PNG)
Ce test est présent dans le fichier original avec les 3 modeles présent sous le nom: **All_three.ipybn**

