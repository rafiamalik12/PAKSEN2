# PAKSEN2 Dataset
<p align="justify"> 
We introduce a novel dataset comprising of Sentinel-2 imagery of Pakistani water resources. This dataset has the potential to become a benchmark for training and evaluation of water classification and segmentation models in future research.


## Data Collection
<p align="justify">  
Pakistan possesses one of the world's largest interconnected irrigation systems, known as the Indus Basin Irrigation System (IBIS), which encompasses rivers, canals, dams, lakes, and seas. For PAKSEN2 dataset, six distinct water resources from various geographic regions across Pakistan were selected. Sentinel-2 imagery for the said water resources was procured from the USGS Earth Explorer (https://earthexplorer.usgs.gov/), a prominent platform for hosting free satellite and aerial imagery. We obtained six satellite tiles, one for each of the six chosen water resources. The satellite tiles were carefully selected to represent different seasons throughout the year, as well as maintaining an overall cloud cover of less than 2%.
  
![fig3-darkmode-2](https://github.com/rafiamalik12/PAKSEN2/assets/32853925/f2862dbe-2cf1-4af9-a6ff-c925bfbffe2a)


## Data Preprocessing and Annotation
<p align="justify"> 
A Sentinel-2 image tile contains 13 distinct bands with varying spectral resolutions (10m, 20m, and 60m). To create a composite image, the 20m and 60m bands are up-scaled to 10m resolution using interpolation and then combined together to form a single multispectral image. This preprocessing was carried out using the open-source software QGIS, which employs cubic-spline interpolation for generating composite images. For each tile, we produced two types of composite images: an RGB image (Red, Green, Blue bands) and a 13-band image with all bands interpolated to 10m resolution. Image annotation was performed by using the Label-Me tool, carefully delineating water bodies using polygons, and saving binary image masks (.png) for each satellite image. The LabelMe tool was modified to save binary class mask files directly from the labeled polygon points. The modified version of LabelMe is available at this link (https://github.com/shahrukh27/labelme)



![Picture1](https://github.com/rafiamalik12/PAKSEN2/assets/32853925/19b19d2b-6227-4d93-ba6c-549ce5bb8cdb)


## Dataset Creation
<p align="justify"> 
The PAKSEN2 dataset comes in two versions. In case of PAKSEN2-ALL, the 13-band composite images are divided into 64 x 64 pixel image patches and categorized into two groups, namely “Water” and “Non-water”, based on the percentage of water pixels in their binary masks. Image patches with at least 70% water pixels are labeled as “Water”, while those below this threshold are labeled as “Non-water”. Additionally, an RGB version of the dataset is also available. The key features of the PAKSEN2 dataset are summarized as below:

![Figure3-9](https://github.com/rafiamalik12/PAKSEN2/assets/32853925/0d2e1b44-1bcc-4060-a3c4-fd5a56cac2f3)



## Dataset Availability
<p align="justify"> 
Full dataset will be made available on request. Sample images from the PAKSEN2 dataset are shown below: 
  
![Figure3-10](https://github.com/rafiamalik12/PAKSEN2/assets/32853925/ca9eb5f5-d8d5-4d1d-a43e-bfe79045d5b3)


## Applications and Future Work
<p align="justify"> 
PAKSEN2 dataset can be used to train/fine-tune classification networks such as ResNet50 and Vision Transformers (ViT) for water classification.  Another important feature of PAKSEN2 is the inclusion of meticulously crafted binary masks for each data sample, specifically designed for water segmentation tasks. Using these binary masks, we can effectively separate water bodies from the surrounding landscape in Sentinel-2 imagery. 
In the future, we plan to geographically expand the PAKSEN2 dataset by incorporating water bodies from both domestic and international regions. This diversification will improve the dataset's inclusivity and representation, leading to improved performance and generalization of the models trained on it. 

  
## Citation
<p align="justify"> 
"Supervised Classification of Water Bodies: Analyzing Various Methods through a Case Study of Water Resources in Pakistan", 20<sup>th</sup> International Bhurban Conference on Applied Sciences and Technology (IBCAST), Aug 2023, Islamabad, Pakistan
