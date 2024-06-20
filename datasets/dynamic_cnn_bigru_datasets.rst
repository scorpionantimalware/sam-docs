.. _doc_dynamic_cnn_bigru_datasets:

Dynamic CNN BiGRU Datasets
==========================

The following table describes the datasets used in the Dynamic CNN BiGRU model.

.. list-table:: Dynamic CNN BiGRU Datasets
   :widths: 25 25 25 25 50 50
   :header-rows: 1

   * - Dataset Name
     - Benign Samples
     - Malicious Samples
     - Related Papers
     - Links
     - Extraction Script Link
   * - mal2019
     - 0
     - 7107
     - `Classification of Methamorphic Malware with Deep Learning (LSTM) <http://dx.doi.org/10.1109/SIU.2019.8806571>`_, `A Benchmark API Call Dataset For Windows PE Malware Classification <https://www.researchgate.net/publication/332877263_A_Benchmark_API_Call_Dataset_For_Windows_PE_Malware_Classification>`_.
     - https://github.com/ocatak/malware_api_class
     - `Dynamic_datasets_formatting_and_EDA.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/Dynamic_datasets_formatting_and_EDA.ipynb>`_
   * - malbehav
     - 1285
     - 1285
     - `API-MalDetect: Automated malware detection framework for windows based on API calls and deep learning techniques <https://doi.org/10.1016/j.jnca.2023.103704>`_
     - https://github.com/mpasco/MalbehavD-V1
     - `Dynamic_datasets_formatting_and_EDA.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/Dynamic_datasets_formatting_and_EDA.ipynb>`_
   * - friendllcc
     - 2000
     - 2000
     - `A novel deep framework for dynamic malware detection based on API sequence intrinsic features <https://doi.org/10.1016/j.cose.2022.102686>`_
     - https://github.com/friendllcc/Malware-Detection-API-Sequence-Intrinsic-Features
     - `Dynamic_datasets_formatting_and_EDA.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/Dynamic_datasets_formatting_and_EDA.ipynb>`_
   * - oliveira
     - 1079
     - 42,797
     - `Behavioral Malware Detection Using Deep Graph Convolutional Neural Networks <https://doi.org/10.36227/techrxiv.10043099.v1>`_
     - https://ieee-dataport.org/open-access/malware-analysis-datasets-api-call-sequences
     - `Dynamic_datasets_formatting_and_EDA.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/Dynamic_datasets_formatting_and_EDA.ipynb>`_
   * - allan
     - 100
     - 452
     - `Windows PE API calls for malicious and benigin programs <http://dx.doi.org/10.13140/RG.2.2.14417.68960>`_
     - https://www.researchgate.net/publication/336024802_Windows_PE_API_calls_for_malicious_and_benigin_programs/link/5d8b6a4e92851c33e9395c89/download?_tp=eyJjb250ZXh0Ijp7ImZpcnN0UGFnZSI6InB1YmxpY2F0aW9uIiwicGFnZSI6InB1YmxpY2F0aW9uIn19
     - `Dynamic_datasets_formatting_and_EDA.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/Dynamic_datasets_formatting_and_EDA.ipynb>`_
   * - zenodo
     - 946
     - 891
     - `Dynamic Malware Analysis kernel and user-level calls <https://doi.org/10.5281/zenodo.1203289>`_
     - https://zenodo.org/records/1203289
     - `zenodo_formatted_dataset.ipynb <https://github.com/scorpionantimalware/sam-cnn-bigru-dynamic-pe-classifier/blob/master/data/zenodo_formatted_dataset.ipynb>`_
