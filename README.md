# Master's Thesis Project
## Unsupervised Image Classification Using Domain Adaptation Via the Second Order Statistics
![screen](misc/screen.png)

## Overview
This master's thesis project was conducted with Scania and Uppsala University during spring/summer of 2022.
CORAL (COrrelation ALignment) from "Return of Frustratingly Easy Domain Adaptation" by Sun et.al. [link] (https://arxiv.org/pdf/1511.05547.pdf) is an unspuervised domain adaptation method which minimizes the domain shift
by aligning the second order statistics of the source and target deep features. A linear classifier will then
adapt to the target domain by learning in a supervised manner on the aligned source deep features.

### The deep learning packages
The shallow CORAL method was implemented in Keras at the begining of the project, but pytorch was later favoured
for the deep CORAL model because its low-level accessability. Therefore you will find two folders, a keras folder
for the shallow CORAL method, and a pytorch folder for the deep CORAL model

### Required environment
See [requirements.txt](requirements.txt) for full specification of 
platform, python and dependency packages. Run `pip install -r 
requirements.txt` to install dependencies.

### Source Code
1. Shallow CORAL
2. Deep CORAL

## Usage shallow CORAL
1) In `main.py` load pretrained weights to the neural network by setting `load_weights = True` in the `train_cifar10` function
2) Train the linear classifier or load weights to the classifier by either setting `load_weights = False` or `load_weights = True` in the `shallow_CORAL` function.


## Report

[Web](http://35.227.117.218/)  
[Slides](https://docs.google.com/presentation/d/e/2PACX-1vT5Qs8ly5csvfrqpafVQ4H0pQTr0U1S1XYF1gudEBVSxXaMwgUgVN4zEBDhO11j3d2Td7VmJ_PK6VGJ/pub?start=false&loop=false&delayms=3000)  
[Report](misc/articlix-final-report.pdf)

## License

[MIT](LICENSE)
