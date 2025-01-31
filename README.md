# object-detection-YOLOv11

This repository is for the YOLOv11-CV baseline test to, test its performance on object detection for parcels, doors, people, numbers and characters. 

## Setup and installations 

To install the repo locally, you will need [Poetry](https://python-poetry.org/). Once Poetry is installed, make sure your current directory is where the [pyproject.toml](pyproject.toml) file resides and run 
```
poetry shell
poetry install
```
This should create a virtual environment and install all the required dependancies in it. Note in order to export to tflite format python 12 is required with this setup.

## Preprocessing pipeline 

The preprocessing.ipynb combines a set of separate datasets that are already have YOLO format annotations with labels and images in one folder, located inside `datasets/separate_datasets`. Additionally, it splits them into 60-20-20 train-val-test splits and places them in appropriate labels & images folders as required for YOLOv11 training.

![Data Folder Structure](assets/data_structure.png)

*Figure 1: Required data digestion folder structure for preprocessing*

## Training pipeline

The training.ipynb file runs the training for the YOLOv11 model. Then it exports it to `.onnx` format and `.tflite` format. Finally, a few test inferences are demonstrated on each class of interest.