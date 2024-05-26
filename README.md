
### Environment Setup
##### This code is tested on python 3.9

Step -1 :  git clone https://github.com/THU-MIG/yolov10.git

Step -2 :  cd yolov10

Step -3 :  pip install .     

Step -4 : Download yolov10 pretrained weights from official repo (https://github.com/THU-MIG/yolov10)

Step -5 : Test Pretrained YOLOv10 model using this command: 

!yolo task=detect mode=predict conf=0.25 save=True model=../weights/yolov10n.pt source=test_images/1.jpg


##### Train Custom model:

Custom dataset is required for training the model. Sample dataset is in "custom_dataset" folder, Your dataset should have the same format.

Make changes in in custom_data.yaml file as per your dataset

##### Train model using this command:

!yolo task=detect mode=train epochs=100 batch=16 plots=True model=weights/yolov10n.pt data=custom_data.yaml

##### Inference using custom trained model:

!yolo task=detect mode=predict conf=0.25 save=True model=runs/detect/train/weights/best.pt source=test_images_1/veh2.jpg
