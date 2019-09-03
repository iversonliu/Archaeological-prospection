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


There are some unavoidable limitations in this human-scale approach for archaeological object detection, which can be summarized as three parts. 
1. It cannot handle the sheer quantity of available remote sensing data, which is growing exponentially. 
2. It does not justice the quality of remote sensing data, as well as the dimensionality and resolution of which is often beyond the processing capacity of the human visual system. 
3. The inherent biases of the traditional approach are not overcome but rather reproduced on a larger scale. These limitations together give importance of applying computational approaches to remote sensing-based archaeological prospection. Among the ways of computational approaches, machine learning, which overcome most of the stated limitations, is the most suitable one for this project. 

Through a literature review for machine learning application in archaeology, it is found that the studies of this field are very limited (Refer to Table 1) and two major challenges for the application remain to be solved: 
1. The absence of large datasets with labeled archaeological objects; 
2. The presence of hitherto unknown archaeological objects that have to be validated within the datasets. Additionally, both challenges require labor-intensive and time-consuming works, and the accuracy of the results might depend on the number of the interpreters. 

Having got an inspiration from the remote sensing and crowdsourcing applications on the search for MH370, this project is going to develop a tool for archaeological objects/features detection and then build a website for volunteer to improve the tool generating and validating parts of detections 


## __Objectives and aims__ <a name="paragraph1"></a>
The general aim of the project is to integrate remote sensing, machine learning and crowdsourcing in archaeological prospection, and it can be separated in detail as following:
1. Create a Matlab tool for “Similar-image search” for VHR satellite images in visible band. This tool will enable users to discover unmapped or unmappable “patterns of archaeological object or protected areas”;
2. Summarize the visible archaeological sites from different civilizations, and examining the similarities and relation among them. 
3. Build a website platform for volunteers, such as archaeologists, citizen scientists, humanitarian agencies, urban planners and other researchers, to generate and validate parts of detections of hitherto unknown archaeological objects. In the future, this platform is expected to satisfy the function like satellite image data exchange;
4. Update the tool and website on labelled data from volunteers. The labelled data from volunteers will be used to train a convolutional neural network to systematically identify similar archaeological objects/features;
5. Enhance awareness and better protection of the archaeological relics directly through the involvement of the public, especially countries like Afghan, a country so divided (its cultural heritage is considered to be a key to economic development and be critical for a strong national identity).
6. Generate two articles from the result of this project.


## __Theoretical Frame__ <a name="paragraph2"></a>
Existed studies on archaeological object detection from remotely sensed data can be classified into four main classes, which are template matching-based, knowledge-based, object-based image analysis, and machine learning (Refer to Fig 1). 

However, the first three classes all build on an explicit prior understanding of the target archaeological objects. In other words, they all rely on the detailed recording by prior discoveries which might harbor the following revealed bias during their implementation: 
1. The often handcrafted algorithms are specialized in specific object categories and data sources, which restrict their use in different contexts and limits their usability in general for archaeological prospection; 
2. Templates and characteristic spatial attributes are often difficult to define for heterogeneous archaeological objects, especially if these have been altered by various natural and anthropogenic processes over time; 
3. These approaches are predominantly complex algorithms that can require a high level of expertise, and are regularly dependent on expensive software.

Machine Learning, the fourth class, is a new method in archaeological application. Compared with the first three classes, its advantage is it does not require any explicit knowledge of the properties for the expected objects of their surroundings, or any rules for finding them either. The computer learns from many known positive instances of the expected object classes without making the relevant object properties explicit. Furthermore, Region Convolutional Neural Networks (R-CNNs), a subfield of machine learning CNNs, is the most suitable approach for this project. It is designated to image processing and can obtain the exact position of objects in the wider landscape. Through R-CNNs, computer can learn to generalize from a large set of labeled images rather relying on a human programmer to give rules, which meet the need for this project’s method. 

As for “crowdsourcing”, its definition is very broad, but it will be narrowed down into “volunteers help with scientific inquiry” in this project. Within archaeology, there exists cases involving volunteer in collection/ interpretation of datasets to deal with the bottleneck that professional can not solve. For example, in 2014, National Geographic set a crowdsourced search for Genghis Khan’s tomb. Over 10,000 volunteers gave contribution and 2.3 million potential archaeological objects were identified. A rather small-scale one is the Cotswold Escarpment project, in which six volunteers examined LiDAR data of an area of 100 km2 in South West England and identified over 260 objects. To sum up, the success of these project highlights the potential for integration of remote sensing and crowdsourcing in this project.


## __Study Area__ <a name="paragraph3"></a>
This project’s focus is to collect archaeological sites from different civilizations and to examine the similarities and relations among the sites. Thus, the study area of it should preferably be a general or conceptualized area including several civilizations but not an area of several km2 as habitat for Arabs or Chinese. 

Belt and Road could be taken into prior consideration. Theoretically, Belt and Road is considered to be an extended and revived version of the historic Silk Road which is a route of transportations and trade of goods and services across Eurasia. Apart from a network of trade routes, the ancient silk road is also one of major paths of cultural interaction and exchange among various civilization including Arabs, Chinese, Central Asians, Indians, and other Europeans. 

Furthermore, remote sensing enables the data collection for sites which are hard to access. Along the ancient silk road, potential archaeological sites in countries, which today are facing or have suffered from armed conflicts and civil wars, are too dangerous for researcher to visit and are almost impossible to conduct field works. This dilemma can be overcame by using satellite images.


## __Method__ <a name="paragraph4"></a>
Phase 1: Get a broad understanding of cultural/landscape background and classify existing visible archaeological objects by different civilizations
The categories of civilizations’ visible archaeological objects will be fully discussed in this phase to overcome culture-based and landscape/environment-based problems. The importance of the discussion is that the core difference between this project and other machine learning projects which lies in the study objectives - visible archaeological objects from satellite image. Sarah (2010) in the book “Satellite Remote Sensing for Archaeology” argued that archaeological object types for satellite image analysis can be divided into settlements, linking, temporary, installation, agriculture, mortuary, religion and ceremonial. Lambers (2019) classified the archaeological objects into barrows, Celtic fields and charcoal kilns in his research in Veluwe. These classifications could be a reference for the classification of this project’s archaeological objects (training labels). Besides, some websites, which can provide the location of existing archaeological and heritage objects, are listed in the Table 2.


## __Limitation and Contingencies__ <a name="paragraph5"></a>
The second paragraph text

## Reference <a name="paragraph6"></a>
The second paragraph text
