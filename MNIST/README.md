# MNIST_v1_DNN

This is a project in which we will be detecting the digit present in the provided image using tensorflow and python.
> *Note : clone this repo and then add it to google drive. Execute the file in 'colab notebooks' folder. You also need to mount the drive in google colab*. Follow this tutorial to learn how to mount drive : https://youtu.be/PA1WPr0o_DY

# The data - MNIST

The MNIST dataset consists of thousands of images of handwritten digits. It is present in the tensorflow library

![mnist](https://th.bing.com/th/id/OIP.XR9gnceJSVEoRJOVvMjU8gHaFj?pid=ImgDet&rs=1)

Every image is of size 28 x 28 i.e there are a total of 784 pixels in a single image of the dataset with 28 rows and 28 columns.
All the images are in **grayscale(black and white)**.

The digits range from 0 to 9. As the images are black and white every pixel has a value from 0 to 255. 0 means the pixel is black and 255 represents white pixels and all the value between 0 and 255 are different shades of grey, white and black.

## What is a neural network?

the definition says:
>A computer system modelled on the human brain and nervous system

This means that a neural network consists of neurons which are linked together and it tries to mimic the human brain 

>A neural network is a network or circuit of biological neurons, or, in a modern sense, an artificial neural network, composed of artificial neurons or nodes. Thus, a neural network is either a biological neural network, made up of biological neurons, or an artificial neural network, used for solving artificial intelligence problems.

<img src = "https://www.researchgate.net/profile/Facundo_Bre/publication/321259051/figure/fig1/AS:614329250496529@1523478915726/Artificial-neural-network-architecture-ANN-i-h-1-h-2-h-n-o.png" height = 325px width = 554px>

An artificial neural network consists of three parts

 - Input layer
 - Hidden layers
 - Output layer

All these layers consist of neurons. Every neuron consists of a value called the *activation of the neuron*.

### Input layer

The input layer consists of neurons which take in the data. For our case of image data the input layer will consist of pixels. Every neuron in the input layer takes in 1 pixel of the image. Therefore the input layer will consist of 784 neurons as there are 784 pixels in each image of our data. The activation of these neurons will be the value of the pixels i.e every pixel has a value between 0 and 255 all the neurons in the input layer represent a pixel of the image means the activation of the neuron is the pixel value of every pixel.

### Output Layer

The output layer consists of neurons which give us the output. In out case the output should be a digit form 0 to 9. Therefore the output layer consists of 10 neurons as there are 10 classes(digits 0 - 9). The activation of the neurons in the output layer give us the output. Every neuron in the output layer has an activation and the neuron which has the highest activation in the output layer is considered as the output. The activation of the neurons in the output layer depend on the neurons of the hidden layers.

### Hidden layers

Every other layer of neurons between the input layer and the output layer is called as hidden layer. this is where all the processing part takes place.

# Working of a neural network

<img src = "https://cdn-images-1.medium.com/max/1600/1*7mZxWa3zvTzdtFZFoHSqBg.jpeg" height = 256px width = 572px>

Every neuron in the first hidden layer is connected to every single neuron in the input layer. Just as it is shown in the picture above.

these connections are called __weights__

Every connection between one neuron and the particular neuron in the successive layer has a different value. 
>w(1), w(2), w(3), w(4), w(5), ..., w(n)

We also know the every neuron has an activation. The weights are multiplied with the activation of the respective neurons.
>w(1)a(1), w(2)a(2), w(3)a(3), ..., w(n)a(n)

*where 'w' represents the weight and 'a' represents the activation.*

After multiplying the weights and the activations they are all added and this summation value is equal to 'k' lets say. Now another value called bias('b') is added to 'k'. the bias value is a constant.

>[{w(1)a(1) + w(2)a(2) + w(3)a(3) + ... + w(n)a(n)} + b]

now the whole value is equal to 'y' lets say.

Now this value 'y' is substituted in a function called the **activation function**. This activation function takes in the 'y' value and the output of the activation function is a value ranged between 0 and 1. The output of the activation function is the activation of the neuron in the next layer.

<img src = "https://i.stack.imgur.com/9FVqo.png" height = 283px width = 388px>

Lets take the above example

the first neuron in the input layer has an activation 1 and the second neuron in the same layer has an activation also 1. The weights connecting the 2 neurons to the first neuron of the hidden layer are 0.8 and 0.2.

[(0.8 * 1) + (0.2 * 1)] = 1

now we add a bias to this value ('1') and then it is passed into an activation function and the output will be the activation of the 1st neuron of the hidden layer.

Some activation functions:
 - relu
 - sigmoid
 - softmax
 - tanh