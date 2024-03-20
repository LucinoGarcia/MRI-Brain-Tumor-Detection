# MRI Brain Tumor Detection: Project Overview



# Resources
**Python Version:** 3.10.9 <br>
**Packages:** NumPy, Matplotlib, JSON, Pandas, Keras backend, TensorFlow, scikit-learn, NiBabel, util, public_tests, test_utils



# Data Collection
Data was provided by the [Decathlon 10 Challenge](https://decathlon-10.grand-challenge.org/). 



# EDA
Each of the 484 samples consists of two files. The first file is an image file containing a 4D array of MR images with 3 for voxels and specifying one of the four sequences: Fluid Attenuated Inversion Recovery, T1-weighted, T1-weighted with gadolinium contrast enhancement, or T2-weighted. The second file is a 3D array label indicating whether the corresponding voxel is background, edema, non-enhancing tumor, or enhancing tumor. The files will have sizes of (240, 240, 155, 4) and (240, 240, 155), respectively. <br><br>
In regards to the voxel, the first two shape components (240, 240) refer to the MRI image along the transversal plane. The third component is the number of slices (155) of those images. Below is mutiple views of a sample. <br><br>
![image](/images/3_View.png)



# Data Cleaning
Some rudimentary data cleaning was required, as showcased in [this notebook here.](/MRI_CVision,_Data_Cleaning.ipynb) It essentially boiled down to creating functions for patches and standardization.



# Model Building
<img align="right" src="/images/3D_U-Net_Model_Diagram.png" width="77px">

A 3D U-Net model for the following reasons:
- its architecture is specifically designed for volumetric datasets
- the concatinating of paired down convolutions and upsampling maintain contextual information
- achieves good results with only a couple hundred of samples


The 3D U-Net model's architecture is quite lengthy but it, along with all 16,318,307 of its parameters, [can be seen here](/images/3D_U-Net_Model_Diagram.png) or by clicking the image on the right. The scripting to build the model [can be found here](/Need_Power,_MRI_CVision,_Model_Building.ipynb) <br><br>
Unfortunetely, limited computing power prohibited local training of the model. Fortunately, a pretained was provided. The following is a table of its Sensitivity and Specificity.

|                |   Edema           | Non-Enhancing Tumor | Enhancing Tumor |
|:--------------:|:-----------------:|:--------------------:|:---------------:|
|  Sensitivity  |       0.8746      |        0.9419        |     0.8049      |
|  Specificity  |        0.97       |        0.9957        |     0.9924      |



# Potential Implications
