# Cause 
There are some reasons that you should perform **Feature Extraction** stage with a python script named "feature_extraction.py".  
  
## 1. Incompatible Dependency 
If you running ipython notebook ("pyRadiomics.ipynb") with only python version 3.7 and install pyradiomics, you could perform **Feature Extraction** stage with iPython notebook.  
  
However, sklearn version 1.1+, which could be only compatible with only python 3.8+, only support ```n_features_to_select='auto'``` option in sklearn.feature_selection.SequentialFeatureSelector.  
  
In other words, **Feature Extraction** stage and **Feature Selection 2 & Model Selection** stage could not be run in a single iPython notebook with a single environment.  
  
  
## 2. Multiprocessing 
It's because iPython notebook do not support multiprocess which could dramatically speed up feature extraction process.  
  
Performing **Feature Extraction** stage with a single process require too long time to extract radiomics features. 
  
Thus, it is highly recommend to perform **Feature Extraction** with a python script named "feature_extraction.py" before running code blocks in iPython notebook ("pyRadiomics.ipynb").  

  
# Usage 
## 1. Performing Feature Extraction with a stand alone python script 
```
$python3 feature_extraction.py
```  
  
## 2. Running code blocks in iPython notebook while skipping Feature Extraction stage
running code blocks in the following procedure:   
- import modules and functions 
- perform **Split Dataset** stage. In this stage, loading csv files resulted from **Feature Extraction** stage and meta data files
- perform machine learning experiments 
- visualize the result



