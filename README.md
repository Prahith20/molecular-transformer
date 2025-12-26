# Generative Molecular Transformer

An autoregressive Transformer model implemented from scratch in PyTorch to generate valid chemical structures (SMILES strings).

![Project Status](https://img.shields.io/badge/Status-Complete-green)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![RDKit](https://img.shields.io/badge/Cheminformatics-RDKit-blue)

## Project Overview
This project applies Deep Generative Modeling to drug discovery. By treating molecular strings (SMILES) as a language, I trained a Transformer to predict the probability distribution of the next atom in a sequence.

Unlike standard implementations that rely on pre-built `nn.Transformer` layers, this project manually implements the core mechanisms—**Multi-Head Self-Attention**, **Causal Masking**, and **Positional Embeddings**—to demonstrate a granular understanding of the architecture.

## Key Features
* **Manual Transformer Architecture**: Custom implementation of Query/Key/Value projections and scaled dot-product attention.
* **Causal Masking**: Implemented an upper-triangular mask to enforce the autoregressive property (preventing information leakage from future tokens).
* **Chemical Validation**: Integrated **RDKit** to validate the valency and ring integrity of generated molecules.
* **Tokenization**: Custom tokenizer handling the specific vocabulary of the Tox21 dataset (112 unique tokens).

## Results
The model was trained for 50 epochs on the Tox21 dataset.
* **Validation Loss (NLL):** Decreased from **64.78** to **~27.5**.
* **Reconstruction Accuracy:** Achieved **~91.6%** next-token prediction accuracy.
* **Generation Validity:** **~65%** of chemically sampled sequences were valid molecules (verified via RDKit).


## Attribution & References
This project is an adaptation and extension of the Deep Generative Modeling course material provided by **Jakub M. Tomczak**.

* **Original Framework:** [intro_dgm](https://github.com/jmtomczak/intro_dgm) by J.M. Tomczak.
* **Modifications:** Analysis of causal masking mechanics, custom visualization pipelines, and extended hyperparameter documentation.

## License
MIT License
