# Performance Analysis of Knowledge Representation Learning (KRL) on Linked Building Data (LBD)


[![PyPI pyversions](https://img.shields.io/pypi/pyversions/pykeen)](https://img.shields.io/pypi/pyversions/pykeen)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This repository accompanies my PhD thesis and enables reproduction of the key results.

## Overview

In this work we investigate the performance of five KRL models on Linked Building Data LBD (BIM-Based Knowledge Graphs)Two publicly available
BIM-KGs datasets were used in these experiments. The overall goal was not to identify the best KRL model configurations. Instead, the study examined more closely how model performance can be affected by modifications to the training step, selection of hyper-parameters and their optimization. The experimental results were used to define the prerequisites for integrating KRL with BIM-KGs in a domain-independent framework. This means that although a building automation use case is used to formulate the framework, it can be applied to other AEC/FM
domains such as heritage, quantity-takeoff and energy analysis. The framework aims to enhance trust, reproducibility and understanding
of KRL-based methods among AEC/FM stakeholders and researchers.

The models we investigate are: 

- [TransE](https://papers.nips.cc/paper/2013/hash/1cecc7a77928ca8133fa24680a88d2f9-Abstract.html)
- [TransH](https://ojs.aaai.org/index.php/AAAI/article/view/8870)
- [RotatE](https://arxiv.org/abs/1902.10197)
- [DistMult](https://arxiv.org/abs/1412.6575)
- [ComplEX](https://arxiv.org/abs/1606.06357)

With the following datasets being used

- [Rice Hall at University of Virginia](https://dl.acm.org/doi/10.1145/2993422.2993577)
- [Soda Hall at University of Carlifonia, Berkeley](https://dl.acm.org/doi/10.1145/2993422.2993577)

These datasets are representative examples of how the Brick ontology can be used to model real buildings. The datasets were available online at the official [BRICK schema website](https://brickschema.org/resources/#original-brick-reference-models) in early 2023 and were archived locally for this research however the links went down early this year (2024) possibly due to lack of maintenance. Details about these datasets can be found in this [paper](https://dl.acm.org/doi/10.1145/2993422.2993577) by the BRICK schema authors.


## Running the experiments

The required project dependencies are listed in ```requirements.txt``` at the root of the project directory and can be installed automatically by running the first cell of the jupyter notebooks. This cell prepares a virtual environment and thereafter installs the dependencies needed to run the experiments. Depending on your operating system, make sure you activate the virtual environment after running this cell.

The experiments rely on the [PyKEEN](https://github.com/pykeen/pykeen) package, which uses [PyTorch](https://pytorch.org/) behind the scenes for gradient computation. A GPU enabled version of pytorch is recommended if you want to run these experiments. CPU is fine but will be slow.

The models are provided as part of the the PyKEEN package so there is no need to download them separately. 

The datasets are provided in the subfolders encapsulated in the ```Datasets``` folder. Each subfolder is give a custom name to identify the dataset and in it contains the ```input.ttl``` file.

## Reproducing Experiments

This repository contains code to preprocess the ```input.ttl``` (BIM-KG) files and replicate the experiments detailed in the thesis. Each experiment is run using a Jupyter notebook and an associated YAML configuration file. The folder structure of the project is quite opinionated based on the jupyter notebooks and as described therein but you are free to reorganize things as you see fit. 

Please note that the results of the experiments will be saved in the **results** directory at the root of each study's folder.

### Experiments: A study on training setup choices

The initial series of experiments aims to evaluate the influence of different categorical decisions related to the training configuration of KRL models. These experiments vary the optimizer, training objective function and finally considering the exclusion or inclusion of inverse relationships in the BIM-KGs.

### Experiments: A study on HPO choices

The HPO experiments perform 100 repeats to find the optimal hyper parameters for a given dataset and model combination.

## Citation

Please consider citing the paper for this repo if you find it useful:

```
TO BE CONFIRMED
```

**License**

- [Apache 2.0](https://github.com/AstraZeneca/awesome-drug-discovery-knowledge-graphs/blob/master/LICENSE)
