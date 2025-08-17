# Handwritten_Digit_Recognition-using-Deep-Learning
We will use an ANN trained on MNIST dataset to recognize the hand-written digits 0-9 .

Train Accuracy of Model is roughly 98% Test accuracy of Model is 91%.
# Outline of Project
## 1. Packages/Library used-
   Numpy,Tensorflow,Matplotlib
## 2. Dataset-MNIST(Available in tensorflow):
      A. We will use MNIST database for this task available in the tensorflow library.
      
      B. The load_data() function loads the data into variables x_train,y_train,x_test and y_test.
      
      C. The data set contains 70000 examples of handwritten digits.
      
      D. We split it into 60000 train and 10000 test examples
      
      E. Each training example is a 28-pixel x 28-pixel grayscale image of the digit.
      
      F. Each pixel is represented by a floating-point number indicating the grayscale intensity at that location.
      
      G. The 28 by 28 grid of pixels is “unrolled” into a 784-dimensional vector.
      
      H. Each training examples becomes a single row in our data matrix X. This gives us a 60000 x 784 matrix x_train where every row is a training example of a handwritten digit image.
      
      I. The second part of the training set is a 60000 x 1 dimensional vector y that contains labels for the training set. For example, y = 0 if the image is of the digit 0, y = 4 if the image is of the digit 4 and so on.
## 3. Data Normalisation-Divide each pixel value by 255
## 4. Reshaping the image to feed into neural network- Converting 2-D image array of 28*28 into 1-D array of 784 size.
## 5. Data Visualisation- Visualising the dataset
   <img width="400" height="390" alt="Dataset" src="https://github.com/user-attachments/assets/a6cba10e-81fd-4ad7-811a-3a241b5429a0" />
   
## 6. Tensorflow Model Training
   We use Keras Sequential model and Dense Layer with a ReLU activation to construct the three layer network.We also use a dropout layer to avoid overfitting.
   In order to improve numerical softmax is grouped with the loss function rather than the output layer during training. Therefore while model building we do the following:
   In the final Dense layer we use a 'linear' activation. This is effectively no activation.
   The model.compile statement will indicate this by including from_logits=True.
   **loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True)**
   
   Hence,the outputs are not probabilities. If output probabilities are desired, apply a softmax function.
   <img width="877" height="248" alt="image" src="https://github.com/user-attachments/assets/fd4747d8-a1f2-4a47-aa6e-d82abcf405dc" />

## 7. Train Loss and Test Loss visualisation
  **Training Loss vs Epochs**
   
  <img width="576" height="432" alt="Train_loss" src="https://github.com/user-attachments/assets/dbc39509-1485-44b7-b2d7-402315951720" />
    
  **Test Loss vs Epochs**
   
  <img width="576" height="432" alt="Test_loss" src="https://github.com/user-attachments/assets/4a154df3-6fa7-41f8-a252-b2d1a6412703" />
  
## 8. Prediction on random set of  64 images from test data.

  <img width="479" height="469" alt="Predictions" src="https://github.com/user-attachments/assets/717f01cf-ae65-4b93-9a03-b8ee42159f9d" />



