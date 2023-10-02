# Instructions
1. Begin by downloading the Test_Coin.ipynb file.
2. Upload it to Colab and configure the environment to utilize the T4 GPU.
3. Execute the notebook.

# Approaches
Two different approaches were explored during testing:

* Implementation using a U-net Model.
* Implementation utilizing the Hough Transform method.


## U-Net Model
I decided to employ the U-net neural network architecture for the specific segmentation task, known for its effectiveness in image segmentation and feature extraction.

This U-Net model consists of a multi-level structure with four levels of blocks. Each block includes a pair of convolutional layers with batch normalization and ReLU activation functions. There is one additional max-pooling layer in the encoding part, while in the decoding part, up-convolutional layers are utilized instead.

In light of the dataset's lack of images, a deliberate strategy was employed to incorporate augmentation methods. This strategic decision was motivated by the need to mitigate issues related to overfitting and underfitting. To ensure uniform application of the desired alterations to input images and their corresponding ground truths, a sophisticated approach was adopted involving customising Transform modules

The dataset was methodically split into two segments, with a distribution ratio of 70% for training data and 30% for testing data. This division was meticulously designed to facilitate effective model training and comprehensive testing. 

In the context of this project, the choice of loss function fell upon MSE (Mean Squared Error) due to its suitability for the task. Additionally, RMSProp was selected as the optimizer to fine-tune the model's performance.

## Hough Transform
An alternative approach was explored during the experimentation phase, which diverged from deep learning methodologies and instead leveraged the OpenCV Hough Transform function for circle detection.

Although this approach resulted in a slightly lower accuracy, it demonstrated a notable advantage in terms of execution speed, making it a pragmatic choice for specific scenarios.