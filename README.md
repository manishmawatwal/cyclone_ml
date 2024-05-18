# North Indian Ocean Tropical Cyclone Detection Using YOLOv5

## Abstract
This research paper focuses on the application of You Only Look Once version 5 (YOLOv5) Deep Learning (DL) architecture for cyclone detection and classification. Cyclones are one of the most devastating natural disasters that cause significant loss of lives and property damage. Accurate and timely detection and classification of cyclones can help in effective disaster management and mitigation. In this study, YOLOv5 is used for detecting and classifying cyclones in satellite images.
The proposed method involves pre-processing the data, training the YOLOv5 model on the dataset, and evaluating the model’s performance. The results demonstrate that the proposed method achieved high accuracy in both cyclone detection and classification
tasks. This research paper provides insights into the potential of YOLOv5 in cyclone detection and classification, which can be beneficial in enhancing disaster management strategies.

## Introduction
Tropical cyclones (TCs) have become a major threat to human lives and the environment, with their frequency and intensity increasing due to climate change. Accurate detection and classification of TCs are crucial to prevent and mitigate
their devastating effects. Deep Learning (DL) models have been incorporated in TC detection, including the application of neural networks in existing TC detection [1], precursor identification of TCs [2], detection of TC [3], TC track
forecasting [4]. However, DL models typically demand a substantial number of training samples due to the challenge of achieving high accuracy with finite training data, as observed in computer vision and other domains [5], [6]. Transfer
learning can effectively mitigate this issue, thereby enhancing the accuracy of DL models [7]–[9]. In recent years, DL techniques have shown promising results in image-based object detection, including TCs. Advancements in satellite imaging
and computer vision have enabled accurate automatic weather prediction, including predicting cyclones.
Among other techniques, the You Only Look Once version 5 (YOLOv5) model has gained popularity due to its speed and accuracy. The economic losses associated with TCs are also significant, further highlighting the urgency of developing
effective detection and mitigation strategies [10]. [11] introduced a novel detection framework, NDFTC, which utilizes deep transfer learning by merging DCGAN and YOLO v3 for identifying tropical cyclones in meteorological satellite
images. [11] proposes a YOLOv5 algorithm for identifying TCs on GridSat dataset and China Meteorological Administration satellite data. The algorithm showed good identification ability, fast detection speed, and low missed detection rate. [12] proposes a cyclone detection technique with cyclone eye localization using satellite images. [13] evaluates convolutional neural network (CNN) models for object detection in aerial views of disaster affected areas. The CNN models are trained on a dataset containing annotated aerial videos collected during hurricanes in the US. Transfer learning is used to pretrain the models on the COCO/VOC dataset and then re-train them on the disaster dataset. [14] used YOLOv3 for cyclone detection and was trained to detect TCs using data from the Thermal InfraRed (TIR) Atmospheric Sounding Interferometer (IASI) onboard the Metop satellites. The proposed framework could be extended to other models and sensors like AIRS, MODIS, and SEVIRI. In this context, this paper aims to explore the application of the YOLOv5 model in TC detection and classification, with the goal of contributing to environmental sustainability and reducing economic losses.

## Data and Pre-Processing
Long wave infrared images are taken from CIMSS Tropical Data Archive [15] captured by Meteosat-5/7/8 for the period 2000-2022. The temporal resolution is 3hr/6hr and the image has a 10km spatial resolution. The dataset included images of various cyclones with different intensities, sizes, shapes, and from different perspectives. Best track data of North Indian Ocean (NIO) region is taken from the Indian Meteorology Department (IMD) [16] for labelling the intensity of the images. The best track cyclone intensity is provided at a resolution of 5 kt. The images are classified into Depression (D), Deep Depression (DD), Cyclonic Storm (CS), Severe Cyclonic Storm (SCS) and Very Severe Cyclonic Storm (VSCS). Fig. 1 shows the sample raw image from the CIMSS dataset, Fig. 2 shows a cyclone of D category, Fig. 3 shows a cyclone of VSCS category. Table 1 shows the category of cyclones with their frequency.
The images of TCs in NIO are first cropped to an average dimension of 310 x 310 manually (average aspect ratio is maintained at 1) in a way that they contain cyclone eye in the off-centre, which makes the model more robust, as the region
contains non-cyclonic parts as well. The reduction of image size is also done to reduce the processing time and to remove the unwanted boundaries and excess noise in the data. The images are then converted into grayscale to improve detection.
LabelImg annotation tool is used to create bounding box annotations of the TCs in the images. The images are labelled with bounding boxes around the cyclone, keeping the cyclone eye in the middle, indicating the location of the cyclone in the
image. There are certain cases when multiple cyclones can be detected simultaneously in NIO. Some instances include, Kyaar and Maha cyclones in the year 2019, Pawan and 07A in 2019, Luban and Titli in 2018, Laila and Bandu in year
2010. Multiple cyclone detections in the image can also be done simultaneously. The images were then split into training and testing dataset. However, it should be noted that as the cyclone images in few hours doesn’t change much, there is
always a possibility of leakage of the data between training and testing samples. To avoid this, the evaluation is carried separately with a testing dataset of 2022 while keeping 2000-21 as training dataset. This, however, doesn’t guarantee the
proper representation of all the cyclone classes.

## Conclusion and Future Scope
In conclusion, the YOLOv5 model has shown great promise in detecting TCs from satellite imagery. However, there are limitations to its accuracy due to a lack of sufficient data and the temporal resolution of 5 knots. This highlights the
need for more research and data collection to further improve the model’s performance. Future object detection models that take advantage of the latest advancements in DL techniques, such as attention mechanisms and graph neural networks,
could potentially overcome these limitations and provide even more accurate cyclone detection. In addition, efforts should be made to expand the dataset and to cover a longer period of time. Such efforts would help to advance the field of cyclone
detection and contribute to better management of the economic losses and environmental impact caused by these powerful storms. YOLOv5 can also be used for real-time TC detection’s. YOLOv5 can be especially useful in mitigating the impact of
natural disasters by providing advance warnings to those living in affected areas. By using this model, authorities can quickly identify and track the movements of TCs, thereby allowing for timely evacuation orders and other measures to be put in
place.
