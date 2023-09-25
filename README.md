# Fake_image_detection

This code is a Python script that demonstrates how to train a binary image classification model to detect whether an image is genuine or fake. The code involves loading images, preprocessing them, defining a model, training the model, and evaluating its performance.

Here's a detailed explanation of each section of the code:

1. **Importing Libraries**:
   - The necessary Python libraries are imported, including Pandas for data manipulation, NumPy for numerical operations, ImageDataGenerator for data augmentation, and the required layers from Keras.

2. **Directory Paths and Parameters**:
   - Paths to the directories containing genuine and fake image data are specified.
   - Image dimensions (`img_height` and `img_width`) and batch size for training (`batch_size`) are defined.

3. **Image Filtering and Loading**:
   - Functions are defined to filter and load genuine and fake image files from the specified directories based on supported image formats (JPEG, PNG).
   - TIF files are converted to JPEG format using the PIL library.
   - DataFrames (`genuine_df` and `fake_df`) are created to store the image filenames and labels (genuine or fake).

4. **Data Augmentation**:
   - An `ImageDataGenerator` is initialized for data augmentation, including rescaling, rotation, shifting, and horizontal flipping.
   - Separate generators are created for training and validation using `flow_from_dataframe`.

5. **Custom Data Generator for Fake Images**:
   - A custom data generator is defined for fake images, as they are sampled directly from the DataFrame.
   - The generator loads and preprocesses the fake images during training.

6. **Model Definition**:
   - A sequential model is defined using Conv2D, MaxPooling2D, Flatten, Dense, and Dropout layers.
   - The model's architecture is summarized using `model.summary()`.
  
7. **Model Compilation and Training**:
   - The model is compiled with Adam optimizer and binary cross-entropy loss.
   - The model is trained using the training generator, specifying epochs and validation data.

8. **Model Evaluation on Fake Test Data**:
   - The model is evaluated on a generator created for fake images to measure the test accuracy on fake data.

9. **Model Saving**:
   - The trained model is saved to a file (`"fake_image_detection_model.h5"`).

The goal of this code is to create a simple binary classification model to distinguish genuine and fake images based on the provided training data. The dataset should be diverse and representative of the types of real and fake images expected in practice for accurate detection.
