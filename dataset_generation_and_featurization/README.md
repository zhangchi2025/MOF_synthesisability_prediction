The Jupyter Notebook `dataset_generation_and_featurization.ipynb` hereafter presents the generation of the ground-truth and query dataset, along with the featurization process (corresponding to Figure 1, step 1-3). The ground-truth dataset, containing 3D-connected MOF networks made of a single metal and a single linker species in the CSD MOF subset, is generated from 1M1L3D dataset [Pétuya, 2022](DOI: 10.1002/anie.202114573) used for predicting the guest accessibility of MOFs. Taking all of the separate metals and linkers contained in the 1M1L3D dataset, we then generate a larger query dataset of 160,582 potential MOF chemistries by considering every pairwise combination of these metals and linkers that are not contained in the 1M1L3D dataset.

Three different featurization approaches are used for both metals and linkers. This notebook contains the featurization of metals using 6 elemental features, magpie, and mat2vec, and the featurization of linkers using Mordred and RDKit. The process for generating ECFPs is shown in the `one_class_classification_models/models_training_process.ipynb`.

This notebook requires the following input files of 1M1L3D dataset and 6 elemental metal features from [Pétuya, 2022](DOI: 10.1002/anie.202114573). These two documents are included in this folder and are also publicly available from (http://datacat.liverpool.ac.uk/1494):

`1M1L3D_summary.csv` - the list of metal and linker constituents of 14,296 reported 3D MOF structures<br/>
`1M1L3D_metal_descriptors.csv` - the list of 6 metal features<br/>

This notebook outputs the following files:

`ground_truth_pairs.csv` - the list of metal and linker combinations of the ground_truth dataset<br/>
`query_pairs.csv` - the list of metal and linker combinations of the query dataset<br/>
`linker_list.pkl` - the list of linkers<br/>
`metal_scaled_6.csv` - the list of normalised 6 metal features<br/>
`metal_scaled_27.csv` - the list of normalised 27 metal features<br/>
`metal_scaled_205.csv` - the list of normalised 205 metal features<br/>
`linker_scaled_1613.csv` - the list of normalised 1613 mordred linker features<br/>
`linker_scaled_177.csv` - the list of normalised 177 mordred linker features after removing feature columns with Pearson correlation greater than 0.80 and low variance below 0.50<br/>
`linker_scaled_rdkit.csv` - the list of normalised 194 RDkit linker features<br/>
