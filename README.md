# Billboard Fault Detection

## Project Overview

This project implements a real-time dark spot detection system using YOLOv8, designed to monitor an input directory for new image files. When a new image is detected, it's automatically processed by a pre-trained YOLOv8 model to identify "dark spots." If a dark spot is found, the original image is copied to a designated `detected` folder. The system also includes a Streamlit web application for manual image uploads, visualization of detections, and model management.

## Features

* **Real-time Folder Monitoring:** Automatically detects and processes new images dropped into a specified `input_images` directory.
* **YOLOv8 Dark Spot Detection:** Utilizes a custom-trained YOLOv8 model (`fault1.pt`) to accurately identify "dark spots" in images.
* **Automated Image Archiving:** Copies images containing detected dark spots to a separate `detected` folder.
* **Streamlit Web UI:**
    * Upload images manually for immediate dark spot detection and visualization.
    * View annotated images with bounding boxes around detected dark spots and other classes.
    * Display detection confidence scores.
* **Modular Design:** Separate scripts for monitoring, detection utilities, and the Streamlit app.

## Technologies Used

* **Python 3.x**
* **YOLOv8 (Ultralytics Library)**: For object detection.
* **Streamlit**: For creating the interactive web application.
* **Watchdog**: For real-time file system monitoring.
* **Pillow (PIL)**: For image processing.
* **PyTorch**: Deep learning framework underpinning YOLOv8.

## Project Structure
├── app/
│   ├── config.py             # Configuration settings (paths to model, input/output dirs)
│   ├── monitor_script.py     # Script to monitor input_images folder
│   ├── detection_utils.py    # Utility functions for YOLO detection and image handling
│   ├── streamlit_app.py      # Streamlit web application
│   ├── input_images/         # Directory where new images are dropped for monitoring
│   ├── detected/             # Directory where images with detected "Dark Spot" are copied
│   ├── annotated/            # Directory where annotated images from Streamlit are saved
│   └── venv/                 # Python virtual environment
├── README.md                 # This README file
└── requirements.txt          # Python dependencies

## Setup and Installation

Follow these steps to get the project up and running on your local machine or server.python3 -m venv venv
source venv/bin/activate # On Linux/macOS
# .\venv\Scripts\activate # On Windows
```bash
git clone <your-repository-url>
cd <your-repository-name>
pip install -r ../../requirements.txt # Adjust path if requirements.txt is not at root

