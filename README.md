# Drowsiness Detection System  

## Project Overview  
The **Drowsiness Detection System** is a real-time application designed to monitor driver alertness by detecting eye states (open or closed) and triggering an alarm if prolonged drowsiness is detected. This system leverages computer vision and deep learning techniques to enhance road safety by preventing accidents caused by driver fatigue.

---

## Features  
- **Real-Time Eye Detection**: Uses OpenCV and Haar Cascades to detect eyes and faces in a live video feed.  
- **Deep Learning Model**: A pre-trained neural network classifies eyes as either "Open" or "Closed."  
- **Alert System**: Triggers an audible alarm if the driver’s eyes remain closed for an extended duration.  
- **Visual Feedback**: Displays live annotations of face and eye states along with a drowsiness score.  

---

## Prerequisites  

1. **Programming Language**: Python 3.x  
2. **Libraries and Dependencies**:  
   - OpenCV  
   - TensorFlow/Keras  
   - NumPy  
   - Pygame (for alarm sound)  

Install the required packages using the following command:  
```bash  
pip install opencv-python tensorflow numpy pygame  
```  

3. **Pre-trained Model**: A deep learning model (`model.h5`) trained to classify eye states.  
4. **Alarm Sound File**: An `alarm.wav` file to alert the driver in case of drowsiness.  

---

## How It Works  
1. **Face and Eye Detection**:  
   - Uses Haar Cascades for face and eye detection in a grayscale video feed.  
2. **Eye Classification**:  
   - Captured eye images are resized and normalized.  
   - The model predicts the probability of the eyes being "Open" or "Closed."  
3. **Drowsiness Scoring**:  
   - A score is incremented for consecutive frames where the eyes are detected as "Closed."  
   - If the score exceeds a threshold, the alarm is triggered.  
   - The score is decremented when the eyes are detected as "Open."  

---

## Code Structure  
- **`face_cascade` and `eye_cascade`**: Haar cascade models for face and eye detection.  
- **`model.h5`**: Deep learning model to classify eye states.  
- **`mixer.Sound`**: Pygame's sound module for alarm playback.  
- **Real-Time Feed Processing**:  
  - Captures frames using OpenCV.  
  - Annotates faces, eye states, and drowsiness scores on the video feed.  

---

## Usage Instructions  
1. Ensure your camera is connected and operational.  
2. Place the `model.h5` and `alarm.wav` files in the same directory as the script.  
3. Run the script:  
   ```bash  
   python drowsiness_detection.py  
   ```  
4. Press **'q'** to exit the application.  

---

## Customization  
- **Drowsiness Threshold**: Modify the `score > 20` condition to adjust the sensitivity.  
- **Alarm Sound**: Replace `alarm.wav` with a custom audio file of your choice.  
- **Camera Index**: Adjust `cv2.VideoCapture(1)` to `cv2.VideoCapture(0)` if the primary camera is at index 0.  

---

## Challenges and Limitations  
- **Lighting Conditions**: Performance may vary in low-light environments.  
- **Model Accuracy**: Ensure the pre-trained model is robust and trained on diverse datasets.  
- **Face Occlusions**: Glasses or other obstructions may affect eye detection.  

---

## Future Enhancements  
- Integrate yawning detection for enhanced fatigue monitoring.  
- Improve robustness in varying lighting conditions using advanced image processing techniques.  
- Deploy as a mobile or embedded application for portability.  

---

## Conclusion  
This **Drowsiness Detection System** provides an effective solution for enhancing road safety by monitoring driver alertness in real time. Its integration of deep learning and computer vision showcases the potential of AI-driven safety systems.  
