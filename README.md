# CVR-Net: A deep convolutional neural network for coronavirus recognition from chest radiography images

The novel Coronavirus Disease 2019 (COVID-19), originated in Wuhan (China), is a global pandemic disease. COVID-19 is an acute resolved disease, but it can also be deadly, with a 2.0 % case fatality rate. COVID-19 has abruptly and undoubtedly changed the world at the end of the second decade of the 21st century. COVID-19 is extremely contagious and quickly spreading disease globally making its early diagnosis of paramount importance. COVID-19 is perhaps the greatest challenge of mankind in the twenty-first century. The development of the disease, its transmission, and the increased mortality in several countries, make it imperative to develop a treatment, but also to protect health care and society from the transmission of the disease. Early diagnosis of COVID-19 enables health care professionals and government authorities to break the chain of transition and flatten the epidemic curve. The early and automatic diagnosis of COVID-19 may be beneficial for countries for timely referral of the patient to quarantine, rapid intubation of serious cases in specialized hospitals, and monitoring of the spread of the disease. Therefore, remote control of the disease, including diagnosis, early quarantine, and follow-up, is essential. The common type of COVID-19 diagnosis test requires specific equipment and has relatively low sensitivity. Computed tomography (CT) scans and X-ray images reveal specific manifestations associated with this disease, so Artificial intelligence can contribute to the above perspectives. 

