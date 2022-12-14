# Master's Thesis Project
## Image Classification Using Usupervised Domain Adaptation Via the Second Order Statistics

## Overview
This Master's thesis project was conducted at Scania and Uppsala University during the spring/summer of 2022.

## The deep learning libraries
The shallow CORAL method was implemented in Keras at the beginning of the project. Later, Pytorch was favored because its low-level accessibility was needed for reimplementing the deep CORAL model. Therefore, there is a Keras folder for the shallow CORAL method, and a PyTorch folder for the deep CORAL model, with their separate dependency requirement

## Shallow CORAL
CORAL COrrelation ALignment) from "Return of Frustratingly Easy Domain Adaptation" by Sun et. al. ([link](https://arxiv.org/pdf/1511.05547.pdf)) is an unsupervised domain adaptation method that minimizes the domain shift by aligning the second-order statistics of the source features with that of the target features. A linear classifier will then adapt to the target domain by learning in a supervised manner on the aligned source deep features.

### Required environment shallow CORAL
See [requirements_sc.txt](requirements_sc.txt) for full specification of 
platform, python and dependency packages. Run `pip install -r 
requirements_sc.txt` to install dependencies.

### Source Code shallow CORAL
- folders
    - `deep_features` __ contains deep features of the datasets
    - `plots` ___________ contains plots
    - `weights` _________ contains model parameters from previous training sessions
- scripts 
    - `main.py` ____________ main script
    - `library.py` _________ creates and preprocess data, and other utility functions
    - `coral.py` ___________ computes the linear transformation A for the CORAL method
    - `data_loader.py` ____ loads Cifar-10, camera, and LiDAR datasets 
    - `nn_cifar_10.py` ____ neural net model for pretraining on Cifar-10
    - `nn_classifier.py` __ linear classifier model

### Usage shallow CORAL
1) In `main.py` there are boolean vaiables that control which code to be executed load weights from pretraining on Cifar-10 dataset to the neural network by setting `load_weights = True` in the `train_cifar10` function.
2) 
3) Setting `do_CORAL = True` will align the camera deep features extracted from the last layer of the CNN in `train_cifar10`. Train the linear classifier or load weights to the classifier by either setting `load_weights = False` or `load_weights = True` in the `shallow_CORAL` function.
4) Check the main function to check that the code both functions will be executed.
5) Set `plotting = True` to plot TSNE plots and a confusion matrix.

## Deep CORAL
Deep CORAL from "Deep CORAL: Correlation Alignment for Deep Domain Adaptation" by Sun, B. & Saenko, K. ([link](https://arxiv.org/pdf/1607.01719.pdf)) constructs a joint loss function of the CORAL loss and the classification loss such that a convolutional neural net learns a deep, robust representation of the domain adaptation task.

### Required environment Deep CORAL
See [requirements_dc.txt](requirements_dc.txt) for full specification of 
platform, python and dependency packages. Run `pip install -r 
requirements_dc.txt` to install dependencies.

### Source code deep CORAL
- folders
    - `data` __________ contains the Cifar-10 dataset
    - `models` ________ contains model parameters from succesful training runs
    - `plots` _________ contains plots generated by plot_trainstats.py
    - `train_stats` __ contrains training history
- scripts
    - `cnn_torch_no_coral.py` ____ neural net model for supervised learning
    - `cnn_torch.py` ______________ neural net model for unsupervised domain adaptation
    - `confusion_matrix.py` ______ creates and plots a confusion matrix
    - `coral.py` ___________________ computes the CORAL loss
    - `data_loader_our_data.py` __ loads the Cifar-10, camera, and LiDAR data
    - `deep_coral.py` _____________ main script to train a DA model from `cnn_torch.py`, and to perform hyperparameter tuning of lambda
    - `no_deep_coral.py` __________ main script for supervised training of neural net model from `cnn_torch_no_coral.py` on camera data
    - `our_utils.py` _______________ create and preprocess camera and LiDAR datasets
    - `plot_trainstats.py` ________ a range of code snippets that plots training metrics and results from the hyperparameter tuning
    - `target_accuracy.py` ________ computes classification accuracy of a model on the LiDAR test data
    - `plot_dataset_images.py` ____ creates and plots a collage of ten images per class, in one image.

### Usage Deep CORAL
1) In the main function of `deep_coral.py`, there are several boolean variables that controls which code will be executed.
    - `hparamtuning` __ hyperparameter tuning on lambda
    - `train_model` ___ train model from `cnn_torch.py` with selected hyperparameter lambda
    - `load_model` ____ load model parameters from previous training session
    - `eval_test` _____ evaluate a model on test data
    - `tsneplot` ______ plots TNSE figures
    - `conf_matrix` ___ plots confusion matrix
3) The script `no_deep_coral.py`, trains a model in a supervised manner to finetune the pretrained model on the camera dataset.
4) In the main function of `no_deep_coral.py`, there are three booleans variables that controls which code will be executed.
    - `train_model` __ supervised training of the model from `cnn_torch_no_coral.py` on camera dataset
    - `load_model`____ loads model parameter from a previous training session
    - `histplot`______ plots training history

## Report 
[Slides](final_presentation.pptx)  
[Report](thesis_paper.pdf)
