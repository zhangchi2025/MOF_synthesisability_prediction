The Jupyter Notebook `models_training_process.ipynb` hereafter presents the training procedure (corresponding to Figure 1, step 4) of one-class classification models. To avoid repetition, this notebook shows only seven OCC models (IForest, kNN, OCSVM, LOF, CBLOF, LUNAR, and DeepSVDD) trained by their best-performing feature sets. 

This notebook requires the following input files from the `dataset_generation_and_featurization` folder:

`ground_truth_pairs.csv` - the list of metal and linker combinations of the ground_truth dataset<br/>
`query_pairs.csv` - the list of metal and linker combinations of the query dataset<br/>
`linker_list.pkl` - the list of linkers<br/>
`metal_scaled_205.csv` - the list of normalised 205 metal features<br/>

This notebook outputs the following files:

`MorganFP_256_train.csv` - the prediction results of five traditional models (IForest, kNN, OCSVM, LOF, CBLOF) for the ground_truth dataset<br/>
`MorganFP_256_test.csv` - the prediction results of five traditional models (IForest, kNN, OCSVM, LOF, CBLOF) for the query dataset<br/>
`DeepSVDD_train.csv` - the prediction results of the DeepSVDD model for the ground_truth dataset<br/>
`DeepSVDD_test.csv` - the prediction results of the DeepSVDD model for the query dataset<br/>
`Lunar_train.csv` - the prediction results of the LUNAR model for the ground_truth dataset<br/>
`Lunar_test.csv` - the prediction results of the LUNAR model for the query dataset<br/>

This folder also includes the following file(s):

`Classifiers_Hyperparameter.txt` - optimised hyperparameters for traditional models with different feature sets
