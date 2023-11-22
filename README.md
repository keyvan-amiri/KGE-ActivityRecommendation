# KGE-ActivityRecommendation
This is the supplementary reposititory for the paper:
"Knowledge Graph Completion for Activity Recommendation in Business Process Modeling"

We are currently cleaning up and refatcoring our code, it will be available at latest on 25.11.2023.

# Installation libKGE library
As it is mentioned in our paper, we relied on the PyTorch-based library [libKGE](https://github.com/uma-pi1/kge) to apply knowledge graph embedding models. Therefore, you need to install libKGE:
1. Clone libkge (i.e., `git clone https://github.com/uma-pi1/kge.git`) to have all the library's contents in the root folder **kge**.
2. Navigate to **kge** folder: `cd kge` (We recommend to create a virtual python environment using: `python -m venv kge_work` `source kge_work/bin/activate` for better handling of all dependencies between libraries.)
3. Install all requirements: `pip install -e .`
4. Make yourself familiar with main functionalities of libKGE using the documentation provided on the [libKGE repository](https://github.com/uma-pi1/kge). 
# Adding datasets, and configuration files
In the folder **kge**, you can observe that it includes a folder called **local**. We use this folder for all our experiments. To do so you need to clone this github repository including the datasets used in our experiments as well as the best configuration files for KGE models.
All datasets used in our experiment can be found in the folder **bpmai datasets** within current repository, while the following table provides additional information about these datasets:

| Header 1 | Header 2 |
|----------|----------|
| bpmai_lastrev_caise_onlyAfter  | Translation approach **1** without augmentation | 
| bpmai_lastrev_caise_onlyAfter2 | Augmented dataset for translation approach **1**| 
| bpmai_lastrev_caise | Translation approach **2a** without augmentation | 
| bpmai_lastrev_caise2 | Augmented dataset for translation approach **2a** |
| bpmai_lastrev_caise_inProcess | Translation approach **2b** without augmentation | 
| bpmai_lastrev_caise_inProcess2 | Augmented dataset for translation approach **2b** | 

All configuration files that are used for training KGE models in our experiment can be found in the folder **configs** within current repository. Similar to the dataset folder, here we have separate subfolders for all datasets used in our experiments.
For training, and evaluation of KGE models you need to copy all dataset folders to the folder called **data** within the root folder **kge**. For more information, please refer to ["use your own dataset"]([https://github.com/uma-pi1/kge](https://github.com/uma-pi1/kge#use-your-own-dataset) on github repository of libKGE.
