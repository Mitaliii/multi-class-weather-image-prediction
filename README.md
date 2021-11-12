# multi-class-weather-image-prediction
Estimating image properties from visual content is a fundamental step of various computer vision studies. For example, estimating image scene labels facilitates image browsing and retrieval, and recognizing whether images were captured indoors or outdoors. As of now for this project we have just taken 4 types of weather (i.e. cloudy, rain, sunrise, sunshine) images and classified them using Convolution Neural Networks (CNN) and Support Vector Machine (SVM) as last layer of cnn.
## [Dataset link](https://drive.google.com/drive/folders/1yW1DSVWOdaLXjWgijszeb83X7X7yiVtp?usp=sharing)
## Data cleaning
In order to clean data it is more like 99% cleaning to 1% modeling. This is because a neural network needs images to be a standardized size, but the dataset used in this project is already clean though preprocessing steps like rescale, shear image, zoom range, horizontal flip are required. Steps in pre-processing data for this weather classification using image are done by: 
### (1) Rescale:
As the image contains 256 pixels (from 0 to 255) so to rescale we divide it by 255, so that values are between 0 to 1.
### (2) Shear range and zoom range:
Shear means that the image will be distorted along an axis, mostly to create or rectify the perception angles. It's usually used to augment images so that computers can see how humans see things from different angles. 
### (3) Horizontal flip:
The vertical and horizontal flip augmentation means they will reverse the pixels rows or column-wise respectively. We used the horizontal_flip or vertical_flip arguments to use this technique inside of the ImageDataGenerator class. Below we have the python code for both the methods with results.![Model Report pdf - Adobe Reader 11_12_2021 9_57_41 AM](https://user-images.githubusercontent.com/66302933/141409834-643e250c-f2d6-49c6-9524-f831407da600.png)

## Building Model
In a code we created a baseline neural network for the weather classification problem. Note that we use a
“softmax” activation function in the output layer. Finally, the network uses the efficient Adam gradient descent optimization algorithm with a logarithmic loss function, which is called “squared_hinge” in Keras. We can also pass arguments in the construction of the KerasClassifier class that will be passed on to the fit() function internally used to train the neural network. Here, we pass the number of epochs as 5 when training the model. 
![python code - Jupyter Notebook and 3 more pages - Personal - Microsoft​ Edge 11_11_2021 9_30_07 PM](https://user-images.githubusercontent.com/66302933/141409219-de540368-844b-47a5-a530-1e737cb81d93.png)

## Model Evaluation
After training model for 5 epoch it is evaluated that:
### • accuracy of the train data: 83.31%
### • accuracy of the validation data: 94.90%
### • loss of the train data: 83.3%
### • loss of the validation data: 96.40%
![python code - Jupyter Notebook and 3 more pages - Personal - Microsoft​ Edge 11_11_2021 9_33_51 PM](https://user-images.githubusercontent.com/66302933/141409370-363663ba-6999-429b-ba59-4cc21931c3c4.png)
