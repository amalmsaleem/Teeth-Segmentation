# [Teeth-Segmentation](https://arxiv.org/pdf/2210.03739)
Segment out teeth from mandibular canal scans. 

## Pre-processing
To train a model to segment teeth, it is necessary that all of these scans be of similar contrast. We have achieved this by applying dynamic windowing to all scans that best enhances their teeth. As these scans have different contrast, they have different patterns of intensities and intensity density. We have exploited these to differentiate automatically. The histograms better explain this difference:

![output](https://github.com/amalmsaleem/Teeth-Segmentation/blob/main/histogram.png) 

## Prediction model
A ResUnet++ model was trained on a total of 400 teeth scans, 320 of which were for training and 80 for validation.

## Post processing
Due to the large size of the 3D CBCT scans, segmentation without localization produces choppy results as can be seen. The goal is to produce smoother results. Predictions from the previously trained model are used to extract the teeth region. To obtain smoother masks, another model was trained on only the cropped teeth regions.

![output](https://github.com/amalmsaleem/Teeth-Segmentation/blob/main/image1.png) 
## Results

Achieved dice score of 88.67%

![output](https://github.com/amalmsaleem/Teeth-Segmentation/blob/main/Results/result1.png) 

![output](https://github.com/amalmsaleem/Teeth-Segmentation/blob/main/Results/result2.png) 

![output](https://github.com/amalmsaleem/Teeth-Segmentation/blob/main/Results/result3.png) 
