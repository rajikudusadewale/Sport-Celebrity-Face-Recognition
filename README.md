# Sport-Celebrity-Face-Recognition
Image Classification, Machine Learning, SVM, OpenCV.


![](https://github.com/rajikudusadewale/Sport-Celebrity-Face-Recognition/blob/main/Model/image.png)


#### Introduction
The "Sport Celebrity Classifier" project embarked on the ambitious goal of applying machine learning techniques to accurately classify images of sports celebrities. Leveraging a variety of machine learning models, including Support Vector Machine (SVM), Logistic Regression, and TensorFlow-based neural networks, the project aimed to identify the most effective approach for this complex classification task.

#### Data Collection and Preprocessing
A comprehensive dataset of sports celebrities' images was meticulously compiled, serving as the foundation for the project. The data collection process was followed by a rigorous preprocessing phase, where images were standardized, cleaned, and augmented to ensure a robust dataset ready for machine learning models.


**Code Snippet: Data Preprocessing**
```python
# Example preprocessing steps
import cv2
import numpy as np

def preprocess_image(image_path):
    img = cv2.imread(image_path)
    img_resized = cv2.resize(img, (224, 224)) # Resizing to 224x224
    img_gray = cv2.cvtColor(img_resized, cv2.COLOR_BGR2GRAY) # Convert to grayscale
    img_normalized = img_gray / 255.0 # Normalize pixel values
    return img_normalized
```

*Explanation:* This snippet demonstrates a common preprocessing pipeline for image data. Images are first read from their paths, resized to a standard dimension (224x224 pixels in this case), converted to grayscale to reduce complexity, and finally normalized so that pixel values fall within the 0 to 1 range. These steps are crucial for ensuring consistency in the dataset, which aids in the effectiveness of the machine learning model.

#### Model Selection and Training
The project explored three distinct machine learning models: SVM, Logistic Regression, and TensorFlow-based CNNs. Each model was carefully trained and evaluated on the preprocessed dataset, with a keen focus on identifying which model would offer superior performance in classifying sports celebrities.

After extensive training and evaluation, the SVM model emerged as the top performer, demonstrating the highest accuracy and robustness among the tested models. This outcome underscored the SVM model's effectiveness in handling the nuances of image classification within the specific context of sports celebrity recognition.

#### Model Optimization and Export
With the SVM model identified as the most effective for our classification task, further optimization was undertaken to refine its performance. The final model was then saved, and the target class names were exported as a JSON file. This file, alongside the saved SVM model, was prepared for handover to the engineering team for production deployment.

#### Conclusion and Future Directions
The "Sport Celebrity Classifier" project successfully demonstrated the power of machine learning in the domain of image classification. By systematically exploring various models and optimizing the SVM model, the project achieved its goal of accurately classifying sports celebrities.

As we look to the future, there are several avenues for enhancing the project further. These include expanding the dataset with more diverse images, exploring additional machine learning models, and continuously refining the SVM model based on new data and feedback from the production environment.

#### Handover to Engineering Team
The successful completion of the project marked the beginning of its journey into production. The saved SVM model and the JSON file containing the target class names were handed over to the engineering team, ensuring a seamless transition from development to deployment. This collaboration between the data science and engineering teams is a testament to the project's holistic approach, bridging the gap between machine learning research and real-world application.

In conclusion, the "Sport Celebrity Classifier" project stands as a significant achievement in the application of machine learning to image classification. It highlights the importance of model selection, optimization, and collaboration in creating effective machine learning solutions ready for production.
