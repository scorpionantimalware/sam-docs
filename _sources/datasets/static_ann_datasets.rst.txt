.. _doc_static_ann_datasets:

Static Artificial Neural Network Datasets
=========================================

We have a base datasets related to 
`EMBER: An Open Dataset for Training Static PE Malware Machine Learning Models <https://arxiv.org/abs/1804.04637v2>`_ 
paper called EMBER. You can find the datasets inside 
`elastic/ember <https://github.com/elastic/ember>`_ repository. We maintained our version of the ember repository 
`scorpionantimalware/ember <https://github.com/scorpionantimalware/ember>`_.

`EMBERSim: A Large-Scale Databank for Boosting Similarity Search in Malware Analysis <https://arxiv.org/abs/2310.01835>`_ 
paper from NIPS conference 2023 that provide some enchancement inside 
`CrowdStrike/embersim-databank <https://github.com/CrowdStrike/embersim-databank>`_ 
repository.

.. list-table:: Static Artificial Neural Network Datasets
   :widths: 25 25 25 25 50 50
   :header-rows: 1

   * - Dataset Name
     - Size
     - Benign Samples
     - Malware Samples
     - Related Papers
     - Links

   * - ember-dataset (Public)
     - 1.6 GB JSONLs or 5 GB vectorized
     - 300,000 Train + 100,000 Test
     - 300,000 Train + 100,000 Test
     - `EMBER: An Open Dataset for Training Static PE Malware Machine Learning Models <https://doi.org/10.48550/arXiv.1804.04637>`_
     - https://www.kaggle.com/datasets/pwn3xt/ember-dataset

.. note:: We use the EMBER dataset to train our base models and then we use our datasets to fine-tune the models.
