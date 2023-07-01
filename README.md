# LCR-Rot-hop-ont-plus-plus
Knowledge Injection from an Ontology in a Neural Network for Aspect-Based Sentiment Classification

## Installation
- Set up environment:
  - Set up a conda environment using Python 3.10
  - Install the required packages: `pip install -r requirements.txt`
  - The code can be opened and edited in any editor, we used Visual Studio: https://code.visualstudio.com
- Set up data
  - Create a directory `data/raw` and download the [SemEval 2015](https://alt.qcri.org/semeval2015/task12/index.php?id=data-and-tools) and [SemEval 2016](https://alt.qcri.org/semeval2016/task5/index.php?id=data-and-tools) restaurant datasets, and the [ontology](https://github.com/KSchouten/Heracles/tree/master/src/main/resources/externalData). Create the following files:
    - `data/raw`
        - `ABSA15_Restaurants_Test.xml`
        - `ABSA15_Restaurants_Train.xml`
        - `ABSA16_Restaurants_Test.xml`
        - `ABSA16_Restaurants_Train.xml`
        - `ontology.owl`

## How to use? 
To view the CLI for a file, run `python [FILE] --help`. 

- Clean the data and obtain the contextual word embeddings
  - Run main_preprocess.py for the SemEval 2015 and SemEval 2016 datasets, for the training and test phase
- Tune the hyperparameters for each task by running main_hyperparam.py for the specific task
- Change the hyperparameters and train the model by running main_train.py. Set the patience variable for stopping criterion.
- Run main_validate.py to obtain the accuracy. Add ablation when running to do an ablation experiment. 

## References
Code is used from: 
- https://github.com/wesselvanree/LCR-Rot-hop-ont-plus-plus/tree/c8d18b8b847a0872bd66d496e00d7586fdffb3db.
- Liu, W., Zhou, P., Zhao, Z., Wang, Z., Ju, Q., Deng, H., Wang, P.: K-BERT: Enabling language representation with knowledge graph. In: 34th AAAI Conference on Artificial Intelligence. vol. 34, pp. 2901–2908. AAAI Press (2020)
- https://github.com/Bjarten/early-stopping-pytorch/blob/master/pytorchtools.py
