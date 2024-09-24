# The MFD (Maximum Fractional Difference) method and its implementation on MOF synthesisability prediction
**The repository for the publication "Accelerating Metal-Organic Framework Discovery via Synthesisability Prediction: The MFD Evaluation Method for One-Class Classification Models"**

This repository contains five folders with the following contents:<br/>

- `dataset_generation_and_featurization`: the generation of the ground-truth and query dataset, along with the featurization process.<br/>
   <br/>
   The 1M1L3D dataset used to as the fround-truth dataset after removing duplicates is obtained from Pétuya et al. **[DOI: 10.1002/anie.202114573]**. This dataset is sourced from decomposing reported experimental three-dimensional MOF structures made of a single metal and a single linker in **CSD (Data Update 3-2019)** into their constituent components, are openly available in http://datacat.liverpool.ac.uk/1494.
   <br/>
   <br/>
- `elemental_descriptor`: The full elemental descriptor vectors used to represent metals.
- `one_class_classification_models`: the training procedure of one-class classification models. To avoid repetition, this notebook shows only seven OCC models (IForest, kNN, OCSVM, LOF, CBLOF, LUNAR, and DeepSVDD) trained using their best-performing feature sets.
- `model_architecture`: the source code for the DeepSVDD and the LUNAR model.
- `best_vs_poor_model`: the score and the positive fraction distributions for the best-performing model (the DeepSVDD model trained by 205-dimensional metal features and 2048-dimensional linker features from ECFPs, with an MFD value of 0.59) and the poor model used for comparison (the IForest model trained by 6 elemental metal features and 1613-dimensional linker features from Mordred, with an MFD value of 0.08). The two notebooks also show the creation of the positive validation dataset and model validation procedure.
- `model_validation_and_analysis`:  1. the model predictions for the 14 true negative samples. 2. the results of UMAP projection of the query dataset.

If you want to use the MFD method to evaluate your models, please input the prediction results for your ground_truth dataset and the query dataset into `MFD calculation.ipynb`. This notebook can help you plot score distributions, positive fraction distributions, and generate the MFD and OT values. Further instructions can be found within the notebook.<br/>

If you want to use the best-performing trained DeepSVDD model to predict the synthesisability of your input [metal, linker] combination, please use `synthesisability_prediction.ipynb`. Enter the metal as an element symbol and the organic linker as a SMILES string. The `deep_scaler.joblib` saves the DeepSVDD model scaler used to normalise the prediction score for the input.<br/>

## Clone and Run
**This repository includes large files uploaded using LFS(Git Large File Storage). Please also use LFS to clone the repository to your local machine to avoid errors when running the code:**
1. Install Git LFS:
   ```
   git lfs install
   ```
3. Clone the Repository with LFS:
   ```
   git lfs clone <repository-url>
   ```
**To avoid package conflicts, please build environment with python==3.7 and install the packages listed in a requirements.txt file using the following command:**
   ```
   pip install -r requirements.txt
   ```

## Citation and Contact
Please cite the corresponding paper if you used the Maximum Fractional Difference (MFD) method or these trained machine learning (ML) models in your work.<br/>

This article is pre-printed on ChemRxiv on 22 May 2024.<br/>

```
@article{
   author = {Chi Zhang, Dmytro Antypov, Matthew J. Rosseinsky, and Matthew S. Dyer},
   title = {Accelerating Metal-Organic Framework Discovery via Synthesisability Prediction: The MFD Evaluation Method for One-Class Classification Models},
   doi = {10.26434/chemrxiv-2024-tlmp4},
   url = {https://chemrxiv.org/engage/chemrxiv/article-details/664c7a3c418a5379b0ded343}
}
```
