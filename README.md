# Image-Segmentation-for-Disaster-Resilience

A deep-learning based image segmentation model for detecting and classifying affected regions from drone imagery after floods, helping in faster response and damage assessment.

- [Dataset Link](https://www.kaggle.com/datasets/saiharshitjami/flood-images-mask-segmentation)

The Project uses image samples with their corresponding segmentation masks for efficient image segmentation model training.

This will help the model classify between a damage affected region and a normal region, the datasets of both classes will be split in 80-20% for training and testing of the model.

## Week 1:
The task agenda for week 1 focuses on data preprocessing and EDA (Exploratory Data Analysis). With following members contributing to each task:\
Somya Sharma : Data Preprocessing\
Suhani Vhatkar & Aman Jaiswal : EDA

- The dataset preprocessing consisted of loading the dataset and matching each image to its corresponding mask, removing corrupted data samples, converting imaged from BGR to RGB and resizing all images to equal dimensions (256X256)  while normalizing pixel values and also resizing image segmentation masks (256X256) and converting them into binary (0 - normal, 1 - flood).
