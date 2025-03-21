# Melanoma_Detection_Assignment
To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

# What is the dataset that is being used?

The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.

    Actinic keratosis
    Basal cell carcinoma
    Dermatofibroma
    Melanoma
    Nevus
    Pigmented benign keratosis
    Seborrheic keratosis
    Squamous cell carcinoma
    Vascular lesion

# Business Goal:

The objective is to construct a multiclass classification model using a personalized convolutional neural network (CNN) implemented in TensorFlow.

# Project Pipeline

The project pipeline involves several steps in order to build a multiclass classification model using a custom convolutional neural network in TensorFlow. The steps are as follows:

**Data Reading and Understanding:** _The first step involves defining the path for train and test images to be used in the project._

**Dataset Creation:** _The next step is to create the train and validation datasets from the train directory, with a batch size of 32 and resizing the images to 180 x 180._

**Dataset Visualization:** _The project involves visualizing one instance of all the nine classes present in the dataset to get an understanding of the distribution of classes in the data._

**Model Building and Training:** _The project involves building a CNN model that can accurately detect the nine classes present in the dataset. The model is built by rescaling the images to normalize the pixel values between (0,1) and choosing an appropriate optimizer and loss function for model training. The model is trained for approximately 20 epochs and the findings after the model fit are analyzed to check for evidence of overfitting or underfitting._

**Data Augmentation:** _To resolve issues of overfitting or underfitting, an appropriate data augmentation strategy is chosen._

**Model Building and Training on Augmented Data:** _A CNN model is built using the augmented data and is trained for approximately 20 epochs. The findings after the model fit are analyzed to see if the earlier issue has been resolved._

**Class Distribution:** _The project involves examining the class distribution in the training dataset, including which classes dominate the data in terms of proportionate number of samples and which class has the least number of samples._

**Handling Class Imbalances:** _To rectify class imbalances present in the training dataset, the Augmentor library is utilized._

**Model Building and Training on Rectified Class Imbalance Data:** _A CNN model is built on the rectified class imbalance data, with images being rescaled to normalize pixel values between (0,1), and choosing an appropriate optimizer and loss function for model training. The model is trained for approximately 30 epochs and the findings after the model fit are analyzed to see if the issues have been resolved._

## CNN Architecture Design

To classify skin cancer using skin lesions images. To achieve higher accuracy and results on the classification task, I have built custom CNN model.
    * Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.

    ..* Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.
    ..* Convolutional Layer - Convolutional layers apply a convolution operation to the input, passing the result to the next layer. A convolution converts all the pixels in its receptive field into a single value. For example, if you would apply a convolution to an image, you will be decreasing the image size as well as bringing all the information in the field together into a single pixel.
    ..* Pooling Layer - Pooling layers are used to reduce the dimensions of the feature maps. Thus, it reduces the number of parameters to learn and the amount of computation performed in the network. The pooling layer summarises the features present in a region of the feature map generated by a convolution layer.
    ..* Dropout Layer - The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.
    ..* Flatten Layer - Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer.
    ..* Dense Layer - The dense layer is a neural network layer that is connected deeply, which means each neuron in the dense layer receives input from all neurons of its previous layer.
    ..* Activation Function(ReLU) - The rectified linear activation function or ReLU for short is a piecewise linear function that will output the input directly if it is positive, otherwise, it will output zero.The rectified linear activation function overcomes the vanishing gradient problem, allowing models to learn faster and perform better.

# Model
The model uses a simple CNN architecture with convolutional, Max pooling and dense layers. The model is trained using SparseCategoricalCrossentropy loss and the Adam optimizer.

# Observations:

    We build total 3 models, first model does not try to fix class imbalance or any other data issue and showed 93.9% accuracy on train while 84.4 on validation data.
    Second model uses Data Augmentation Strategy to make the model more robust, but it ended up creating highly underfitted model
    In final model, Data aurmentation is being used to add 500 images for each class to handle class imbalance, along with 40 epochs, and this model performed well. 
    Model showing great improvement in accuracy as accuracy for Train data is 94.31 while for test data it's 91.99 %.
    Loss graph also showing some fluctuation as begining but later it's setteled for 2-3% range on both validation and train data.
    Model benefitted largaly with Aurgumentation strategy as it helped fix class imbalance problem.

 # Final Conclusion - Model 3 With Augmentor - 500 Generated images

    With help of Augmentor generated data, Overall Accuracy increased very well
        Training Accuracy - around 91%
        Validation Accuracy - around 87%

    Overall Loss
        Training Loss - less than 0.25
        Validation Loss - between 0.4

    The model's performance was significantly enhanced through a judicious augmentation strategy, which effectively mitigated the challenges posed by class imbalance.

# Technologies Used

    Python 3.0
    Pandas
    Numpy
    matplotlib
    pathlib
    tensorflow
    keras    
    Agumentor

# Contact

Created by @Mrudhul Kommana
