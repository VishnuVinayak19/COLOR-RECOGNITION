# COLOR-RECOGNITION
Color recognition is a computer vision technique used to identify and classify colors within images or visual data. In data analysis, this capability can be leveraged to extract meaningful insights from image-based datasets, such as detecting product colors in retail, identifying dominant colors in artworks, or analyzing satellite imagery.Using Python, libraries like OpenCV, Pillow, and matplotlib help in image processing, pixel-level color extraction, and visualizations. Colors can be analyzed in RGB, HSV, or HEX formats, and clustering techniques like K-Means are often applied to detect dominant color palettes.

With SQL, the extracted and transformed color data (e.g., HEX codes, frequency counts, object associations) can be stored in structured databases for efficient querying and reporting. SQL enables analysts to perform aggregations, joins, and filters to correlate color features with other data dimensions (such as time, location, or user behavior).

Use Cases:

Identifying most popular product colors in sales data

Tracking color trends over time in fashion datasets

Automating quality control by detecting color defects in manufacturing

This integration of Python for color extraction and SQL for structured analysis forms a powerful workflow for turning unstructured visual data into actionable insights.

You can use color_recognition_api to perform real-time color recognition in your projects. You can find a sample usage of color_recognition_api in this repo. Please contact if you need professional color recognition project with the super high accuracy!

Run color_classification_image.py to perform color recognition on a single image.


<img width="480" height="424" alt="42423806-14cdfa7a-8309-11e8-9478-23d50fc0002f" src="https://github.com/user-attachments/assets/7af535dd-c0c1-4f0a-92f5-6350c9978f94" />

What does this program do?

Feature Extraction: Perform feature extraction for getting the R, G, B Color Histogram values of training images
Training K-Nearest Neighbors Classifier: Train KNN classifier by R, G, B Color Histogram values
Classifying by Trained KNN: Read Web Cam frame by frame, perform feature extraction on each frame and then classify the mean color of it by trained KNN classifier.

TODOs:

* "Add New Color" utility will be added.
* New feature extractors will be added.
* New classifiers will be added.

The![ConspiracyCharlieDayGIF](https://github.com/user-attachments/assets/670ea93f-ae1e-47d9-bf71-7fe948fb3aac)
ory
In this study, colors are classified by using K-Neares Neşghbor Machine Learning classifier algorithm. This classifier is trained by image R, G, B Color Histogram values. The general work flow is given at the below.

<img width="986" height="700" alt="35335133-a9632c70-0125-11e8-9204-0b4bfd0702a7" src="https://github.com/user-attachments/assets/2efe0d7c-70fa-4f93-ac2b-28ef33f89127" />

You should know 2 main pheomena to understand basic Object Detection/Recognition Systems of Computer Vision and Machine Learning.

1.) Feature Extraction

How to represent the interesting points we found to compare them with other interesting points (features) in the image.

2.) Classification

An algorithm that implements classification, especially in a concrete implementation, is known as a classifier. The term "classifier" sometimes also refers to the mathematical function, implemented by a classification algorithm, that maps input data to a category.

For this project;

1.) Feature Extraction = Color Histogram

Color Histogram is a representation of the distribution of colors in an image. For digital images, a color histogram represents the number of pixels that have colors in each of a fixed list of color ranges, that span the image's color space, the set of all possible colors.
<img width="484" height="301" alt="34918867-44f5feaa-f96b-11e7-9994-1747846266c9" src="https://github.com/user-attachments/assets/643dab6d-9add-4cf1-ad1a-99656bc52a65" />

2.) Classification = K-Nearest Neighbors Algorithm

K nearest neighbors is a simple algorithm that stores all available cases and classifies new cases based on a similarity measure (e.g., distance functions). KNN has been used in statistical estimation and pattern recognition already in the beginning of 1970’s as a non-parametric technique.
<img width="564" height="315" alt="34918895-c7b94d24-f96b-11e7-87da-8619d9bd4246" src="https://github.com/user-attachments/assets/a3fbc42d-5fc4-4ac2-b64d-664a3645ba83" />

Implementation:

OpenCV was used for color histogram calculations and knn classifier. NumPy was used for matrix/n-dimensional array calculations. The program was developed on Python at Linux environment.

In the “src” folder, there are 2 Python classes which are:

color_classification_webcam.py: test class to perform real-time color recognition form webcam stream.

color_classification_image.py: test class to perform color recognition on a single image.

In the “color_recognition_api” folder, there are 2 Python classes which are:

feature_extraction.py: feature extraction operation class

knn_classifier.py: knn classification class

1.) Explanation of “feature_extraction.py"

I can get the RGB color histogram of images by this Python class. For example, plot of RGB color histogram for one of the red images is given at the below.
![34919478-f198beb8-f975-11e7-8c1c-0a552f7cd673](https://github.com/user-attachments/assets/513d8587-6ebf-4b5b-8ffd-05ed0345c764)

I decided to use bin number of histogram which has the peak value of pixel count for R, G and B as feature so I can get the dominant R, G and B values to create feature vectors for training. For example, the dominant R, G and B values of the red image which is given at above is [254, 0, 2].

I get the dominant R, G, B values by using Color Histogram for each training image then I labelled them because KNN classifier is a supervised learner and I deploy these feature vectors in the csv file. Thus, I create my training feature vector dataset. It can be found in the file which name’s is training.data under src folder.

2.) Explanation of “knn_classifier.py”

This class provides these main calculations;

Fetching training data
Fetching test image features
Calculating euclidean distance
Getting k nearest neighbors
Prediction of color
Returning the prediction is true or false
“color_classification_webcam.py” is the main class of my program, it provides;

Calling feature_extraction.py to create training data by feature extraction
Calling knn_classifier.py for classification
You can find training data in here.

You can find features are got from training data in here.

Conclusion:

I think, the training data has a huge important in classification accuracy. I created my training data carefully but maybe the accuracy can be higher with more suitable training data.

Another important thing is lightning and shadows. In my test images, the images which were taken under bad lighting conditions and with shadows are classified wrong (false positives), maybe some filtering algorithm should/can be implemented before the test images send to KNN classifier Thus, accuracy can be improved.

Citation:

If you use this code for your publications, please cite it as:

@ONLINE{cr,
    author = "Vishnu Vinayak",
    title  = "Color Recognition",
    year   = "2024",
    url    = "https://github.com/VishnuVinayak19/COLOR-RECOGNITION/edit/main/README.md"
}

License:

This system is available under the MIT license. See the LICENSE file for more info.






