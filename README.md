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


- Item 1
- Item 2
- Item 3

<figure>
  <img src="/images/3D_U-Net_Model_Diagram.png" alt="3D U-Net Model Diagram" style="float: right; margin-left: 20px; width: 100px;">
  <figcaption>Figure 1: 3D U-Net Model Diagram</figcaption>
</figure>







# Potential Implications
