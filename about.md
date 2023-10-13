# attention_checker
This Python script uses the OpenCV (Open Source Computer Vision Library) to create an application for checking a person's attentiveness based on their eye movements. It works by detecting faces and eyes in a video stream from a webcam and analyzing the behavior of the person's eyes.

Here's a step-by-step explanation of the code:

- Import necessary libraries: Import the OpenCV library (cv2) and the NumPy library (numpy) to work with images and data.

- Load pre-trained cascade classifiers: Two pre-trained cascade classifiers are loaded to detect faces and eyes. These classifiers are trained to recognize specific patterns in images.

- Define the check_attention function: This function takes a video frame as input and returns a measure of attentiveness. It does the following:

- Converts the frame to grayscale.
Uses the face cascade classifier to detect faces in the grayscale frame.
For each detected face, it extracts the region of interest (ROI) and uses the eye cascade classifier to detect eyes within that region.
For each detected eye, it calculates the mean intensity (brightness) of the eye region after applying a threshold to it. This mean intensity is used as a measure of attentiveness. If no eyes are detected, it returns -1.
Initialize the video capture: The script captures video from the default camera (usually the built-in webcam).

- Start an infinite loop: The code enters an infinite loop to continuously capture video frames and analyze attentiveness.

- Call check_attention for each frame: Inside the loop, the check_attention function is called for each captured frame.

- Display the result: Depending on the attentiveness measure, the script displays a message on the video frame using OpenCV's putText function. If no face is detected, it displays "No face detected." If the attentiveness is below 70 (a threshold value), it displays "Not attentive," and if the attentiveness is 70 or above, it displays "Attentive."

- Key press to exit: The script waits for the 'Esc' key to be pressed (key code 27) and breaks out of the loop to exit the application.

- Release video capture and close windows: Once the loop is exited, the video capture is released, and all OpenCV windows are closed.

This code can be used as a basic example for monitoring attentiveness in a real-time video stream, making it a potential building block for more advanced applications, such as the Student Attention Detection App.




