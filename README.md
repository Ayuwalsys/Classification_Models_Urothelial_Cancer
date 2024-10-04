## Benchmarking Spatial-Aware Classification Models for Urothelial Cancer Subtypes Using Cardinal


This project aims to establish a benchmark for classifying muscle-invasive from non-muscle invasive urothelial cancer from MSI data. The dataset consists of 49 bladder tissue samples obtained from 47 patients, which represents various diagnoses in urothelial cancer, including muscle-invasive, non-muscle invasive, and related conditions. Pre-processing of MSI data was performed on the European Galaxy server for transparency and reproducibility. All data are publicly available in the Proteomics IDEntifications Database under project code PXD026459. As seen from our preliminary exploratory analysis, there is indeed marked variation in the spatial patterns across the tissue microarrays, with clear segregation between tumor and stromal tissues. Characteristic peaks are present within the mass spectra, especially in the low m/z range, which can indicate a range of different biomolecules that could be important in distinguishing cancer types.

With this in mind, the scope of our project is to devise a classification model based on Cardinal's SCC algorithm and then compare the performance with the best result obtained from the use of traditional machine learning methods, such as PCA and LDA. This would also showcase exactly how well spatial-aware algorithms like SCC perform compared to their traditional counterparts in MSI-based cancer classification. These findings may finally equip us with the ability to accurately identify and classify these cancers of the urothelial origin, which in turn may contribute to better patient care and treatment.



