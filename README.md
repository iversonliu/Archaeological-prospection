# Archaeological-prospection

# Proposal (Lite Version)
# Table of contents
- [Introduction](#introduction)
- [Objectives and Aims](#paragraph1)
- [Theoretical Frame](#paragraph2)
- [Study Area](#paragraph3)
- [Method](#paragraph4)
- [Limitation and Contingencies](#paragraph5)
- [Reference](#paragraph6)

## Introduction <a name="introduction"></a>
How people interpret the visual world is a mixture of perception and comprehension. Everyone’ eyes use their own unique “lens” providing them with a completely different perception to sense the surrounding world. However, the scientific laws by which the Earth is observed are immutable. Every landscape result from certain environmental and anthropogenic factors. Similar things affect satellite imagery, which enables space archaeologists to observe and manually mark potential archaeological objects in the satellite images by obeying the “laws”.
</br>

There are some unavoidable limitations in this human-scale approach for archaeological object detection, which can be summarized as three parts. 
- *It cannot handle the sheer quantity of available remote sensing data, which is growing exponentially*. 
- *It does not justice the quality of remote sensing data, as well as the dimensionality and resolution of which is often beyond the processing capacity of the human visual system*. 
- *The inherent biases of the traditional approach are not overcome but rather reproduced on a larger scale. These limitations together give importance of applying computational approaches to remote sensing-based archaeological prospection. Among the ways of computational approaches, machine learning, which overcome most of the stated limitations, is the most suitable one for this project*. 

</br>
Through a literature review for machine learning application in archaeology, it is found that the studies of this field are very limited (Refer to Table 1) and two major challenges for the application remain to be solved: 
- *The absence of large datasets with labeled archaeological objects*; 
- *The presence of hitherto unknown archaeological objects that have to be validated within the datasets. Additionally, both challenges require labor-intensive and time-consuming works, and the accuracy of the results might depend on the number of the interpreters*. 

Having got an inspiration from the remote sensing and crowdsourcing applications on the search for MH370, this project is going to develop a tool for archaeological objects/features detection and then build a website for volunteer to improve the tool generating and validating parts of detections 
</br>
</br>

## Objectives and aims <a name="paragraph1"></a>
The general aim of the project is to integrate remote sensing, machine learning and crowdsourcing in archaeological prospection, and it can be separated in detail as following:
- *Create a Matlab tool for “Similar-image search” for VHR satellite images in visible band. This tool will enable users to discover unmapped or unmappable “patterns of archaeological object or protected areas”*;
- *Summarize the visible archaeological sites from different civilizations, and examining the similarities and relation among them*. 
- *Build a website platform for volunteers, such as archaeologists, citizen scientists, humanitarian agencies, urban planners and other researchers, to generate and validate parts of detections of hitherto unknown archaeological objects. In the future, this platform is expected to satisfy the function like satellite image data exchange*;
- *Update the tool and website on labelled data from volunteers. The labelled data from volunteers will be used to train a convolutional neural network to systematically identify similar archaeological objects/features*;
- *Enhance awareness and better protection of the archaeological relics directly through the involvement of the public, especially countries like Afghan, a country so divided (its cultural heritage is considered to be a key to economic development and be critical for a strong national identity)*.
- *Generate two articles from the result of this project*.
</br>
</br>

## Theoretical Frame <a name="paragraph2"></a>
Existed studies on archaeological object detection from remotely sensed data can be classified into four main classes, which are template matching-based, knowledge-based, object-based image analysis, and machine learning (Refer to Fig 1). 

However, the first three classes all build on an explicit prior understanding of the target archaeological objects. In other words, they all rely on the detailed recording by prior discoveries which might harbor the following revealed bias during their implementation: 
- *The often handcrafted algorithms are specialized in specific object categories and data sources, which restrict their use in different contexts and limits their usability in general for archaeological prospection*; 
- *Templates and characteristic spatial attributes are often difficult to define for heterogeneous archaeological objects, especially if these have been altered by various natural and anthropogenic processes over time*; 
- *These approaches are predominantly complex algorithms that can require a high level of expertise, and are regularly dependent on expensive software*.

Machine Learning, the fourth class, is a new method in archaeological application. Compared with the first three classes, its advantage is it does not require any explicit knowledge of the properties for the expected objects of their surroundings, or any rules for finding them either. The computer learns from many known positive instances of the expected object classes without making the relevant object properties explicit. Furthermore, Region Convolutional Neural Networks (R-CNNs), a subfield of machine learning CNNs, is the most suitable approach for this project. It is designated to image processing and can obtain the exact position of objects in the wider landscape. Through R-CNNs, computer can learn to generalize from a large set of labeled images rather relying on a human programmer to give rules, which meet the need for this project’s method. 

As for “crowdsourcing”, its definition is very broad, but it will be narrowed down into “volunteers help with scientific inquiry” in this project. Within archaeology, there exists cases involving volunteer in collection/ interpretation of datasets to deal with the bottleneck that professional can not solve. For example, in 2014, National Geographic set a crowdsourced search for Genghis Khan’s tomb. Over 10,000 volunteers gave contribution and 2.3 million potential archaeological objects were identified. A rather small-scale one is the Cotswold Escarpment project, in which six volunteers examined LiDAR data of an area of 100 km2 in South West England and identified over 260 objects. To sum up, the success of these project highlights the potential for integration of remote sensing and crowdsourcing in this project.
</br>
</br>

## Study Area <a name="paragraph3"></a>
This project’s focus is to collect archaeological sites from different civilizations and to examine the similarities and relations among the sites. Thus, the study area of it should preferably be a general or conceptualized area including several civilizations but not an area of several km2 as habitat for Arabs or Chinese. 

Belt and Road could be taken into prior consideration. Theoretically, Belt and Road is considered to be an extended and revived version of the historic Silk Road which is a route of transportations and trade of goods and services across Eurasia. Apart from a network of trade routes, the ancient silk road is also one of major paths of cultural interaction and exchange among various civilization including Arabs, Chinese, Central Asians, Indians, and other Europeans. 

Furthermore, remote sensing enables the data collection for sites which are hard to access. Along the ancient silk road, potential archaeological sites in countries, which today are facing or have suffered from armed conflicts and civil wars, are too dangerous for researcher to visit and are almost impossible to conduct field works. This dilemma can be overcame by using satellite images.
</br>
</br>

## Method <a name="paragraph4"></a>
- __*Phase 1: Get a broad understanding of cultural/landscape background and classify existing visible archaeological objects by different civilizations*__

The categories of civilizations’ visible archaeological objects will be fully discussed in this phase to overcome culture-based and landscape/environment-based problems. The importance of the discussion is that the core difference between this project and other machine learning projects which lies in the study objectives - visible archaeological objects from satellite image. Sarah (2010) in the book “Satellite Remote Sensing for Archaeology” argued that archaeological object types for satellite image analysis can be divided into settlements, linking, temporary, installation, agriculture, mortuary, religion and ceremonial. Lambers (2019) classified the archaeological objects into barrows, Celtic fields and charcoal kilns in his research in Veluwe. These classifications could be a reference for the classification of this project’s archaeological objects (training labels). Besides, some websites, which can provide the location of existing archaeological and heritage objects, are listed in the Table 2.

It is note-worthy that environmental events (including natural disasters) in the landscape may cause ancient sites and features to be hidden from plain view. This environment-based problem needs to be taken into serious consideration. The solutions employed in the existed studies are listed in the following as a reference: (1) using infrared and thermal satellite bands to detect abnormal parts of vegetation index in satellite images; (2) finding areas with high possibility providing water and food sources as clues from the satellite images. 
</br>

- __*Phase 2: Collect remote sensing data and archaeological data to generate training dataset (input images and training dataset based on categories and labels)*__

The geographic location of the input images will be narrowed down according to the location of the civilizations along the ancient silk road (the scale of the location will also be discussed, e.g., nationally, regionally). Detailed information of input satellite image which includes its types, resolution, coordinate system will also be decided. In addition, it is recommended to create a table to present the characteristics of sensors for a better discussion (Refer to Table 3).
As for the training dataset, it will be collected based on the categories and labels discussed in the Phase 1. In order to make it be more suitable for input images with different resolutions, spatial resolution of the training dataset will be collected hierarchically, like “100m-50m-10m”. 
</br>

- __*Phase 3: Automate archaeological object detection by using R-CNNs (or other methods)*__

     A Matlab tool for “Similar-image search” for VHR satellite images in visible band will be created. Some websites about open-access visual search engine for satellite maps are listed below (Refer to Table 4), which could be a reference:
</br>
     
- __*Phase 4: Build a website for tool presentation and data crowdsourcing*__

A website is going to be built to show the tool in Phase 3 and the interface can refer to the above websites. The validation of archaeological objects/features should also be given same attention as find potential ones. Lambers (2019) argued the validation can be separated into three consecutive steps, which are desktop survey, initial field survey, and minimal invasive survey. However, because this project’s aim is not to fully validate the potential site, the validation here will only focus on the desktop survey - a function on the website for crowdsourcing (and commercial use) will be built. The collection of crowdsourcing data will be extended and updated constantly based on the validation of detections on the process. In another word, the labelled data from website users will be used to improve the deep learning-based detection algorithm. In addition, this project also looks forward to exchanging the training data with projects working in similar fields, which could be a more direct way to improve the algorithm.

If possible, to make the website more user-friendly, some links which provides data source like historical, geo(morpho)logical, topographic maps, will be added into the website. This could act as a help for people who are interest in further validation.
</br>

- __*Phase 5: Finish the two articles for this project*__

New insight into the following objects could be discussed in the articles: 
1. The number, distribution, and state of preservation of the visible archaeological objects/features; 

2. Find the relations and similarities among landscape patterns of different civilizations; 

3. Explore the way to automatic detect archaeological objects/features hidden in forest or examine the impact of forests on the protection of archaeological objects/features; 

4. Policy for better preserving and monitoring of these objects which can answer different questions from urban planner, citizen scientist and other groups; 

5. The roles and the importance of crowdsourcing in the satellite archaeology.
</br>
</br>

## Limitation and Contingencies <a name="paragraph5"></a>

For study object, this project only focuses on visible archaeological objects/features. However, there are massive archaeological objects/features which has been buried under the ground. With technology available, whether it is worthy for us to use other band to detect these buried ones in a large-scale need further discussion. 

The result of this project highly depends on the selection and collection of training datasets which requires professional understandings of archaeological objects. Reviewing a large quantity of related literature or looking for existed related training datasets might be a way to minimize this limitation. 

Furthermore, open-source policy, the privacy policy and other archaeological policy might limit parts of the implementation of this project. The related policy should be taken into consideration when developing the tool and building the website. 
</br>
</br>

## Reference <a name="paragraph6"></a>

