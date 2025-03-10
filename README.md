# Fall Detection from Video Footage

## Overview
This repository contains a vision-based fall detection system developed using deep learning techniques and pose estimation models. The goal is to detect falls from video footage accurately and efficiently. The project employs pre-trained models (MediaPipe and MoveNet) combined with classification algorithms (SVM, MLP, LSTM) to classify fall and non-fall events.

## Motivation
Falls, particularly among the elderly, are a critical health concern due to the high risk of severe injury or death. Detecting falls in real time can significantly improve response times and outcomes. This project aims to address this challenge by leveraging computer vision and machine learning techniques.

## Features
- Pose estimation using MediaPipe and MoveNet.
- Classification of fall and non-fall activities using SVM, MLP, and LSTM models.
- Comprehensive accuracy evaluation on benchmark datasets (Le2i and URFD).
- Detailed performance comparison and analysis.
- Real-time fall detection prototype.


## Datasets
The project uses the following publicly available datasets:
- **Le2i Fall Detection Dataset:** Used for training and validation.
- **URFD Dataset:** Used for testing and evaluation.

## Usage
1. Prepare your datasets by following the data preprocessing steps.
2. Train the models using the training scripts provided.
3. Test the models on the URFD dataset.
4. Use the prototype for real-time fall detection.

## Model Performance
The models achieved the following accuracy scores on the URFD dataset:
| Model | MediaPipe Accuracy | MoveNet Accuracy |
|------|--------------------|------------------|
| SVM  | 83.34%              | 84.07%           |
| MLP  | 83.11%              | 83.51%           |
| LSTM | 78.13%              | 78.56%           |

## References
- Charfi, I., et al. (2013). Optimized spatio-temporal descriptors for real-time fall detection.
- Kwolek, B., & Kepski, M. (2014). Human fall detection on embedded platform using depth maps and wireless accelerometer.
- Alam, E., et al. (2022). Vision-based human fall detection systems using deep learning: A review.
- Chua, J., et al. (2015). A simple vision-based fall detection technique for indoor video surveillance.
- Espinosa, R., et al. (2019). A vision-based approach for fall detection using convolutional neural networks.




## Installation
You only need to run the Prototypes file it is saved as "PrototypesDemo.ipynb".
It's best to use GoogleColab as the code was developed on it. 

Ensure all dependencies are installed and correctly configured.
Verify that the paths to the video files and model files are correct.
Check the output directory permissions to ensure the script can write files.


Main functions to get an output:

createDemoVideo(vid_num , VIDPATH , TEST , mv_svm_model , mp_svm_model , 'svm')
createDemoVideo(vid_num , VIDPATH , TEST , mv_mlp_model , mp_mlp_model , 'mlp')
createDemoVideo(vid_num , VIDPATH , TEST , mv_lstm_model , mp_lstm_model , 'lstm')

Parameters:
vid_num: Set an identifier or number for the video.
VIDPATH: The path where the video is located
TEST:  A bool indicating whether to start running or not.
Rest of the parameters should not be changes if you want the full output
You can comment any of three "createDemoVideo" to get a specific model output.

Output for a single video input
	* six Annotated Videos: Videos with pose landmarks and fall detection annotations.
	* six CSV Files: Detailed fall detection results per frame,including:
			>Video_num
			>frame_indx	
			>predictions: o or 1 for SVM and a float (from 0 to 1) for MLP and LSTM	
			>frame_proccessing_duration: execution time in milliseconds
			>fall_detection_duration_perVideo: timstep of the first frame fall prediction	
			>frame_width , frame_height
All Files saved in OUT_directory
