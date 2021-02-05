# Wellsville
Description of the repository:
Test the utility of the TSEB model in Wellsville. Corn, alfalfa, marijuana, and bare soil (landcover type) are the main objectives for this field. This repository is used to save all the code we used for this project. Details are shown below.


## 2. Model for spectral data extraction for each grid where there are ground measured - "Data_Extraction.ipynb"
Rui Gao (rui.gao@aggiemail.usu.edu)<br>
20210205<br>
Main goal for this script is that this script could generate "sufficient" statistics from the image for a machine learning model which is expected to delineate the relationship between statistics and LAI. Labor (manual) work, after-process, is needed to get the relationship for LAI prediction.<br> 
Raw image is needed, and the 6 (default) bands are needed to manually modify. Another needed input is the grids where do we took the ground measurements. The output is a ".csv" format table. 


## 3. Model for images generation - "Wellsville_Image_TSEB.ipynb"
Rui Gao (rui.gao@aggiemail.usu.edu)<br>
20210205<br>
Raw image includes 6 bands, ordered by B, G, R, RE, NIR, and Tr. DEM data is also provided, but for this part, it is not used.
This script cannot automatically finish the whole process. Such as equations for LAI calculation for different objectives need manual modifications. And the pre-process are needed before running this script.





    
 
