# KGE-ActivityRecommendation
This is the supplementary reposititory for the paper:
"Knowledge Graph Completion for Activity Recommendation in Business Process Modeling"

We are currently cleaning up and refatcoring our code, it will be available at latest on 25.11.2023.

# Installation libKGE library
We used the PyTorch-based library [libKGE](https://github.com/uma-pi1/kge) to apply knowledge graph embedding models. Therefore, you need to install libKGE to replicate our study:
1. Clone libkge (i.e., `git clone https://github.com/uma-pi1/kge.git`) to have all the library's contents in the root folder **kge**.
2. Navigate to **kge** folder: `cd kge`

   We recommend to create a python environment using: `python -m venv kge_work` `source kge_work/bin/activate` to avoid any discrepency between libraries.
3. Install all requirements: `pip install -e .`
4. Make yourself familiar with the main functionalities of libKGE using the documentation provided on the [libKGE repository](https://github.com/uma-pi1/kge). 

# Adding datasets, and configuration files
The **kge** folder includes a folder called **local** which will be used for all our experiments (see: https://github.com/uma-pi1/kge/tree/master/local). In order to replicate our results, you need to:
1. Clone this github repository: `git clone https://github.com/keyvan-amiri/KGE-ActivityRecommendation.git`
2. Run `mv KGE-ActivityRecommendation local/` to move the folder **KGE-ActivityRecommendation** (i.e., current repository) into **kge/local**.
3. Navigate to **KGE-ActivityRecommendation** `cd local/KGE-ActivityRecommendation` and run `python file_transfer.py` to add all datasets, and configuration files to the libKGE that you have already cloned.

Current github repository includes the datasets used in our experiments as well as the best configuration files for KGE models. 

All datasets used in our experiment can be found in the folder **bpmai datasets** within current repository, while the following table provides additional information about these datasets:

| Folder name | Corresponding dataset in the paper |
|----------|----------|
| bpmai_lastrev_caise_onlyAfter  | Translation approach **1** without augmentation | 
| bpmai_lastrev_caise_onlyAfter2 | Augmented dataset for translation approach **1**| 
| bpmai_lastrev_caise | Translation approach **2a** without augmentation | 
| bpmai_lastrev_caise2 | Augmented dataset for translation approach **2a** |
| bpmai_lastrev_caise_inProcess | Translation approach **2b** without augmentation | 
| bpmai_lastrev_caise_inProcess2 | Augmented dataset for translation approach **2b** | 

<!-- This is not remaining of the table. -->
All configuration files that are used for training KGE models in our experiment can be found in the folder **configs** within current repository. Similar to the dataset folder, here we have separate subfolders for all datasets used in our experiments.

For training, and evaluation of KGE models you need to copy all dataset folders to the folder **data** within the root folder **kge**. For more information, please refer to ["use your own dataset"](https://github.com/uma-pi1/kge#use-your-own-dataset) on github repository of libKGE. You also need to copy all configuration files to the related folders in the folder **data** within the root folder **kge**. For more information, please refer to ["Using LibKGE"](https://github.com/uma-pi1/kge#using-libkge). To simplify this process, we have provided **file_transfer.py** which takes care of adding all dataasets, and configuration files.

# Preprocessing datasets
Each dataset consists of three files **train.txt**, **valid.txt** and **test.txt** each of them including all relevant triples like this one:

quotationsent_840044706_rev15	after	quotationrecieved_840044706_rev15

In order to train and evaluate KGE models, you need to preprocess these files: first navigate to **kge/data** folder, and then run the preprocessing file while you provide the name of the dataset. For instance, for preprocessing the augmented version of translation approach 2a, you need to run: `python preprocess_default.py bpmai_lastrev_caise2`.
