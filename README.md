# CVR-Net: A deep convolutional neural network for coronavirus recognition from chest radiography images

The novel Coronavirus Disease 2019 (COVID-19), originated in Wuhan (China), is a global pandemic disease. COVID-19 is an acute resolved disease, but it can also be deadly, with a 2.0 % case fatality rate. COVID-19 has abruptly and undoubtedly changed the world at the end of the second decade of the 21st century. COVID-19 is extremely contagious and quickly spreading disease globally making its early diagnosis of paramount importance. COVID-19 is perhaps the greatest challenge of mankind in the twenty-first century. The development of the disease, its transmission, and the increased mortality in several countries, make it imperative to develop a treatment, but also to protect health care and society from the transmission of the disease. Early diagnosis of COVID-19 enables health care professionals and government authorities to break the chain of transition and flatten the epidemic curve. The early and automatic diagnosis of COVID-19 may be beneficial for countries for timely referral of the patient to quarantine, rapid intubation of serious cases in specialized hospitals, and monitoring of the spread of the disease. Therefore, remote control of the disease, including diagnosis, early quarantine, and follow-up, is essential. The common type of COVID-19 diagnosis test requires specific equipment and has relatively low sensitivity. Computed tomography (CT) scans and X-ray images reveal specific manifestations associated with this disease, so Artificial intelligence can contribute to the above perspectives. 

To recognize the Covid-19 accurately, we proposed an end-to-end multi-scale-multi-encoder ensemble model, where we have aggregated the outputs from two different encoders and their different scales to obtain the final prediction probabilities. We evaluate our model's performance on three different publicly available datasets and compare them with the state-of-the-art methods. The results are encouraging and demonstrate the effectiveness of deep learning, and more specifically, transfer learning with CNNs to the automatic detection of abnormal X-ray and CT images from different datasets, related to the Covid-19 disease. However, the graphical abstract of this research is depicted in the following figure. 
![BLOCK](https://user-images.githubusercontent.com/32570071/87485156-edaabc80-c659-11ea-82f2-4540258af049.png) 

As COVID is a new pandemic, a huge number of positive coronavirus images are not available yet. We have collected images from different open sources, such as such as Kaggle, GitHub, and MICCAI grand challenge. The distribution of all the three datasets is presented in the following table. With the limited datasets, we apply geometry-based image augmentations and transfer learning on ImageNet. 

| Different studies  | Class categories | Number of Images | Source References with links                                                                                                                                                                                       | Modality |
|--------------------|------------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|
|                    | NOR              | 5,856            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              |          |
| CXR-Single-CL2     | NCP              | 500              | [CIDC](https://github.com/ieee8023/covid-chestxray-dataset)                                                                                                                                                        | X-ray    |
|                    | NOR              | 7,864            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://www.kaggle.com/nih-chest-xrays/data)                                                                                  |          |
| CXR-Multiple-CL2   | NCP              | 4,015            | [CCXRI](https://www.kaggle.com/tawsifurrahman/covid19-radiography-database), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [BIMCV](https://bimcv.cipf.es/bimcv-projects/bimcv-covid19/)             | X-ray    |
|                    | NOR (Train/Test) |  6,958/1,227     | [CheXpert](https://stanfordmlgroup.github.io/competitions/chexpert/)+[CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)/[ChestX-ray8](https://www.kaggle.com/nih-chest-xrays/data)              |          |
| CXR-Individual-CL2 | NCP (Train/Test) |  3,515/500       | [CCXRI](https://www.kaggle.com/tawsifurrahman/covid19-radiography-database)+[BIMCV]()/[CIDC](https://github.com/ieee8023/covid-chestxray-dataset)                                                                  | X-ray    |
|                    | NOR              | 1,227            | [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset)                                                                                                                                               |          |
| CT-Single-CL2-I    | NCP              | 1,252            | [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset)                                                                                                                                               | CT       |
|                    | NOR              | 397              | [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                                                                                                                                                       |          |
| CT-Single-CL2-II   | NCP              | 349              | [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                                                                                                                                                       | CT       |
|                    | NOR              | 7,864            | [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset), [CCII](http://ncov-ai.big.ac.cn/download?lang=en), [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                              |          |
| CT-Multiple-CL2    | NCP              | 4,015            | [SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset), [CCII](), [MGC](https://github.com/UCSD-AI4H/COVID-CT)                                                                                       | CT       |
|                    | NOR (Train/Test) | 16,616/1,227     | [MGC](https://github.com/UCSD-AI4H/COVID-CT)+[CCII](http://ncov-ai.big.ac.cn/download?lang=en)+[iCTCF](http://ictcf.biocuckoo.cn/HUST-19.php)/[SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset) |          |
| CT-Individual-CL2  | NCP (Train/Test) | 6,427/1,252      | [MGC](https://github.com/UCSD-AI4H/COVID-CT)+[CCII](http://ncov-ai.big.ac.cn/download?lang=en)+[iCTCF]()/[SCoV](https://www.kaggle.com/plameneduardo/sarscov2-ctscan-dataset)                                      | CT       |
|                    | NOR              | 1,583            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              |          |
|                    | CPN              | 4,273            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              |          |
| CXR-Single-CL3     | NCP              | 500              | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              | X-ray    |
|                    | NOR              | 3,591            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://www.kaggle.com/nih-chest-xrays/data)                                                                                  |          |
|                    | CPN              | 4,595            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [ChestX-ray8](https://www.kaggle.com/nih-chest-xrays/data)                                                                                  |          |
| CXR-Multiple-CL3   | NCP              | 4,015            | [CCXRI](https://www.kaggle.com/tawsifurrahman/covid19-radiography-database), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [BIMCV](https://bimcv.cipf.es/bimcv-projects/bimcv-covid19/)             | X-ray    |
|                    | NOR              | 3,591            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) , [ChestX-ray8](https://www.kaggle.com/nih-chest-xrays/data)                                                                                 |          |
|                    | CPB              | 2,780            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              |          |
|                    | CPV              | 1,493            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)                                                                                                                                              |          |
| CXR-Multiple-CL4   | NCP              | 4,015            | [CXRI](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [CIDC](https://github.com/ieee8023/covid-chestxray-dataset), [BIMCV](https://bimcv.cipf.es/bimcv-projects/bimcv-covid19/)                   | X-ray    |



The more details of the proposed framework can be found here: <br>
https://arxiv.org/abs/2007.11993


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
