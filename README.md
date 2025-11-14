## Helmet and Number Plate Detection

This project provides a real-time computer vision system to detect whether a motorcycle rider is wearing a helmet and, if not, to detect their vehicle's number plate. The system is built using YOLOv5 and includes a simple prototype GUI created with Tkinter.

## Features

*   **Helmet Detection**: Classifies riders into two categories: `helmet` or `no-helmet`.
*   **Number Plate Detection**: Detects and localizes number plates, primarily for riders without helmets.
*   **Flexible Input**: Supports detection on both static images and video files.
*   **GUI Application**: A user-friendly desktop application built with Tkinter for easy interaction and file selection.
*   **Training and Inference**: Includes complete scripts for training a custom YOLOv5 model and running inference.
*   **Performance Monitoring**: Integrated with TensorBoard for visualizing training metrics and model performance.

## Tech Stack
* Python  
* OpenCV  
* TensorFlow / Keras  
* PyTorch / YOLOv5  
* Tkinter  
* PIL, Numpy, etc.

## Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites

*   Python 3.8 or later
*   Pip

### Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/nikkiray309/Helmet-and-Number-plate-Detection.git
    cd Helmet-and-Number-plate-Detection
    ```

2.  **Install the required dependencies:**
    ```sh
    pip install -r requirements.txt
    ```

3.  **Download pre-trained YOLOv5 weights:**
    These weights serve as a starting point for training your custom model.
    ```sh
    bash weights/download_weights.sh
    ```

## Usage

You can train a new model, run inference from the command line, or use the provided GUI application.

### Training the Model

To train the model on your custom dataset, run `train.py` with your specified parameters.

```sh
python train.py --data path/to/your/data.yaml --cfg ./models/yolov5l.yaml --weights ./yolov5l.pt --batch-size 4 --epochs 100
```

**Key Training Arguments:**

*   `--data`: Path to your dataset's `.yaml` configuration file.
*   `--cfg`: Model configuration file (e.g., `yolov5s.yaml`, `yolov5m.yaml`, `yolov5l.yaml`).
*   `--weights`: Path to initial weights (e.g., `yolov5l.pt`).
*   `--batch-size`: Number of images per batch. Adjust based on your GPU memory.
*   `--epochs`: Number of training epochs.
*   `--img-size`: Training image size.
*   `--device`: Device to run on, e.g., `cpu` or `0` for CUDA device 0.

### Running Inference

#### Command-Line Inference

Use `detect.py` to run detection on images or videos. The results, including images with bounding boxes, will be saved in the `runs/detect/exp` directory.

```sh
python detect.py --weights path/to/your/best.pt --source path/to/your/image_or_video.jpg --device cpu
```

**Key Inference Arguments:**

*   `--weights`: Path to your trained model weights (`best.pt`).
*   `--source`: Path to the input image, video, or directory.
*   `--conf-thres`: Object confidence threshold for detection.
*   `--img-size`: Inference image size.

#### GUI Application

Launch the Tkinter application to use a graphical interface for detection.

```sh
python main.py
```

The application allows you to browse and select an image or video file. After processing, the result will be displayed in a new window.

### Monitoring with TensorBoard

You can monitor the training process, including loss and accuracy metrics, using TensorBoard.

1.  Launch TensorBoard and point it to the training logs directory:
    ```sh
    tensorboard --logdir runs/train
    ```

2.  Open your web browser and navigate to `http://localhost:6006/` to view the dashboard.


