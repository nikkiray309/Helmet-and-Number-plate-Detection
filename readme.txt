# 🪖 Helmet and Number Plate Detection🚗  
Detects whether a motorcycle rider is wearing a helmet and captures their number plate using YOLOv5 and CNN.

## 📌 Overview
This project is a real-time computer vision system built using:
- **YOLOv5** for number plate detection
- **Convolutional Neural Network (CNN)** for helmet classification
- A simple **Tkinter-based desktop app** as a prototype UI

The system identifies riders **without helmets** and captures their **vehicle number plates** for reporting or alerting purposes.

---

## 🛠️ Features
- Helmet vs No Helmet detection using trained CNN
- Number plate detection for non-helmet riders using YOLOv5
- webcam/video input support
- Easy-to-use Tkinter GUI
- GPU/CPU compatible
- TensorBoard support for training insights

---

## 🧰 Tech Stack
- Python  
- OpenCV  
- TensorFlow / Keras  
- PyTorch / YOLOv5  
- Tkinter  
- PIL, Numpy, etc.

---

## 🚀 Getting Started

## INSTALL REQUIREMENTS 

pip install -r requirements.txt

## TRAIN MODEL 

python train.py --name NAME_OF_MODEL --batch-size 2 --epochs 60 --cfg ./models/yolov5l.yaml --weights ./yolov5l.pt --data ./PATH_TO_data.yaml/  


# ARGS
 --img-size :- size of image if all images are same size (improves accuracy)
 --device :- cuda device, i.e. 0 or 0,1,2,3 or cpu
 --batch-size : iamges per batch as per gpu and system memory (higher reduce time per epoch)
 --epochs : training epochs (higher improves accuracy but sometimes overfit)
 --cfg :- model configuration; can be yolov5s.yaml, yolov5m.yaml, yolov5l.yaml, yolov5x.yaml
 --weights :- pretrained weights; can be yolov5s.pt, yolov5m.pt, yolov5l.pt, yolov5x.pt
 --data :- path to data.yaml file  


## DETECT 

python detect.py --device 0 --source ./PATH_TO_IMAGES_OR_VIDEO/ --weights ./PATH_TO_TRAINED_MODEL/

# ARGS 
 
  --device :- cuda device, i.e. 0 or 0,1,2,3 or cpu (if detect on gpu generate error then use cpu as argument)
  --weights :- path to trained model
  --source :- path to images or videos
  --img-size :- size of image if all images are same size (improves accuracy)
  --conf :- minimum confidence to detect object


## TENSORBOARD 

tensorboard --logdir runs/train 

# run above command in command prompt in same directory and then paste http://localhost:6006/  in any browser
