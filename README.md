# Master's Thesis Project
### Unsupervised Image Classification Using Domain Adaptation Via the Second Order Statistics
![screen](misc/screen.png)

## Overview
This Master's thesis project was conducted at Scania and Uppsala University during spring/summer -22.

## The deep learning packages
The shallow CORAL method was implemented in Keras at the begining of the project, but pytorch was later favoured
for the deep CORAL model because its low-level accessability. Therefore you will find two folders, a keras folder
for the shallow CORAL method, and a pytorch folder for the deep CORAL model

## Required environment
See [requirements.txt](requirements.txt) for full specification of 
platform, python and dependency packages. Run `pip install -r 
requirements.txt` to install dependencies.

## Source Code
1. Shallow CORAL
    - folder: deep_features
    - folder: plots
    - folder: weights
    - main.py
    - library.py
    - coral.py
    - data_loader.py
    - losses.py
    - nn_cifar_10.py
    - nn_classifier.py
2. Deep CORAL
    - .py
    - .py
    - .py
    - .py


## Shallow CORAL
CORAL (COrrelation ALignment) from "Return of Frustratingly Easy Domain Adaptation" by Sun et. al. [link](https://arxiv.org/pdf/1511.05547.pdf) is an unspuervised domain adaptation method which minimizes the domain shift
by aligning the second order statistics of the source and target deep features. A linear classifier will then
adapt to the target domain by learning in a supervised manner on the aligned source deep features.

### Usage shallow CORAL
1) In `main.py` load weights from pretraining on Cifar-10 dataset to the neural network by setting `load_weights = True` in the `train_cifar10` function
2) Setting `do_CORAL = True` will align the camera deep features extracted from the last layer of the CNN in `train_cifar10`. Train the linear classifier or load weights to the classifier by either setting `load_weights = False` or `load_weights = True` in the `shallow_CORAL` function. 
3) Check the main function to check that the code both functions will be executed
4) Set `plotting = True` to plot TSNE plots and a confusion matrix.

## Deep CORAL
Deep CORAL from "Deep CORAL: Correlation Alignment for Deep Domain Adaptation" by Sun, B. & Saenko, K. [link](https://arxiv.org/pdf/1607.01719.pdf) constructs a joint loss function of the CORAL loss and the classification loss such that a convolutional neural net learns a deep, robust representation of the domain adaptation task.

### Usage Deep CORAL
1)
2)
3)
4)

## Report
[Web](http://35.227.117.218/)  
[Slides](https://docs.google.com/presentation/d/e/2PACX-1vT5Qs8ly5csvfrqpafVQ4H0pQTr0U1S1XYF1gudEBVSxXaMwgUgVN4zEBDhO11j3d2Td7VmJ_PK6VGJ/pub?start=false&loop=false&delayms=3000)  
[Report](misc/articlix-final-report.pdf)

## License

[MIT](LICENSE)
