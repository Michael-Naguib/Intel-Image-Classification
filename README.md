# Intel-Image-Classification
Last summer during TURC research at the University of Tulsa for a few days we experimented with designing different convolutional architectures for neural nets to classify the Intel Image Dataset : a labeled multiclass image dataset 
- Objective: Design a Convolutional Architecture for a NN to classify the dataset
- Dataset: [Intel Image Dataset provided via Kaggle](https://www.kaggle.com/puneet6060/intel-image-classification/tasks)
-The Code: Is provided in this repository and also through Google Colab  
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1N2IgM66HvkaaXIE4qzgQwwkT6_4U19pJ?usp=sharing)
- **If you run the code in Google Colab you will need to save the dataset to your drive**: the reason for this is that if the script were to attempt to upload a local copy 
of the dataset every time it ran it would take forever! Google drive has an efficient file system which enables quick access by Google Colab's Virtual Machine (i.e the data never left a google server so data and computational resources are in one spot ... and not traversing the internet slowly! )

## Intel Image Dataset
- The [Intel Image Dataset](https://www.kaggle.com/puneet6060/intel-image-classification/tasks) consists of at least 2,190 images *per* category for training & at least 437 images *per* category for validation
- The categories in the dataset are: **glacier**, **sea**, **buildings**, **forest**, **street**, & **mountain**
- Below is a sample of some of the training images
![Image Sample](https://raw.githubusercontent.com/Michael-Naguib/Intel-Image-Classification/main/ImageSample.PNG "Image Sample")

## Model
- One of the primary challenges with the dataset was that models tended to overfit very early on, Increasing the model size and filter's only delayed this.
- To avoid this problem dropout and 2D spatial dropout layers with 50% and 20% probability of dropout respectivly were used
- This helped the model achieve higher accuracy
- The final model began to overfit after around 9 epochs.
![Model](https://raw.githubusercontent.com/Michael-Naguib/Intel-Image-Classification/main/ModelSummary.PNG "Model")


## Metrics and Results
- The model was trained using Sparse Categorical Cross Entropy as the loss and utilized the ADAM optimizer for gradient descent. 
- This enabled the model to reach an accuracy of around 83.7% after 9 epochs!
![Statistics](https://raw.githubusercontent.com/Michael-Naguib/Intel-Image-Classification/main/Statistics.PNG "Statistics")
![EpochAccuracy](https://raw.githubusercontent.com/Michael-Naguib/Intel-Image-Classification/main/EpochAccuracy.PNG "Epoch Accuracy")
![EpochLoss](https://raw.githubusercontent.com/Michael-Naguib/Intel-Image-Classification/main/EpochLoss.PNG "Epoch Loss")