To recognize the Covid-19 accurately, we proposed an end-to-end multi-scale-multi-encoder ensemble model, where we have aggregated the outputs from two different encoders and their different scales to obtain the final prediction probabilities. We evaluate our model's performance on three different publicly available datasets and compare them with the state-of-the-art methods. The results are encouraging and demonstrate the effectiveness of deep learning, and more specifically, transfer learning with CNNs to the automatic detection of abnormal X-ray and CT images from different datasets, related to the Covid-19 disease. However, the graphical abstract of this research is depicted in the following figure. 
![BLOCK](https://user-images.githubusercontent.com/32570071/87485156-edaabc80-c659-11ea-82f2-4540258af049.png) 

As COVID is a new pandemic, a huge number of positive coronavirus images are not available yet. We have collected images from different open sources, such as such as Kaggle, GitHub, and MICCAI grand challenge. The distribution of all the three datasets is presented in the following table. With the limited datasets, we apply geometry-based image augmentations and transfer learning on ImageNet. 

| Tasks      	| Different Studies    	| Categories      	| # of Images  	| Source References                                                                                                                                                                                          	| Modality 	|
|------------	|----------------------	|-----------------	|--------------	|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|----------	|
|            	| CXR-Single-CL2       	| NCV             	| 5,856        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                      	| X-ray    	|
|            	|                      	| CVP             	| 500          	| [CIDC](https://github.com/ieee8023/covid-chestxray-dataset)                                                                                                                                                	| X-ray    	|
|            	| CXR-Multiple-CL2     	| NCV             	| 7,864        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://nihcc.app.box.com/v/ChestXray-NIHCC)                                                                          	| X-ray    	|
|            	|                      	| CVP             	| 4,015        	| [CCXRI](https://www.sirm.org/category/senza-categoria/), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [PadChest](https://bimcv.cipf.es/bimcv-projects/padchest/)                           	| X-ray    	|
|            	| CXR- Independent-CL2 	| NCV(Train/Test) 	| 6,958/1,227  	| [CheXpert](https://github.com/stanfordmlgroup/chexpert-labeler)+[CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)/ [ChestX-ray8](https://nihcc.app.box.com/v/ChestXray-NIHCC)          	| X-ray    	|
| 2-classes  	|                      	| CVP(Train/Test) 	| 3,515/500    	| [CCXRI](https://www.sirm.org/category/senza-categoria/covid-19/)+[PadChest](https://bimcv.cipf.es/bimcv-projects/padchest/)/ [CIDC](https://github.com/ieee8023/covid-chestxray-dataset)                   	| X-ray    	|
|            	| CT-Single-CL2        	| NCV             	| 1,227        	| [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-datasetand)                                                                                                                                    	| CT       	|
|            	|                      	| CVP             	| 1,252        	| [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-datasetand)                                                                                                                                    	| CT       	|
|            	| CT-Multiple-CL2      	| NCV             	| 7,864        	| [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-datasetand), [CCII](https://nihcc.app.box.com/v/ChestXray-NIHCC), [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                 	| CT       	|
|            	|                      	| CVP             	| 4,015        	| [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset), [CCII](https://nihcc.app.box.com/v/ChestXray-NIHCC), [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                    	| CT       	|
|            	| CT-Independent-CL2   	| NCV(Train/Test) 	| 16,616/1,227 	| [MGC](https://github.com/UCSD-AI4H/COVID-CT)+[CCII](https://nihcc.app.box.com/v/ChestXray-NIHCC)+[iCTCF](http://ictcf.biocuckoo.cn/)/ [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset) 	| CT       	|
|            	|                      	| CVP(Train/Test) 	| 6,472/1,252  	| [MGC](https://github.com/UCSD-AI4H/COVID-CT)+[CCII](https://nihcc.app.box.com/v/ChestXray-NIHCC)+[iCTCF](http://ictcf.biocuckoo.cn/)/ [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset) 	| CT       	|
| 3- classes 	| CXR-Single-CL3       	| NOR             	| 1,583        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                      	| X-ray    	|
|            	|                      	| NCP             	| 4,273        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                      	| X-ray    	|
|            	|                      	| CVP             	| 500          	| [CIDC](https://github.com/ieee8023/covid-chestxray-dataset)                                                                                                                                                	| X-ray    	|
|            	| CXR-Multiple-CL3     	| NOR             	| 3,591        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://nihcc.app.box.com/v/ChestXray-NIHCC)                                                                          	| X-ray    	|
|            	|                      	| NCP             	| 4,595        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://nihcc.app.box.com/v/ChestXray-NIHCC)                                                                          	| X-ray    	|
|            	|                      	| CVP             	| 4,015        	| [CCXRI](https://www.sirm.org/category/senza-categoria/covid-19/), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [PadChest](https://bimcv.cipf.es/bimcv-projects/padchest/)                  	| X-ray    	|
| 4-classes  	| CXR-Multiple_CL4     	| NOR             	| 3,591        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://nihcc.app.box.com/v/ChestXray-NIHCC)                                                                          	| X-ray    	|
|            	|                      	| OBP             	| 2,780        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                      	| X-ray    	|
|            	|                      	| OVP             	| 1,493        	| [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                      	| X-ray    	|
|            	|                      	| CVP             	| 4,015        	| [CCXRI](https://www.sirm.org/category/senza-categoria/covid-19/), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [PadChest](https://bimcv.cipf.es/bimcv-projects/padchest/)                  	| X-ray    	|


The more details of the proposed framework can be found here: <br>
https://www.medrxiv.org/content/10.1101/2020.11.07.20227504v1


All the results reported in the literature were produced using the following version Python and Python API:

<ul>
    <li>Python 3.6.5</li>
    <li>numpy 1.19.0</li>
    <li>pandas 1.0.3</li>
    <li>matplotlib 3.1.3</li>
    <li>Scikit-learn 0.22.1</li>
    <li>scipy 1.4.1</li>
    <li>keras 2.3.1</li>
   
</ul>


**Written by**<br>
**Md. Kamrul Hasan**  <br>
M.Sc. in Medical Imaging and Applications (MAIA)(https://maiamaster.udg.edu/ ) <br>
Assistant Professor <br>
Department of Electrical and Electronic Engineering (EEE) <br>
Khulna University of Engineering & Technology (KUET) <br>
Khulna-9203, Bangladesh <br>
E-mail: kamruleeekuet@gmail.com or m.k.hasan@eee.kuet.ac.bd<br>
G.Scholar: https://scholar.google.com/citations?user=36WXELIAAAAJ&hl=en



**Md. Ashraful Alam**  <br>
Undergraduate student <br>
Department of Electrical and Electronic Engineering (EEE) <br>
Khulna University of Engineering & Technology (KUET) <br>
Khulna-9203, Bangladesh <br>
