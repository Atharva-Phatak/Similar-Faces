# Similarity-Learning-with-Siamese-Nets
Implementation of Siamese Neural Networks with contrastive loss for similarity learning.

## Siamese Neural Networks

Siamese networks are a special type of neural network architecture. Instead of a model learning to classify its inputs, the neural networks learns to differentiate between two inputs. It learns the similarity between them.

### Architecture

A Siamese neural network consists of two identical neural networks each taking as input one of the two input images.The last layers of the two networks are then fed to a contrastive loss function , which calculates the similarity between the two images. I have made an illustration to help explain this architecture.

![architecture](https://cdn-images-1.medium.com/max/750/1*XzVUiq-3lYFtZEW3XfmKqg.jpeg)

* There are two sister networks, which are identical neural networks, with the exact same weights.
* Each image in the image pair is fed to one of these networks.
* The networks are optimised using a contrastive loss function(we will get to the exact function).

## Contrastive Loss Function

The objective of the siamese architecture is not to classify input images, but to differentiate between them. So, a classification loss function (such as cross entropy) would not be the best fit. Instead, this architecture is better suited to use a contrastive function.
Intuitively, this function just evaluates how well the network is distinguishing a given pair of images.

The contrastive loss function is given as below : 

![loss](https://cdn-images-1.medium.com/max/1000/1*tzGB6D97tHWR_-NJ8FKknw.jpeg)

where Dw is defined as the euclidean distance between the outputs of the sister siamese networks.

Euclidean Distance is given by :

![title](https://cdn-images-1.medium.com/max/1000/1*6JCpYpYVJnpgYwupVIHSpg.jpeg)

where Gw is the output of one of the sister networks. X1 and X2 is the input data pair.

## The Dataset

The dataset which I used in this implementation is AT&T dataset. You can download it here : [link](http://www.cl.cam.ac.uk/Research/DTG/attarchive:pub/data/att_faces.zip)
The dataset contains images of 40 subjects from various angles.

Here are some images from dataset

![img](https://cdn-images-1.medium.com/max/750/1*31e_wjr4HgKN80xFF4QIBg.png)

You can use any dataset , just enure that each class has its own indiviudal folder , so that you can use PyTorch image folder functionality.

## Requirements

* Python 3.6
* PyTorch 1.0
* Torchvision
* Numpy
* Matplotlib
* Jupyter Notebook

## About training 

I trained the model for 200 epochs on google colab. You can run the notebook on your local system too , just comment out the code where google dive is mounted and ensure you give proper training path to the test and train image data.

Here is what my loss looked like after 200 epochs:

![img](https://github.com/Atharva-Phatak/Similarity-Learning-with-Siamese-Nets/blob/master/loss_plot.png)

Haven fun with the notebook!! 
