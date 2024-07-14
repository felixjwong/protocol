<!--
*** Thanks for checking out this README Template. If you have a suggestion that would
*** make this better, please fork the repo and create a pull request or simply open
*** an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
-->




<!-- PROJECT LOGO -->
<br />
<p align="center">

  <h3 align="center">An explainable deep learning platform for molecular discovery</h3>

  <p align="center">
    Supporting code for the paper
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of contents

* [About this repository](#about-this-repository)
* [Aims](#aims)
* [Using this repository](#using-this-repository)
  * [Checkpoint files](#checkpoint-files)
  * [Chemprop usage](#chemprop-usage)
  * [Key files](#key-files)
* [Contact](#contact)




<!-- ABOUT THE PROJECT -->
## About this repository

The files in this repository allow for repeat analyses of those described in the paper "An explainable deep learning platform for molecular discovery", which is a protocol paper accompanying the paper <i><a href="https://www.nature.com/articles/s41586-023-06887-8">Discovery of a structural class of antibiotics with explainable deep learning</a></i>. The code requires <a href="https://github.com/chemprop/chemprop">ChemProp</a> and Python with the appropriate packages installed, as indicated in the paper. In particular, please ensure that at least the following two packages are installed:
<ul>
<li><a href="https://github.com/chemprop/chemprop">Chemprop</a> (commit 2bcfcfe47b704d73ce7c48f177254fedeb5c0316 was used)</li>
<li><a href="https://www.rdkit.org/">RDKit</a> (version 2023.09.6 was used)</li>
</ul>
Typical installation times range from minutes to hours. Details on installation and the packages required are provided in the protocol.

For running the computational steps provided in the accompanying Jupyter notebook ("Tutorial.ipynb"), refer to the "requirements.txt" file in this repository for Python packages required and corresponding version numbers. 

<!-- Aims -->
## Aims

The accompanying protocol presents an explainable deep learning platform that enables vast chemical spaces to be mined and the chemical substructures underlying predicted activity to be identified. The platform relies on Chemprop, a software package implementing graph neural networks as a deep learning model architecture. In contrast to similar approaches, graph neural networks have been shown to be state-of-the-art for molecular property prediction. Focusing on discovering structural classes of antibiotics, the protocol provides guidelines for experimental data generation, model implementation, and model explainability and evaluation. The protocol does not require coding proficiency or specialized hardware, and it can be executed in as little as 1-2 weeks, starting from data generation and ending in the testing of model predictions. The platform can be broadly applied to discover structural classes of other small molecules, including anti-cancer, anti-viral, and senolytic drugs, as well as to discover structural classes of inorganic molecules with desired physical and chemical properties. 


<!-- GETTING STARTED -->
## Using this repository

### Checkpoint files

Each of the folders entitled "sa_models", "hep_models", "hskmc_models", and "imr_models" contains 10 Chemprop checkpoints generated as described in the protocol. These correspond to trained ensembles of models predicting antibiotic activity against <i>Staphylococcus aureus</i>, cytotoxicity against HepG2 cells, cytotoxicity against human primary skeletal muscle cells, and cytotoxicity against IMR-90 cells. Training was performed for each model with a set of 2,335 compounds, as provided in the .csv file in each folder. These 2,335 compounds refer to the de-duplicated compounds in  MicroSource Discovery Systems' Pharmakon and Natural Products Collections, as detailed in the protocol. 

### Chemprop usage 

The protocol guides readers to train and deploy their own Chemprop models. Successful execution of the protocol should result in files similar to those in this repository. This repository is provided in order to further guide readers in navigating the protocol. 

### Computational steps

This repository provides a Jupyter notebook file, "Tutorial.ipynb", for running all computational steps described in the protocol. Execute each cell in this notebook in sequence, and note the dependencies on different files in this repository. 

### Key files

Key files are detailed as part of the protocol, but it is helpful to note the following: 

<ul>
<li>Tutorial.ipynb: a Jupyter notebook file executing the computational steps described in the protocol using the files provided as part of this repository.</li>
<li>models/train.csv: A CSV file containing the SMILES strings and activity values of compounds in the training set. The default files provided are training sets of 2,335 compounds, which are a subset of the screening data <a href="https://www.nature.com/articles/s41586-023-06887-8">originally published in our work</a>. These files, one each for antibiotic activity against <i>Staphylococcus aureus</i>, cytotoxicity against HepG2 cells, cytotoxicity against human primary skeletal muscle cells, and cytotoxicity against IMR-90 cells, correspond to Supplementary Datasets 1-4 in the protocol. 
</li>
<li>models/hyperparameters.json: A JSON file containing key hyperparameters specifying the architectures of the Chemprop models used. 
</li>
<li>test.csv: A CSV file containing the SMILES strings of 100,000 compounds from the Broad Institute's 800K database, for which Chemprop predictions will be made. This file corresponds to Supplementary Dataset 5 in the protocol. 
</li>
<li>test_results: A CSV file containing the results from running chemprop_predict on test.csv using the models in "sa_models".
</li>
<li>examples.csv: A CSV file containing a single SMILES string with a high antibiotic prediction score and a rationale that can be calculated. 
</li>
<li>examples_rationales: A CSV file containing the results from running chemprop_interpret on hit.csv using the models in "sa_models".
</li>
<li>environment.yml: A file listing the Python dependencies needed for successful installation of Chemprop. 
</li>
</ul>



<!-- CONTACT -->
## Contact

For questions or comments about this repository, please reach out to felix j wong at gmail (no spaces, add domain name). 

