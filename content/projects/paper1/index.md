---
title: "I. Microscope images processing and understanding by computer vision" 
tags: ["Microscope Images Processing & Understanding"]
description: "In this projects we develop automated pipeline based on deep learning and computer vision models for characterizing static and dynamic behaviors of multi-scale phenotypes from bright-field and fluorescent microscope images." 
summary: "In this projects we develop automated pipeline based on deep learning and computer vision models for characterizing static and dynamic behaviors of multi-scale phenotypes from bright-field and fluorescent microscope images." 
cover:
    image: "figure1.png"
    alt: "Some Uses For Olive Oil"
    relative: false
editPost:
    URL: "https://github.com/pmichaillat/hugo-website"
    Text: "Project I"

---

---

***1. Research goal***
<div style="text-align: justify;">
Developing automated pipeline based on deep learning and computer vision models for characterizing static and dynamic behaviors of multi-scale phenotypes from bright-field and fluorescent microscope images.
</div>
<br>

***2. Methods***

+ <u>**Image segmentation**: Precisely extracting the intricate subcellular structures</u>

  (1) *Dataset preparation*: Collected high-resolution fluorescent microscope images and manually annotated the masks of essential organelles, including endoplasmic reticulum (ER), mitochondria (MITO), lysosome (LYSO) and nucleus (NUC). 


  (2) To segment these intricate structures, novel deep neural networks (multi-resolution encoder, hierarchical fusion loss) were developed, and novel training strategies (few-shot and self-supervised learning) were exploited for reducing training costs.

---

+ <u>**Feature engineering**: Characterizing morphologies and interactive behaviors of organelles</u>
 
  (1) *Dataset preparation*: Constructed control group that contained wildtype cells and experimental groups that contained cells treated by different types of drugs. Acquired multi-channel fluorescent microscope images synchronously for ER and MITO of the cells.

  (2) Based on the segmentation results, the static and dynamic behaviors (morphological features, network attributes, contacts, time-series features) of ER and MITO can be correlated, further revealing their interactive mechanism.

  (3) By integrating the segmentation results of nucleus and ER, cell center and border can be approximated. The spatial distribution of lysosomes can then be obtained, which provided evaluation metrics for drug screening and related biological mechanism.

<div style="text-align: center;">
<video src="er_graph.mp4" autoplay="false" controls="controls" width="640" height="320"></video>
</div>

<br>
<br>

<div style="text-align: center;">
<video src="wbp.mp4" autoplay="false" controls="controls" width="640" height="320"></video>
</div>

---


+ <u>**Phenotype classification**: Implicitly representation of phenotype variations</u>
  
  (1) *Dataset preparation*: Constructed experimental groups by treating cells with different types of drugs to induce ER stress at different levels, which presented different amount of ER whorls. Then acquired their high-resolution fluorescent microscope images to construct the dataset.

  (2) Trained a Mask R-CNN to detect and crop out each cell region from a full view. Trained a deep classification model to separate normal and abnormal ER structures. Utilized Grad-CAM to identify the ER whorls in a weakly-supervised manner.

  (3) Counted the cells in a well that present ER stress at different levels. The distribution of the cells from various wells treated by different types of drugs was used to interpret the functions of these drugs.


<div align="center">
<img src="erstress.jpg" alt="Morphological analysis of ER stress for drug screening" width="600" height="600">
</div>

+ <u>**Stereo vision**: 3D reconstruction from axial-view microscope imaging system</u>

  (1) *Dataset preparation*: The imaging system was constructed by fixing the specimen in a tubule, the axial-direction of which was positioned perpendicularly to the camera. By rotating the specimen around the tubule axle, its profiles from all directions can be viewed and imaged.

  (2) Silhouette-based method and probabilistic model were developed for calibrating the camera system, and multi-view 3D reconstruction methods were proposed to recover the 3D shapes of the specimen from a series of 2D images.

  (3) By acquiring bright-field and fluorescence images of the specimen, the 3D reconstruction of its overall shape and its inner structures can be synchronized and aligned. The results can support the studies of toxicology and pharmacokinetics, in which the 3D inner structures tracked the drug’s function in an individual-dependent reference (the overall shape of the specimen).

  (4) Some interesting demos can be found here: [demos](https://liacs.leidenuniv.nl/~guoy3/#Database)

<div style="text-align: center;">
<video src="zebrafish_3d_liver.mp4" autoplay="false" controls="controls" width="640" height="320"></video>
</div>