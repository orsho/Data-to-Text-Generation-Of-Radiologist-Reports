# Data-to-Text-Generation-Of-Radiology-Reports
Radiology report writing in hospitals is a time-consuming task that also requires experience from the involved radiologists. This paper proposes a D2T NLG model to automatically generate selected sections in radiology reports given a structured input of medical annotations from the public MIMIC-CXR dataset.Our model combines three main inputs: (1) medical annotations extracted by Chexbert model into a structured table. (2) All the information in the report before the required generated section, contain only the tokens in which most information is stored for generating a correct coherent text. (3) Text features controlling the style of the generated report. This model uses T-5 encoder-decoder transformer which trained on 230,000 samples and aims to generate a coherent radiological report. We evaluate the generated reports using word-overlap metrics while also creating a new formula to measure the quality of the model's output. The model achieves Precision of 93.7\% on evaluating the differences between the actual sentences to the generated sentences in the "impression" section in the report which showed that 83.3\% of the generated reports on the test set were expertly written without any mistakes. Moreover, the model does not require a specific vocabulary and can be trained on different datasets without changing the architecture as long as the report contains the common sections.

## Project architecture

summarization of the process we performed:

<img src="https://github.com/orsho/Data-to-Text-Generation-Of-Radiology-Reports/blob/main/src/report%20flow.png" width="900" height="500">

## Highlighted Features

* The main code is arranged in one [Colab notebook](https://colab.research.google.com/drive/1pdOScB49x6QvImWw_X7K8QWkVdeMypTP)
* The notebook will work on any python IDE environment but it is best to open it in Colab
* The notebook is divided into sections for better understanding the experiments and the models - It is recommended to use the side navigation bar in colab
* This project has 3 main folders:
  1. Data folder - contains all the files on which we performed the experiments
  2. Notebook folder - contains all the notebooks we used to create the above data files
  3. Results folder - contains the results of the experiments for each data file

## Dataset

MIMIC-CXR-JPG - The MIMIC Chest X-ray JPG Database is a large publicly available dataset of chest radiographs in JPG format with structured labels derived from free-text radiology reports. The aim of MIMIC-CXR-JPG is to provide a convenient processed version of MIMIC-CXR, as well as to provide a standard reference for data splits and medical findings organize in structured tables. The dataset contains 377,110 JPG format images and structured labels derived from the 227,827 free-text radiology reports associated with these images. Labels were determined using DL method named 'CheXbert'. 
