# Master's Thesis Project
## Unsupervised Image Classification Using Domain Adaptation Via the Second Order Statistics
![screen](misc/screen.png)

## Overview
This master's thesis project was conducted with Scania and Uppsala University during spring/summer of 2022.
CORAL (COrrelation ALignment) is an unspuervised domain adaptation method which minimizes the domain shift
by aligning the second order statistics of the source and target deep features. A linear classifier will then
adapt to the target domain by learning in a supervised manner on the aligned source deep features.

### The deep learning packages
The shallow CORAL method was implemented in Keras at the begining of the project, but pytorch was later favoured
for the deep CORAL model because its low-level accessability. Therefore you will find two folders, a keras folder
for the shallow CORAL method, and a pytorch folder for the deep CORAL model

## Installation

### Dev
I use python pip virtual environment and conda as a primary tools for 
development. See [requirements.txt](requirements.txt) for full specification of 
platform, python and dependency packages. Run `pip install -r 
requirements.txt` with [virtualenv](https://virtualenv.pypa.io/en/stable/).

## Usage

### Index

You can now preprocess data (look at [this](articlix/index/clean.ipynb)).  
Then `python main.py --dfpath="data/clean_articles.h5" 
--indexpath="data/index.json" --workers=8 index`.

### Data

[Where to find prepared data](data/where.txt)

### Search

[Examples](articlix/search/search.ipynb)

### Web interface

Run `python main.py web_interface`. Then you can find page 
at localhost on port 8080.

### Evaluation

You will need assessments log file, obtained from server.  
[DCG](articlix/evaluation/dcg.ipynb)

## Report

[Web](http://35.227.117.218/)  
[Slides](https://docs.google.com/presentation/d/e/2PACX-1vT5Qs8ly5csvfrqpafVQ4H0pQTr0U1S1XYF1gudEBVSxXaMwgUgVN4zEBDhO11j3d2Td7VmJ_PK6VGJ/pub?start=false&loop=false&delayms=3000)  
[Report](misc/articlix-final-report.pdf)

## License

[MIT](LICENSE)
