# Enhanced-News-Classification-On-Large-Dataset
## Introduction

In this task, we have a large (2 GB) dataset where one column contains the text of news articles, and another column indicates the category or topic of the news. The goal of this project is to develop a neural network model to classify news articles into their respective categories. The dataset has been preprocessed with Tokenization and Feature Extraction.
### Initial Processing:
The first step involves improving and refining the category labels. A review of the titles shows that some titles are synonymous or belong to the same broader category. These titles are merged to improve the accuracy of the classification. The result is a set of main categories, and any null values in the dataset are identified and removed.
before merge :


<img src="https://github.com/user-attachments/assets/39efe331-69d0-4cf5-af05-06aecf6c796c" width="400">


after merge :


<img src="https://github.com/user-attachments/assets/d597e3d1-edb8-4f37-898a-e5cffec5aed8" width="400">


### Train, Test, and Split:
To optimize the model and reduce overfitting, the dataset is split into training and testing sets. The goal is to ensure that the training data contains an equal number of samples from each category, making the data balanced. The dataset is then split into training and testing sets, with the training set representing 80% of the data and the testing set representing 20%.


<img src="https://github.com/user-attachments/assets/9fb37e1f-a67a-490a-a1cf-b4db5e798a67" width="400">


### Tokenization and Feature Extraction:
Tokenization is performed to break down the text into words or tokens, and the TF-IDF (Term Frequency-Inverse Document Frequency) method is used for feature extraction. This method highlights the importance of a word within a document relative to a collection of documents. Various parameters like ngram_range and max_features are tuned to control the tokenization process and the number of features extracted. It is important to mention that using TF-IDF after seperating train and test results in more negatives comparing to real - life use.

### Artificial Neural Network (ANN):
The neural network architecture is designed for the task. Recurrent Neural Networks (RNNs) are typically used for natural language processing tasks, but the complexity of such networks can lead to overfitting. To prevent this, the network architecture includes dropout layers, which deactivate a fraction of the neurons during training to avoid overfitting. The final output layer uses a softmax activation function to classify the input into one of the predefined categories. We use adam as optimizer and categorical cross entropy for loss.


![image](https://github.com/user-attachments/assets/02bb385f-9c73-484b-8eec-65f709a941ef)


### Model Evaluation:

The model is evaluated using the following methods:

    Cross-Validation: A common method in machine learning to assess how the model generalizes to an independent dataset.
    Confusion Matrix: A tool to visualize the performance of the classification model by showing the correct and incorrect predictions.
    K-Folds Cross-Validation: The dataset is split into k parts, where each part is used as a test set while the rest are used as the training set. This method provides a more robust evaluation of the model's performance.

### User Interface Implementation:

User interface is created using the Gradio library, which allows for easy integration of the model into an interactive environment, such as Google Colab, where users can input new text data and receive classification predictions from the model. Last Cell in the notebook contains the implementation.


<img src="https://github.com/user-attachments/assets/87b0dbaf-7319-4be3-9f22-a540e131bb6d" width="800">


#### Note that the dataset used for this project is not included in the repository; In case of need for the dataset , email me under honarvar.negar.sedighian@gmail.com 
