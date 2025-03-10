# Fall Detection from Video Footage

## Overview
This repository contains a vision-based fall detection system developed using deep learning techniques and pose estimation models. The goal is to detect falls from video footage accurately and efficiently. The project employs pre-trained models (MediaPipe and MoveNet) combined with classification algorithms (SVM, MLP, LSTM) to classify fall and non-fall events.
This project aims to address this challenge by leveraging computer vision and machine learning techniques.

## Features
- Pose estimation using MediaPipe and MoveNet.
- Classification of fall and non-fall activities using SVM, MLP, and LSTM models.
- Evaluation on benchmark datasets (Le2i and URFD).
- Real-time fall detection prototype.


## Datasets
The project uses the following publicly available datasets:
- **Le2i Fall Detection Dataset:** Used for training and validation.
- **URFD Dataset:** Used for testing and evaluation.

## Usage
1. Prepare your datasets by following the data preprocessing steps.
2. Train the models using the training scripts provided.
3. Test the models on the URFD dataset.


## Installation

To run the prototypes, execute the `PrototypesDemo.ipynb` file. It is recommended to use **Google Colab**, as the code was developed and tested on that platform.

### Setup

Before running the code, make sure to:

- **Install all dependencies** and ensure they are correctly configured.
- **Verify the paths** to the video and model files.
- **Check the output directory permissions** to ensure that the script can write files.

### Main Functions to Generate Output

The main functions to get the output are:

```python
createDemoVideo(vid_num, VIDPATH, TEST, mv_svm_model, mp_svm_model, 'svm')
createDemoVideo(vid_num, VIDPATH, TEST, mv_mlp_model, mp_mlp_model, 'mlp')
createDemoVideo(vid_num, VIDPATH, TEST, mv_lstm_model, mp_lstm_model, 'lstm')
```
#### Parameters:
- `vid_num`: Set an identifier or number for the video.
- `VIDPATH`: The path where the video is located.
- `TEST`: A boolean indicating whether to start running or not (set to `True` to start).
- The rest of the parameters should remain unchanged to get the full output.
- You can comment out any of the `createDemoVideo` calls (SVM, MLP, or LSTM) to get the specific model's output.

### Output for a Single Video Input

For each video input, the output includes:

- **Six Annotated Videos**: Videos with pose landmarks and fall detection annotations.
- **Six CSV Files**: Detailed fall detection results per frame, including:
  - `Video_num`: Video identifier or number.
  - `frame_indx`: Frame index.
  - `predictions`: 
    - `0` or `1` for SVM predictions.
    - A float value (ranging from 0 to 1) for MLP and LSTM predictions.
  - `frame_processing_duration`: Execution time for processing each frame (in milliseconds).
  - `fall_detection_duration_perVideo`: Timestamp of the first frame where a fall is detected.
  - `frame_width`: Width of the frame.
  - `frame_height`: Height of the frame.

All files are saved in the specified `OUT_directory`.
```
