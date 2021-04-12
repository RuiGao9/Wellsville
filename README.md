# Wellsville
Description of the repository:
Test the utility of the TSEB model in Wellsville. Corn, alfalfa, marijuana, and bare soil (landcover type) are the main objectives for this field. This repository is used to save all the code we used for this project. Details are shown below.


## 1. Model for LAI data extraction from the LAI-2200 analyzer - "LAI_Analyzer_V2.ipynb"
Rui Gao (rui.gao@aggiemail.usu.edu)<br>
20210106<br>
Main purpose for this script is extracting the measurement record number (ID), the ground true LAI (LAI), the corresponding measurement time including date and time (Time), the latitude of the ground measurement (Lat), and the longitude of the ground measurement (Lon). This code written based on my experience when review the fomat and the patter of the table (txt file) gained from the LAI-2200 analyzer. Current test are all correct.<br>
A .xlsx format file is required for this code, and this is the only manual work that we need to do. A demo .xlsx file, "LAI_Well_0720B.xlsx" is attached in this repository. The original .txt file, "WEL0720B.TXT", is also attached in this repository. By using the software called "FV2200", I copy and past the data into the .xlsx file. 4 sheets are required as the same like I showed in the .xlsx sheet, otherwise, the corresponding part of this code is needed to modify. For the .xlsx file, the first 3 sheets come from the .txt file. Direct copy and past is sufficient. The 4th sheet called "Current_new" is the main part of the 2nd sheet called "Current". Be careful about the format should be enough to run this code successfully.


## 2. Model for spectral data extraction for each grid where there are ground measured - "LAI_SIE_V2.ipynb"
Main idea for this code is extracting the spectral information from each grid: R, G, B, RE, NIR, and Tr. Meanwhile, the fractional cover for each grid is also calculated. In this case, the output table (a .csv file) can help us to find the relationship between the LAI and any VI. After this, we need to tell the equations and/or the relationships to the later processes.


## 3. Model for spectral data extraction for each grid where there are ground measured - "Data_Extraction.ipynb"
Rui Gao (rui.gao@aggiemail.usu.edu)<br>
20210205<br>
Main goal for this script is that this script could generate "sufficient" statistics from the image for a machine learning model which is expected to delineate the relationship between statistics and LAI. Labor (manual) work, after-process, is needed to get the relationship for LAI prediction.<br> 
Raw image is needed, and the 6 (default) bands are needed to manually modify. Another needed input is the grids where do we took the ground measurements. The output is a ".csv" format table. 


## 4. Model for images generation - "Wellsville_Image_TSEB.ipynb"
Rui Gao (rui.gao@aggiemail.usu.edu)<br>
20210205<br>
Raw image includes 6 bands, ordered by B, G, R, RE, NIR, and Tr. DEM data is also provided, but for this part, it is not used.
This script cannot automatically finish the whole process. Such as equations for LAI calculation for different objectives need manual modifications. And the pre-process are needed before running this script.
### Important notice:
This python script can be recognized as a calculator which is not that stable. Users who are using this repository need to run section by section in this python script. ArcMap is recommend to review the result from each block, and tables need to gain your more attention.





    
 
