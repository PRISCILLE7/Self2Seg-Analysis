# Analyse de l’article scientifique — Self2Seg

Ce dépôt présente une synthèse critique de l’article **"Self2Seg: Single-Image Self-Supervised Joint Segmentation and Denoising"**, dans le cadre du module *Bibliographie et Étude de Cas* du Master 2 SIM (IFI, Université Nationale du Vietnam).

Article analysé : [Self2Seg - arXiv:2309.10511](https://arxiv.org/abs/2309.10511)  
 Encadrement : Dr. Ho Tuong Vinh  
Étudiante : Priscille Ebwala (Promotion SIM P27)

---

## Objectif du projet

Réaliser une lecture critique, structurée et approfondie de l’article **Self2Seg**, qui introduit une méthode **auto-supervisée** combinant la segmentation et le débruitage d’une seule image sans annotation manuelle.

---

##  Contenu de l’analyse

### I. Introduction

- Présentation des enjeux : segmentation + débruitage en vision par ordinateur.
- Limites des approches classiques : traitements séparés, dépendance aux données annotées.

### II. Problématique & objectifs

- Proposer une méthode capable de segmenter et débruiter une image **non annotée**.
- Mutualiser les deux tâches via une optimisation conjointe auto-supervisée.

### III. État de l’art

- Méthodes variationnelles (Chan-Vese)
- Débruitage auto-supervisé (Noise2Self, Noise2Void)
- Approches combinées (DenoiSeg)
- Limites relevées : dépendance partielle aux masques ou absence de couplage.

### IV. Solution proposée : Self2Seg

- **Deux réseaux experts** pour avant-plan (DF) et arrière-plan (DB)
- Optimisation conjointe via une fonction énergétique
- Interaction dynamique entre les deux modules :
  - La segmentation guide le débruitage
  - Le débruitage améliore la qualité de segmentation

### V. Mise en œuvre

- Initialisation par masques approximatifs
- Optimisation alternée via ADAM (réseaux) + Chambolle-Pock (segmentation)
- Critère de convergence basé sur la décroissance d’énergie

### VI. Expérimentation

- Données : images de noyaux cellulaires (DSB2018) avec bruit simulé
- Métriques : PSNR, SSIM, Dice
- Résultats :
  - Très bon comportement en bruit faible et fort
  - Supérieur aux méthodes de référence (Chan-Vese, DenoiSeg)

### VII. Travaux connexes

- BEVContrast (LiDAR)
- Multi-Task SSL (Seg + Depth)
- Source Identification (Imagerie médicale)

---

##  Analyse critique

###  Points forts

- Approche **100 % auto-supervisée** applicable sans données annotées
- **Robustesse au bruit élevé**
- Résultats convaincants en segmentation et restauration d’image

###  Limites

- Sensibilité aux hyperparamètres
- Portabilité à d’autres types d’images à confirmer
- Comparaison à des architectures plus modernes (Transformers) absente

### Pistes d’amélioration

- Généralisation à d’autres domaines (satellite, industrie)
- Intégration d’AutoML pour réglage automatique
- Hybridation avec d’autres approches (contraste, multitâche)

---

##  Fichier fourni

- `analyse_self2seg.pdf` : rapport complet de lecture critique (PDF)

---

##  Références principales

- Gruber et al., “Self2Seg: Single-Image Self-Supervised Joint Segmentation and Denoising”, arXiv:2309.10511
- Noise2Self, DenoiSeg, BEVContrast, Multi-Task SSL, Source Identification...

---

 Ce dépôt fait partie du module de *recherche bibliographique* et vise à former à l’analyse scientifique, la synthèse critique, et l’identification des contributions innovantes dans le domaine de l’apprentissage profond appliqué à la vision par ordinateur.
