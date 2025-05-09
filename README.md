# Projet - Information Spotting (Indexation de Documents Numérisés)

Projet réalisé dans le cadre du module **Indexation Contenu Multimédia**, Université de La Rochelle / IFI - Université nationale du Vietnam.

## Objectif

Ce projet vise à développer un système de recherche d’information visuelle dans des documents papier numérisés à partir d'une capture vidéo. Il s’appuie sur l’extraction de points d’intérêt visuels, la description de ces points, leur indexation, puis la recherche de correspondance à partir de requêtes vidéo.

## Technologies et bibliothèques

- Python 3
- OpenCV
- NumPy
- Scikit-learn
- Gensim
- NLTK
- Matplotlib
- SciPy
- Annoy (LSH)

##  Fonctionnement du système

### 1. Extraction des caractéristiques (SIFT)

- Détection de points d’intérêt dans les images de documents.
- Calcul des descripteurs SIFT pour chaque point.
- Construction d’un dictionnaire de descripteurs.

### 2. Indexation (LSH)

- Utilisation de **Locality Sensitive Hashing** via `Annoy` pour indexer les descripteurs.
- Création d’une table de hachage pour accélérer la recherche de correspondance.

### 3. Recherche par vidéo

- Lecture d’une vidéo simulant la capture d’un document avec une caméra.
- Pour chaque frame :
  - Extraction des descripteurs SIFT.
  - Recherche des plus proches voisins dans l’index (LSH).
  - Vote pour déterminer le document correspondant.

### 4. Affichage des résultats

- Affichage de la frame en cours de traitement.
- Indication du document identifié.
- Sauvegarde et visualisation des frames de correspondance détectée.

## Structure du code

- `tp_indexation.ipynb` : Notebook principal contenant toutes les étapes :
  - Chargement des images et vidéos
  - Construction de l’index
  - Traitement vidéo
  - Visualisation

## Données

- **Base d'images** : Images de documents administratifs ou pages de livre.
- **Vidéos** : Captures simulées de ces documents (fournies sur Moodle).

## Concepts appliqués

- SIFT (Scale-Invariant Feature Transform)
- Locality Sensitive Hashing (LSH)
- Recherche de correspondance par vote majoritaire
- Matching de descripteurs visuels
- Indexation basée sur la vision par ordinateur

##  Références

- [OpenCV SIFT Tutorial](https://docs.opencv.org/master/da/df5/tutorial_py_sift_intro.html)
- [Annoy (Approximate Nearest Neighbors)](https://github.com/spotify/annoy)
- [PyImageSearch - Image Hashing](https://www.pyimagesearch.com/2017/11/27/image-hashing-opencv-python/)
