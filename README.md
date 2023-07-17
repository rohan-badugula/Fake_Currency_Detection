# Fake-Currency-Detection-and-Denomination-Recognition
The main objective of this project is to develop an user interface that utilizes image processing and computer vision techniques to classify images as either fake or original banknotes. Specifically, the system aims to identify fake Indian currency notes by comparing them with authentic Indian currency notes.
## Overview
This project focuses on two essential aspects of currency recognition:

### 1. Denomination Detection:
The first part of the project aims to determine whether the input currency note is a 500 or 2,000 denomination. We will utilize image processing and computer vision techniques to extract relevant features and classify the currency based on its denomination.

### 2. Fake Note Detection:
In the second part, we will process the respective currency notes and extract distinctive features. These features will be compared with authentic notes to identify whether the currency is genuine or counterfeit.
![Picture1](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/37b4f39f-fcb3-4a1f-8edc-825ca73a17c5)
## Finding Denomination of Input Currency

This project focuses on determining the denomination of the input currency note, whether it is a 500 or 2000 rupee note. Three methods are employed for this purpose:

### Method 1: Bleed Line Detection
In this method, we calculate the number of bleed lines by iterating over each column of the thresholded image. By counting black regions in each column, we can detect bleed lines. Based on the average number of bleed lines, we identify the denomination as either 500 or 2000.

### Method 2: Dominant Color Extraction using k-means Clustering
Here, dominant colors are extracted from the currency image using k-means clustering. The standard deviation of the red component is calculated to determine the currency's dominance. If the red standard deviation is greater than 40, the note is recognized as a 500 rupee note; otherwise, it is identified as a 2000 rupee note.

### Method 3: ORB and ML Techniques
ORB (Oriented FAST and Rotated BRIEF) is used to detect and compute key points and descriptors for the trained set and test image. Brute-force k-nearest neighbors (knn) matching is employed to find good matches based on distances. The denomination is determined using the maximum point obtained.

Each of these methods efficiently identifies the denomination, allowing further processing of the respective currency notes for fake or genuine recognition.
![pi](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/77e536aa-f89e-499e-8dd5-32fd6af3dc61)

## Dataset Preparation
The project involves creating a comprehensive dataset consisting of images related to both real and fake currency notes. The dataset will be organized into two sub-datasets for Rs. 500 and Rs. 2000 currency notes.
## Architecture
![35](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/a5930f6b-8fed-4f43-a3dc-2d3f5eabf4af)

## Methodology

The currency recognition system involves three main algorithms for feature extraction and identification, along with a final step for displaying the output to the user. Here is a concise overview of the methodology:

### Algorithm 1: Feature Detection using ORB
1. Utilize ORB (Oriented FAST and Rotated BRIEF) for feature detection and matching.
2. Detect security features in the test currency image using ORB, and define a search area for each feature.
3. Crop the highlighted area and apply grayscale and Gaussian blur to extract the features.
4. Compare the extracted features with the corresponding templates using the Structural Similarity Index (SSIM) to determine similarity.

### Algorithm 2: Bleed Line Detection
1. Crop the region containing the bleed lines from the input currency note image.
2. Threshold the image to keep only the black bleed lines on a white background.
3. Count and verify the number of bleed lines on the left and right sides of the currency note.
4. The count should be approximately 5 for Rs 500 currency notes and 7 for Rs 2000 currency notes.

### Algorithm 3: Number Panel Detection
1. Apply image thresholding with multiple values to isolate the black characters in the number panel on a white background.
2. Perform contour detection on the thresholded image of the number panel.
3. Find bounding rectangles for each contour and eliminate erroneous rectangles.
4. Calculate the number of characters in the number panel for each threshold value.
5. The algorithm terminates when it finds 9 characters in three consecutive rounds or when the threshold value reaches its maximum value.

### Displaying Output
1. Show the extracted image and key statistics for each feature in a GUI window.
2. Provide the status (Pass/Fail) for each feature.
3. Determine the total number of features that passed successfully for the input currency note.
4. Use the total passed features to determine if the note is genuine or fake.

The complete GUI is built using the tkinter package in Python, allowing users to interact with the system and obtain the classification results for the input currency note.
## Performance Analysis
![35](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/42a784c4-f257-422e-b117-3f7fe14441c6)
## Output
![1](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/eae8992a-8cc8-4664-9153-c60771cbfd80)
![2](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/a78dd326-d19b-4dfc-86a9-c1743b5c58cb)
![3](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/affb7598-9a92-4efa-8ace-c9c7ffea8ba5)
![4](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/5494c594-0252-4487-a6b6-92c1d4a9fae5)
![5](https://github.com/Gunti-Swathi/Fake-Currency-Detection-and-Denomination-Recognition/assets/75379302/7202895a-5138-43fd-aa98-b2e8a8fce7c2)
