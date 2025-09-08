
# CLARUS V1

CLARUS: Contrastive Learning and Anomaly Detection for Respiratory Ultrasound Screening 

This work is to be presented at the IEEE IUS 2025 conference


## Overview

CLARUS comprises of 2 modules that is utilized to detect the presence of pneumonia in pediatric lung ultrasound data. This framwork detects small and large consolidations within a lung ultrasound frame.

This framework consists of two modules:
### 1. Unsupervised Anomaly Detection module 
This module learns latent features of a balanced LUS dataset using different CNN models. A reference distribution is also constructed using frames of patients without consolidation. Then, a cosine distance plot is used to measure the deviation of test frame embeddings from the reference distribution. A custom threshold is set to determine whether or not the video contains large consolidations or not. 
 

### 2. Self-supervised Contrastive Learning module 

This module is trained on positive(both images contain consolidation) and negative(either of the images contain consolidation) pairs of images. A contrastive loss encourages similar frames to cluster and dissimilar frames to separate in the embedding space. Frame-level binary classifier head is attached for determining the probability of whether a frame contains a small consolidation or not.


## Relevant

The dataset used for this project is from the paper: [Curated and Annotated Dataset of Lung US Images in Zambian Children with Clinical Pneumonia](https://pubmed.ncbi.nlm.nih.gov/38381039/)

Three CNN models were used to train and learn the latent features for both the modules. The .pth files are listed below:

[ResNet-18 model path](https://www.dropbox.com/scl/fi/0pp83yfrg10p7bigar9r4/trained_resnet18_contrastive_with_classifier_ssl.pth?rlkey=sdxj5uarxyw9ibv5lsw9u0ctr&st=cinbdjs9&dl=0)\
[DenseNet-121 model path](https://www.dropbox.com/scl/fi/n574ewhk0l0bnotjnm24q/trained_densenet121_contrastive_with_classifier_ssl.pth?rlkey=vycfaqgj38k5zhg345tzl5r94&st=zqkbr932&dl=0)\
[EfficientNet-B0 path](https://www.dropbox.com/scl/fi/c062f5yikd2wbice7wowb/trained_efficientnet_contrastive_with_classifier_ssl.pth?rlkey=kropnhj6g74l0no2cphtwpey4&st=1dr3mhuk&dl=0)

## Note
CLARUS V2 is another model that does video-level classification, which will be made public once it is published.
