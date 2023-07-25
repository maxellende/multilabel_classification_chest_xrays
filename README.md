# Multilabel classification of chest diseases 
Personnal project in progress - Multilabel classification of chest diseases using chest xrays

## Data
[NIH Chest X-ray Dataset](https://www.kaggle.com/datasets/nih-chest-xrays/data) found on Kaggle \
Over 112,000 Chest X-ray images from more than 30,000 unique patients
15 diagnosis, with 14 chest diseases : 
  - Atelectasis
  - Cardiomegaly
  - Consolidation
  - Edema
  - Effusion
  - Emphysema
  - Fibrosis
  - Hernia
  - Infiltration
  - Mass
  - Nodule
  - Pleural_Thickening
  - Pneumonia
  - Pneumothorax
  - No Finding : the 14 diseases are not found in the image. Also uncertainty case in terms of diagnostic or NLP extraction. More details in the FAQ documents. 


The diagnostics are not mutually exclusive, this is thus a case of multilabel classification.
 
## Code 
An Attention CNN model is trained on downscaled images.

Preprocessing : 
- **Channel** : only one channel is kept, as all channels are the same
- **Resizing** : original image size 1024 is divided by 4
- **Normalization** : mean-std normalization

Model :
- **Architecture** : 3 simple Attention blocks
- **Loss** : BCE loss (with logits)
- **Optimizer** : Adam optimizer

## Performance 
In the research paper _CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays
with Deep Learning_, Rajpurkar et al., 2017, radiologists show an average F1-score of 0.387, the best being at 0.442. CheXNet performs at an average F1-score of 0.435.
Our goal is to perform at least as well as the average performance of radiologists.



