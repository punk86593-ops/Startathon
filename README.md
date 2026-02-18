# Offroad Semantic Segmentation - GHR 2.0 Hackathon Submission

## Team Information
Team Name: CHAI WITH COFFEE  
Team Members: Abhi Srivastava(leader), Nawansh Dwivedi, Parth Kaushik, Deepanshu Suthar  


## Project Overview

This project focuses on semantic segmentation for off-road autonomous systems.  
The objective is to train a deep learning model that assigns a class label to every pixel in a desert scene image using synthetic digital twin data.

The model is trained on a structured dataset containing training and validation splits and evaluated on a separate unseen test dataset.


## Model Architecture

- Backbone: DINOv2 (Pretrained Vision Transformer)
- Task: Pixel-wise Semantic Segmentation
- Loss Function: Cross Entropy Loss
- Optimizer: Adam
- Device Used: NVIDIA RTX 5050 Laptop GPU

The pretrained backbone enables strong feature extraction and improved generalization performance.


## Dataset Structure

The dataset is organized as follows:

Offroad_Segmentation_Training_Dataset  
├── train  
│   ├── Color_Images  
│   ├── Segmentation  
├── val  
│   ├── Color_Images  
│   ├── Segmentation  

Offroad_Segmentation_TestImages  
├── Color_Images  

Strict separation between training and testing data was maintained.


## Training Details

Baseline Training:
- Epochs: 10
- Training Samples: 2857
- Validation Samples: 317

Improvement Experiment:
- Epochs: 15
- Training Samples: 2857
- Validation Samples: 317

Agressive Experiment:
- Epochs: 25
- Training Samples: 2857
- Validation Samples: 317

Extereme Experiment:
- Epochs: 35
- Training Samples: 2857
- Validation Samples: 317

Training and validation losses were monitored to ensure stable convergence.


## Performance

Mean IoU Score(35 Epoch): 0.2373
Final IoU Score(15 Epoch): 0.326

The model demonstrated consistent learning behavior with decreasing training loss across epochs.  
Evaluation was performed strictly on unseen test data.


## Setup Instructions

1. Install Anaconda.
2. Navigate to Offroad_Segmentation_Scripts folder.
3. Run:

   cd ENV_SETUP  
   setup_env.bat  

4. Activate environment:

   conda activate EDU  

5. Train model:

   python train_segmentation.py  

6. Test model:

   python test_segmentation.py  


## Notes

- Model weights are stored in the `runs/` directory after training.
- No test data was used during training.
- Experiments were conducted to improve convergence and performance.


## Future Improvements

- Data augmentation
- Class-balanced loss functions
- Longer training schedules
- Domain adaptation for real-world deployment
