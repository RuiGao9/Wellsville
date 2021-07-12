# Wellsville
Testing the utility of the TSEB model in Wellsville. Corn, alfalfa, mar***, and bare soil (landcover type) are the main objectives for this field. This repository is used to save all the code (3 main pieces of scripts) we used for this project. Details are shown below.

## 1. "LAI_Analyzer_V2.ipynb"
20210106<br>
- **Goal of this script:**<br>
Extracting the measurement record number (ID), the ground LAI measurements (LAI), the corresponding measurement time including date and time (Time), the latitude of the ground measurement (Lat), and the longitude of the ground measurement (Lon).This script written based on my experience when review the fomat and the pattern of the table (txt file) gained from the LAI-2200 analyzer. Current test are all correct, potential issues are welcome to eamil to Rui.<br>
- **Input:**<br>
A ".xlsx" format file is required for this code, and this is the only manual work that we need to do. A demo ".xlsx" file, "LAI_Well_0720B.xlsx" is attached in this repository. The original ".txt" file, "WEL0720B.TXT", is also attached in this repository. By using the software called "FV2200", I copy and past the data into the ".xlsx" file. 4 sheet-name are required as the same like I showed in the ".xlsx" sheet, otherwise, the corresponding part of this code is needed to modify. For the ".xlsx" file, the first 3 sheets come from the ".txt" file. Direct copy and past is sufficient. The 4th sheet called "Current_new" is the main part of the 2nd sheet called "Current". Being careful about the format should be enough to run this code successfully.
- [LAI2200-PCA](https://github.com/RuiGao92/LAI2200-PCA), a separate repository, is the tool to extract main information from the PCA datalog.

## 2. "LAI_SIE_V2.ipynb" 
- **Goal of this script:**<br>
Spectral data extraction from the AggieAir-platform image based on the grids (a shapefile) where there are ground LAI measured. R, G, B, RE, NIR, and Tr are extracted. Meanwhile, the fractional cover for each grid is also calculated.
- **Inputs:**<br>
A shapefile containing all locations where they provide ground LAI measurements is needed. The resolution for each grid is 1 meter by 1 meter. A sample is provided in the "Demo_Data" folder called "Wellsville_Grids_1m.shp".
- **Output:**<br>
The output table (a ".csv" file) can help us to find the relationship between the LAI and any VI. After this, we need to tell the equations and/or the relationships to the later processes.

## 3. "Wellsville_Image_TSEB_V3.ipynb"
- **Goal of this script:**<br>
Using the raw image data gained from the AggieAir platform and the information gained from previous steps to prepare image data for running the [TSEB-PT](https://github.com/hectornieto/pyTSEB) model.
- **Inputs**<br>
Raw image includes 6 bands, ordered by B, G, R, RE, NIR, and Tr.
- **Note:**<br>
Equations for LAI calculation for different objectives need manual modifications.<br>
This python script can be recognized as a calculator which is not that stable. Users who are using this repository need to run section by section in this python script. ArcMap is recommend to review the result from each block, and tables need to gain your more attention.


## 4. "Data_Extraction.ipynb"
- **Goal of this script**<br>
This is an option regarding the LAI estimation.<br>
Model for spectral data extraction for each grid where there are ground measured (LAI) to generate "sufficient" statistics from the image for a machine learning model which is expected to delineate the relationship between statistics and LAI. Labor (manual) work, after-process, is needed to get the relationship for LAI prediction.<br> 
- **Inputs:**<br>
The 6-band image (default) is required. Another needed input is the grids where do we took the ground measurements. 
- **Output:**<br>
The output is a ".csv" format table. 

