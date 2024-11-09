Sign language detector with Python, OpenCV and Mediapipe !
# Sign Language Recognition System

A real-time sign language recognition system using computer vision and machine learning to detect and classify hand gestures for letters 'A', 'B', and 'L'. The system uses webcam input to capture hand movements, MediaPipe for hand landmark detection, and a trained machine learning model for classification.

## Project Summary
This project implements a real-time sign language letter detection system using OpenCV and MediaPipe for hand tracking, combined with machine learning for gesture classification. Required skills: Python programming, computer vision (OpenCV, MediaPipe), and machine learning fundamentals.

## Features
- Real-time hand gesture detection and tracking
- Recognition of three sign language letters (A, B, L)
- Visual feedback with hand landmark visualization
- Bounding box and prediction display
- Custom dataset creation capability

## Requirements
```
opencv-python
mediapipe
numpy
scikit-learn (or relevant ML framework)
pickle
```

## Project Structure
```
├── data/                  # Directory for training images
│   ├── 0/                # Images for letter 'A'
│   ├── 1/                # Images for letter 'B'
│   └── 2/                # Images for letter 'L'
├── collect_imgs.py        # Script for collecting training data
├── inference.py          # Main recognition script
└── model.p               # Trained model file
```

## Setup and Installation
1. Install required packages:
   ```bash
   pip install opencv-python mediapipe numpy scikit-learn
   ```
2. Ensure you have a working webcam
3. Clone the repository and navigate to the project directory

## Usage

### Data Collection
1. Run the data collection script:
   ```bash
   python collect_imgs.py
   ```
2. Follow the on-screen prompts to capture images for each gesture
3. Press 'Q' to start collecting images for each class
4. The script will automatically capture 100 images per gesture

### Running the Recognition System
1. Ensure your model is trained and saved as 'model.p'
2. Run the inference script:
   ```bash
   python inference.py
   ```
3. Make hand gestures in front of the camera to see predictions
4. Press 'Q' to quit the application

## How It Works
1. **Data Collection**: The system captures images of hand gestures using OpenCV
2. **Hand Detection**: MediaPipe's hand detection model identifies hand landmarks in real-time
3. **Feature Extraction**: The system extracts normalized coordinates of hand landmarks
4. **Classification**: A trained machine learning model predicts the corresponding letter
5. **Visualization**: Results are displayed with hand landmarks, bounding box, and predicted letter

## Customization
- Modify `number_of_classes` and `dataset_size` in collect_imgs.py to collect data for more gestures
- Update `labels_dict` in inference.py to include new gesture labels
- Adjust detection confidence threshold in `mp_hands.Hands()` for different sensitivity

## Limitations
- Currently supports only three letters (A, B, L)
- Requires good lighting conditions
- Single hand detection only
- Dependent on camera quality and position

## Future Improvements
- Add support for full alphabet
- Implement dynamic gesture recognition
- Add data augmentation for better model performance
- Improve robustness to different lighting conditions
- Add support for multiple hand detection

