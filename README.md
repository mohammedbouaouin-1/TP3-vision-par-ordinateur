# TP 3 : Vision par Ordinateur

**École Nationale des Sciences Appliquées de Fès (ENSA Fès)**  
**Filière :** Ingénierie Logicielle et Intelligence Artificielle (ILIA 2)  
**Module :** Technologies de l'Intelligence Artificielle  
**Enseignant :** Prof. Youness IDRISSI KHAMLICHI  
**Étudiant :** Mohammed Bouaouin  

---

## Présentation du TP

Ce dépôt contient la réalisation du TP 3 consacré au traitement d'images et à la vision par ordinateur :

1. **Partie 1 & 2 : Traitement d'images et vidéos avec OpenCV**
   - Lecture et affichage d'images, conversion en niveaux de gris, flou gaussien et détection de contours (Canny)
   - Capture vidéo / webcam en temps réel et enregistrement du flux en niveaux de gris (`sortie_gris.mp4`)

2. **Partie 3 : Détection et segmentation d'objets avec Detectron2**
   - Segmentation d'instances avec le modèle pré-entraîné **Mask R-CNN** (`mask_rcnn_R_50_FPN_3x`)
   - Test de l'effet du seuil de confiance `SCORE_THRESH_TEST` sur la détection

3. **Partie 4 : Détection et reconnaissance faciale avec Dlib / `face_recognition`**
   - Détection de visages avec le détecteur frontal de Dlib
   - Comparaison et reconnaissance faciale entre une image de référence et une image de test
   - Extraction des 68 points caractéristiques du visage (*landmarks*) et calcul de l'ouverture de l'œil (EAR)

4. **Partie 5 : Détection en temps réel avec YOLO**
   - Détection d'objets avec `yolov8n.pt` et segmentation avec `yolov8n-seg.pt`
   - Comparaison du temps d'inférence entre YOLOv8n et Mask R-CNN

---

## Mini-projet

Le mini-projet est implémenté dans la dernière section du notebook [`TP3_Vision_par_Ordinateur.ipynb`](TP3_Vision_par_Ordinateur.ipynb) :

- **Objectif :**
  1. **Système de présence** : reconnaître les étudiants et enregistrer `Nom + Heure` dans [`presence.csv`](presence.csv) (une seule fois par séance et par étudiant).
  2. **Détecteur de somnolence** : calculer le rapport d'ouverture de l'œil (EAR) à partir des 68 landmarks et déclencher une alerte si l'œil reste fermé plus de 2 secondes.
  3. **Compteur de personnes** : détecter les personnes avec YOLOv8 sur une vidéo et compter celles qui traversent une ligne virtuelle.
  4. **Floutage automatique des visages** : détecter les visages avec Dlib et les anonymiser par `cv2.GaussianBlur`.

- **Installation :**
  ```bash
  pip install opencv-python numpy matplotlib dlib-bin face_recognition ultralytics
  ```

- **Utilisation :**
  Ouvrir [`TP3_Vision_par_Ordinateur.ipynb`](TP3_Vision_par_Ordinateur.ipynb) dans Jupyter Notebook ou VS Code et exécuter les cellules de la section **Mini-projet**.
