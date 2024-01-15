# Detection of Threat Objects in Baggage Screening
This project employs an ensemble object detection approach to automate the detection of forbidden objects in baggage X-Ray scans. 
The system usesa total of 415 X-Ray scans from the [GDXRay dataset](https://github.com/computervision-xray-testing/GDXray) for training and testing.
Four classes of threat objects were considered in this work-Handgun, Knife, RazorBlade and Shuriken. Three object detection models – YOLOv3, SSD and Faster-RCNN were trained
on the dataset. Further, ensembles of these models were constructed with several techniques namely- Voting, Non-Maximum Suppression (NMS), Soft NMS, Non-Maximum Weighted (NMW), Weighted boxes fusion (WBF). The performance of all the models and their ensembles were evaluated in terms of mean average precision score (mAP).

## Implementation Details
- The training was carried out on the Google Colaboratory free GPU
- YOLOv3 requires annotations to be in the YOLOv3 format and this data is provided in YOLO/data. This model was trained on 8000 epochs with batch size = 64
- SSD and FasterRCNN were implemented using the Tensorflow-2 Object Detection API.
- The data and annotations for SSD and FasterRCNN are in the PascalVOC format and this available in the dataset folder
- This project uses the SSD model with MobileNetV2 as it’s backbone. The model was run for a total of 20000 steps with batch size set to 16.
- This project uses the FasterRCNN model with ResNet50 as it’s backbone. The model was run for a total of 10000 steps with batch size set to 4.
- This work uses five ensemble methods to combine object detection models namely – Voting, Non-Maximum Suppression (NMS), Soft NMS, Non-Maximum Weighted (NMW) and Weighted boxes fusion (WBF)

## Results
- Some sample detection images are as follows:
- SSD:
  ![image](https://github.com/sruthi0107/Threat-Object-Detection-in-Baggage-Screening/assets/63657533/6e189e59-3ca5-4064-9ff4-fe5cf0095530)
- Faster RCNN:
  ![image](https://github.com/sruthi0107/Threat-Object-Detection-in-Baggage-Screening/assets/63657533/695476eb-6bc6-40b6-8d9f-014106748687)
- Ensemble - NMS
  ![image](https://github.com/sruthi0107/Threat-Object-Detection-in-Baggage-Screening/assets/63657533/4de88976-cb5d-4dc4-b95c-c01c1e1ee9d3)

## Acknowledgements
- the ensemble-boxes package was used to perform the ensemble for NMS, Soft-NMS, NMW and WBF. Check out their repository [here](https://github.com/ZFTurbo/Weighted-Boxes-Fusion)
- mAP score calculation was performed using the following repository: https://github.com/Cartucho/mAP

## Useful Links
- https://www.youtube.com/watch?v=XoMiveY_1Z4&t=10s


