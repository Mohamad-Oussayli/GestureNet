# GestureNet

# American Sign Language Recognition Using CNN

## Why This Project is Necessary
Sign language is an essential mode of communication for individuals who are deaf or hard of hearing. However, there is often a communication gap between sign language users and those who don't understand sign language. Automating the recognition of American Sign Language (ASL) gestures can help bridge this gap by providing a tool that interprets sign language in real-time, fostering inclusion and better communication.

## Dataset
To train and test the model, I used the [Sign Language MNIST dataset](https://www.kaggle.com/datasets/datamunge/sign-language-mnist). You can download the dataset from Kaggle and use it for your own projects.

## Steps
1. **Data Preprocessing:**
   - Ensured that counts across all categories were similar.
   - Checked for null values in the dataset.
   - Separated the images from their corresponding labels.
   - Reshaped images to match the input requirements of the CNN model.
   - Applied LabelBinarizer to the labels.
   - Split the data into training and development (dev) sets.

2. **Data Augmentation:**
   - Performed data augmentation techniques to artificially increase the dataset size and improve model generalization.

3. **Model Architecture:**
   - Built the model using a series of convolutional layers and fully connected layers to perform classification.

### Convolutional Neural Network (CNN) Architecture

- **Convolutional Layer 1:**
  - Units: 128
  - Kernel Size: 5x5
  - Stride: 1
  - Activation Function: ReLU
  - Padding: Same
- **MaxPooling Layer 1:**
  - Pool Size: 2x2
  - Stride: 2

- **Convolutional Layer 2:**
  - Units: 64
  - Kernel Size: 3x3
  - Stride: 2
  - Activation Function: ReLU
  - Padding: Same
- **MaxPooling Layer 2:**
  - Pool Size: 2x2
  - Stride: 2

- **Convolutional Layer 3:**
  - Units: 64
  - Kernel Size: 3x3
  - Stride: 1
  - Activation Function: ReLU
  - Padding: Same
- **MaxPooling Layer 3:**
  - Pool Size: 2x2
  - Stride: 2

- **Dense Layer 1:**
  - Units: 128
  - Activation Function: ReLU

- **Dense Layer 2:**
  - Units: 64
  - Activation Function: ReLU

- **Output Layer:**
  - Units: 24 (corresponding to 24 sign language classes)
  - Activation Function: Softmax

4. **Model Training:**
   - The model was compiled and trained on the dataset.
   - Training and dev accuracy were plotted for visual analysis of model performance.

5. **Performance Metrics (Training Set):**
   - **Accuracy**: 98%
   - **Precision**: High precision across most classes.
   - **Recall**: High recall for most classes.
   - **F1-Score**: Balanced F1-scores across classes.

6. **Model Evaluation on Test Set:**
   - **Accuracy**: 94%
   - **Precision**: Generally high, with class 21 showing lower precision (0.68).
   - **Recall**: Most classes had perfect recall, but class 20 had lower recall (0.79).
   - **F1-Score**: High F1-scores for most classes, but lower for some like class 20 (0.88).


   **Conclusion**:
   The model performs very well on the test set with 94% accuracy, demonstrating strong generalization. While the performance on the test set is slightly lower compared to the dev set, the results are still promising. The model shows potential for real-world application, though there may be room for further optimization.
