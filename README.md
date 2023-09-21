# Genre Classification
This is a machine learning pipeline created with MlFlow, Wandb, Hydra and Conda.
It uses the random forest classifier from sklearn to predict the genre of a given music metadata.

The optimal classifier is chosen from a grid search on different hyperparameters. The
performance metric under consideration is the area under roc curve (auc). 
The auc scores are cataloged on Wandb, while the grid search is managed by MlFlow.

The final model is selected by maintaining a balance between high auc score and reduced 
model complexity.

## To run project:

* Login to wandb from terminal:
```
wandb login
```

* To create project on wandb, execute the command:
```
mlflow run . -P hydra_options="main.project_name='genre_classification_prod'"
```

* To run specific steps
```
mlflow run . -P hydra_options="main.execute_steps='download,preprocess'"
```