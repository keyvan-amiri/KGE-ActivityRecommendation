# KGE-ActivityRecommendation
This is the supplementary reposititory for the paper:
"Knowledge Graph Completion for Activity Recommendation in Business Process Modeling"

We are currently cleaning up and refatcoring our code, it will be available at latest on 25.11.2023.

# Installation
1. Create a python environment, and activate it: `python -m venv kge_git`  `source kge_git/bin/activate` 
As it is mentioned in our paper, we relied on the PyTorch-based library [libKGE](https://github.com/uma-pi1/kge) to apply knowledge graph embedding models. Therefore, first you need to install libKGE based on the guide provided [here](https://github.com/uma-pi1/kge#quick-start).
Once libKGE is installed you can navigate to the root folder, and observed that it includes a folder called **local**. We use this folder for our experiments. To do so you need to clone this github repository including the datasets used in our experiments as well as the best configuration files for each KGE model.
