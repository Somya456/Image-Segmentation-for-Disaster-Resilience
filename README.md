# Image Segmentation for Disaster Resilience

A deep-learning based image segmentation model for detecting and classifying affected regions from drone imagery after floods,
helping in faster response and damage assessment.

- [Dataset Link](https://www.kaggle.com/datasets/saiharshitjami/flood-images-mask-segmentation)

The Project uses image samples with their corresponding segmentation masks for efficient image segmentation model training.

This will help the model classify between a damage affected region and a normal region, the datasets of both classes will be split in 80%-10%-10% for training and testing of the model.

## Week 1:
The task agenda for week 1 focuses on data preprocessing and EDA (Exploratory Data Analysis). With following members contributing to each task:

**Somya Sharma : Data Preprocessing**\
**Aman Jaiswal : EDA**

- **Dataset Preprocessing**: consisted of loading the dataset and matching each image to its corresponding mask, removing corrupted data samples, converting imaged from BGR to RGB and resizing all images to equal dimensions (256X256)  while normalizing pixel values and also resizing image segmentation masks (256X256) and converting them into binary (0 - normal, 1 - flood).

- **EDA (Exploratory Data Analysis)**: analysed the preprocessed dataset and provided valuable insights such as dataset size, consistent image size across all image samples, no. of missing values, flood pixel ratio per image, duplicate image samples, etc. In EDA we also determined the optimal split of the dataset for training, testing and validation in (training = 2720 images, testing = 340 images, validation = 341 images).

## Week 2:
The task agenda for week 2 focuses on dataset split, data augmentation, model training, evaluation using IoU and Dice coefficient, and visualization of segmentation outputs.

**Somya Sharma : Dataset Split**\
**Suhani Vhatkar : Data Augmentation**\
**Somya Sharma : Model Training**

- **Dataset Split**: Consisted of splitting dataset of images and their correspoding masks into subsets for training, testing and validation in percentages of 80%, 10%, 10% respectively.

- **Data Augmentation** : To improve model generalization and reduce overfitting, data augmentation was applied only to the training dataset. The validation and test datasets were kept unchanged to ensure unbiased model evaluation.
- **Augmentations Applied** :
  - Horizontal Flip
  - Vertical Flip
  - Rotation
  - Random Brightness
  - Random Contrast

- The augmented training dataset was saved as :
  - `X_train_augmented.npy`
  - `y_train_augmented.npy`

- **Model Training**: Two deep learning models were developed and evaluated for flood image semantic segmentation: a Basic Convolutional Neural Network (CNN) and an Enhanced U-Net architecture.

  **Basic CNN**: A lightweight encoder-decoder CNN was implemented as the baseline segmentation model. The network consists of convolutional layers for feature extraction, max-pooling for downsampling, upsampling layers for spatial reconstruction, and a sigmoid activation layer to generate binary segmentation masks.
  
  **Enhanced U-Net**: An improved U-Net architecture was implemented to achieve better segmentation performance. It incorporates skip connections for preserving spatial information, batch Normalization for stable training, dropout layers for regularization, transposed Convolution layers for learnable upsampling.

  Both models were trained using:
- Optimizer: Adam
- Loss Function: Binary Cross-Entropy + Dice Loss
- Evaluation Metrics: Accuracy, Dice Coefficient, and Intersection over Union (IoU)
- Callbacks: Model Checkpoint, Early Stopping, Reduce Learning Rate on Plateau


   
