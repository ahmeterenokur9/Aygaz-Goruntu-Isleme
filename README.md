**Aygaz Image Processing**  
**Project Title:** Animal Classification and Image Processing Project

**Project Summary:**  
This project involves developing, training, and evaluating a machine learning model to classify specific animal species using the "Animals with Attributes 2" dataset from Kaggle. The project also incorporates image manipulation and color constancy algorithms to improve performance under varying lighting conditions.

**Project Stages:**  
The project consists of four main stages:

1. **Data Preparation:** Organizing images of selected animal species and splitting them into training and testing datasets.  
2. **Machine Learning Model:** Designing, training, and evaluating a Convolutional Neural Network (CNN) model.  
3. **Image Manipulation:** Manipulating the brightness levels of images and testing model performance under different conditions.  
4. **Color Constancy:** Applying the Gray World algorithm to achieve color balance in images and analyzing its impact on model performance.

**Dataset:**  
- **Data Source:** Kaggle - Animals with Attributes 2  
- **Selected Animal Species:** Collie, Dolphin, Elephant, Fox, Moose, Rabbit, Sheep, Squirrel, Giant Panda, Polar Bear  
- **Data Size:** Up to 650 images per species, with 70% for training and 30% for testing.

**Libraries Used:**  
- **Data Processing:** os, shutil, Pillow  
- **Machine Learning:** TensorFlow, scikit-learn, ImageDataGenerator  
- **Visualization:** Matplotlib, OpenCV

**Analysis and Applications:**  
1. **CNN Model:**  
   - A 3-layer Convolutional Neural Network (CNN) was designed.  
   - The model was trained using categorical cross-entropy loss and the Adam optimization method.  
   - The model's accuracy was calculated on both the training and test sets.

2. **Image Manipulation:**  
   - Images were manipulated to different brightness levels (0.5, 1.0, 1.5).  
   - Model performance was analyzed on the manipulated dataset.

3. **Color Constancy:**  
   - The Gray World algorithm was applied to achieve color balance.  
   - The impact on model performance was evaluated.

**CNN Model Performance Analysis and Suggested Solutions:**  
**Current Performance Analysis:**  
Test results show a noticeable decline in performance across different datasets. The original test set had an accuracy of 60.71%, which dropped to 57.16% after light manipulations and 50.66% after applying color constancy.

**Possible Reasons for Performance Decline:**  
- **Impact of Color Constancy Algorithm:** The color constancy algorithm may have altered important features in the images, potentially losing discriminative characteristics.  
- **Model Architecture Durability:** The CNN model showed insufficient robustness to lighting changes, with feature extraction layers failing to extract consistent features under varying lighting conditions.

**Proposed Solutions:**  
1. **Data Augmentation Improvements:**  
   - Add images with manipulated lighting conditions to the training set.  
   - Apply data augmentation techniques such as brightness, contrast, and color transformations.  
   - Include random brightness and contrast augmentations to the model.

2. **Model Architecture Enhancements:**  
   - Add batch normalization layers to improve model robustness.  
   - Review and increase dropout rates if necessary.  
   - Use a deeper and wider architecture to increase model capacity.

3. **Revision of Color Constancy Approach:**  
   - Experiment with less aggressive normalization techniques instead of the current color constancy algorithm.  
   - Evaluate alternative image preprocessing techniques such as histogram equalization.  
   - Apply color constancy during training to ensure consistency.

4. **Ensemble Learning Approach:**  
   - Develop multiple models trained under different lighting conditions.  
   - Combine their predictions to create a more robust system.

**Project Kaggle Link:** [Aygaz Image Processing Bootcamp Project](https://www.kaggle.com/code/ahmeteren9/aygaz-g-r-nt-leme-bootcamp-projesi)
