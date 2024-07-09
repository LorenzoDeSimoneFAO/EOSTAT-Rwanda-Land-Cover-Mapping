# EOSTAT-Rwanda-Land-Cover-Mapping
The repository contains python scripts for producing a national land cover map for Rwanda using Digital Earth Africa platform.  The  methodology was initially developed by FAO in Lesotho for the production of standardized annual land cover maps (L. De Simone et al, 2022). 

The methodology has been adapted for Rwanda as a result of the collaboration of FAO with the National Institute of Statistics Rwanda (NISR) and the Digital Earth Africa and the implementing partner Frontier SI

The EOSTAT LC mapping methodology for producing standardized annual land cover maps is composed of the following processing steps:

Automatic Generation of Training and Validation Datasets:

Utilize a baseline in situ dataset (developed in 2017 - RCMRD) to generate pseudo in situ datasets for each reporting year. Apply K-means clustering on Sentinel-2 temporal composites to isolate representative pixels of each land cover class.

Develop a Sentinel2 Data Cube:
Acquire Sentinel-2 images for the reporting calendar year.
Perform cloud masking using the s2cloudless Sentinel-2 cloud probability.
Apply bimonthly temporal aggregation using the geometric median to create cloud-free temporal composites.

Land Cover Classification using Random Forest:
Train a Random Forest classifier with the generated training datasets.
Use Sentinel-2 spectral bands and vegetation indices (NDVI and EVI) as input features for the classifier.
Generate land cover maps for each reporting year.

Post-Processing and Harmonization:
Apply post-processing techniques to refine the classified land cover maps.
Implement harmonization steps to ensure consistency and comparability of the land cover maps across different years.
Use spatial filters to remove noise and smoothen the classification results.
Conduct majority filtering to correct isolated misclassifications and improve the spatial coherence of the maps.

Validation of Land Cover Maps:
Construct confusion matrices to assess classification accuracy.
Validate the stability and consistency of the estimates over time.

The methodology ensures high accuracy and consistency of land cover maps despite the scarcity of in situ data, leveraging cloud computing and machine learning techniques for efficient and effective land cover mapping. 
