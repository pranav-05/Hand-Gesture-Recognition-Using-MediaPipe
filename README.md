# Hand-Gesture-Recognition-Using-MediaPipe
This project is about the ML approach to recognize the Hand Gestures using MediaPipe and OpenCV libraries. 

## **Problem Statement :**
   Develop the solution for detection of hand gesture and deliver the output in audio format.

## **INPUT :-**
- Video Frames

## **OUTPUT :-**
- Label of recognized hand gesture
- Audio of recognized hand gesture

## **SYSTEM REQURIMENTS :**
   **1) Python:** A Programming Language.
   2) MediaPipe: This library allows Python to detect the real-world objects i.e.,hands which is a basically an API. It helps in diving into common natural language processing (NLP) tasks such as object detection, classifying objects, detecting and tracking of human faces, poses etc.
   
  ![hand_tracking_3d_android_gpu](https://user-images.githubusercontent.com/70014211/165946412-7deee1ab-03d2-4675-a156-2853f5cb10a4.gif)
   
   3) OpenCV: It is a Python library for capturing and processing video frames. It gives real time processing of frames generated by camera.
   4) Pyttx3: It is a text-to-speech conversion library in python. Which basically works offline and generate the audio form of provided string.

## **ALGORITHM :** :
   1) Import OpenCV, MediaPipe, NumPy, pyttsx3 libraries.
   2) Create objects of each library with alas 
   3) From MediaPipe use hand connections and hands landmarks function to track the hand and get landmarks of hands.
   4) Define two functions, one for counting fingers and another for recognizing the gestures.
   5) Call the functions with video frames generated by OpenCV as input parameter.
   6) Display the generated image as well as gesture name of cv2 frames.
   7) Play the audio of corresponding gesture using engine of pyttsx3.

## **SOLUTION :**
   1. MediaPipe object detection API detect the hands from the frames. Basically, this library tracks the 21 3D key points of the hand. These key points and their labels are shown below in hand landmarks diagram.
   2. Currently I am  working on only single hand i.e., on right hand to avoid confusion at the delivered audio output.
   3. Palm is the starting point which has given 0 index. All the five fingers are divided into 4 parts each.
   4. Every key point has its own x, y and z coordinates associated with it. Which represent the distances on each key point from x, y and z axis.
   5. Our task is to build the logic in a such way that when these key points match to a particular hand gesture structure then our output is satisfied.E. g.
      - UNITE: 
          - For this gesture all the fingers should be folded as shown in below image.
          - Values of y coordinates of 
              a. INDEX_FINGER_TIP should be greater than INDEX_FINGER_MCP
              b. MIDDLE_FINGER_TIP should be greater than MIDDLE_FINGER_MCP
              c. RING_FINGER_TIP should be greater than RING_FINGER_MCP
              d. PINKY_FINGER_TIP should be greater than PINKY_FINGER_TIP
          - Also, the x-coordinates of THUMB_TIP >THUMB_IP >THUMB_MCP>THUMB_CMC



## **HAND LANDMARKS:**
   <img width="646" alt="Hand landmarks" src="https://user-images.githubusercontent.com/70014211/165948282-488840b8-3b51-45c7-a9db-992c341b025f.png">
   
## **FLOWCHART:**
   ![flow](https://user-images.githubusercontent.com/70014211/165948532-2e0fd0b7-8ccd-47ed-9f18-584b7cabd56a.png)



