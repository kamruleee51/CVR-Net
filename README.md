# CVR-Net: A deep convolutional neural network for coronavirus recognition from chest radiography images

The novel Coronavirus Disease 2019 (COVID-19), originated in Wuhan (China), is a global pandemic disease. COVID-19 is an acute resolved disease, but it can also be deadly, with a 2.0 % case fatality rate. COVID-19 has abruptly and undoubtedly changed the world at the end of the second decade of the 21st century. COVID-19 is extremely contagious and quickly spreading disease globally making its early diagnosis of paramount importance. COVID-19 is perhaps the greatest challenge of mankind in the twenty-first century. The development of the disease, its transmission, and the increased mortality in several countries, make it imperative to develop a treatment, but also to protect health care and society from the transmission of the disease. Early diagnosis of COVID-19 enables health care professionals and government authorities to break the chain of transition and flatten the epidemic curve. The early and automatic diagnosis of COVID-19 may be beneficial for countries for timely referral of the patient to quarantine, rapid intubation of serious cases in specialized hospitals, and monitoring of the spread of the disease. Therefore, remote control of the disease, including diagnosis, early quarantine, and follow-up, is essential. The common type of COVID-19 diagnosis test requires specific equipment and has relatively low sensitivity. Computed tomography (CT) scans and X-ray images reveal specific manifestations associated with this disease, so Artificial intelligence can contribute to the above perspectives. As COVID is a new pandemic, a huge number of positive coronavirus images are not available yet. We have collected images from different open sources, such as such as [Kaggle](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia), [GitHub](https://github.com/ieee8023/covid-chestxray-dataset), and [grand challenge](https://covid-ct.grand-challenge.org/). The distribution of all the three datasets is presented in the following table, where we assign three different tasks, with a different number of classes, for dataset-1 and single task for the other two datasets.

<center>
    
|  Datasets |    Task types   |         Class Categories         |     No. of images    |
|---------|---------------|--------------------------------|--------------------|
|           |                 |           Normal (NOR)           |         5,856        |
| Dataset-1 | Task-1: 2-class |    Novel Corona Positive (NCP)   |          500         |
|           |                 |           Normal (NOR)           |         1,583        |
|           | Task-2: 3-class |      Common Pneumonia (CPN)      |         4,273        |
|           |                 |    Novel Corona Positive (NCP)   |          500         |
|           |                 |           Normal (NOR)           |         1583         |
|           |                 | Common Pneumonia Bacterial (CPB) |         2780         |
|           | Task-3: 4-class |   Common Pneumonia Viral (CPV)   |         1493         |
|           |                 |    Novel Corona Positive (NCP)   |          500         |
|           |                 |           Normal (NOR)           |         1648         |
| Dataset-2 | Task-4: 3-class |      Common Pneumonia (CPN)      |         4371         |
|           |                 |    Novel Corona Positive (NCP)   |          500         |
|           |                 |           Normal (NOR)           | Train/Test=292/105   |
| Dataset-3 | Task-5: 2-class |    Novel Corona Positive (NCP)   |   Train/Test=251/98  |

<center>


With the limited datasets, we apply geometry-based image augmentations and transfer learning on ImageNet. The graphical abstract of your research is depicted in the following figure. 
![BLOCK](https://user-images.githubusercontent.com/32570071/87485156-edaabc80-c659-11ea-82f2-4540258af049.png) 

To recognize the Covid-19 accurately, we proposed an end-to-end multi-scale-multi-encoder ensemble model, where we have aggregated the outputs from two different encoders and their different scales to obtain the final prediction probabilities. We evaluate our model's performance on three different publicly available datasets and compare them with the state-of-the-art methods. Our model has achieved an accuracy of 99.8 %, 96.4 %, and 78.0 % in these different datasets. The results are encouraging and demonstrate the effectiveness of deep learning, and more specifically, transfer learning with CNNs to the automatic detection of abnormal X-ray and CT images from different datasets, related to the Covid-19 disease.



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

The more details of the proposed framework will be uploaded soon-------


**Written by**<br>
**Md. Kamrul Hasan**  <br>
Erasmus Scholar [2017-2019] <br>
M.Sc. in Medical Imaging and Applications (MAIA)(https://maiamaster.udg.edu/ ) <br>
& <br>
Assistant Professor <br>
Department of Electrical and Electronic Engineering (EEE) <br>
Khulna University of Engineering & Technology (KUET) <br>
Khulna-9203, Bangladesh <br>


E-mail: kamruleeekuet@gmail.com or m.k.hasan@eee.kuet.ac.bd<br>
G.Scholar: https://scholar.google.com/citations?user=36WXELIAAAAJ&hl=en
