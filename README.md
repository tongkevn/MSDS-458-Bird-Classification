# MSDS 458 Bird Classification

<div class="cell markdown" id="g23QPInFcsbC">

# Kevin Tong - Bird Image Classification

</div>

<div class="cell markdown" id="Qvl4h-BZZA6-">

# Packages

</div>

<div class="cell code" execution_count="1"
executionInfo="{&quot;elapsed&quot;:9894,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692593458365,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="488m6E5qYX0e">

``` python
import datetime
import time
from packaging import version
from collections import Counter
import numpy as np
import pandas as pd

import matplotlib as mpl  # EA
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.metrics import confusion_matrix, classification_report
from sklearn.decomposition import PCA
from sklearn.manifold import TSNE
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import mean_squared_error as MSE
from sklearn.metrics import accuracy_score
from sklearn.model_selection import train_test_split

import tensorflow as tf
from tensorflow.keras.utils import to_categorical
from tensorflow import keras
from tensorflow.keras import layers, models
from tensorflow.keras.models import Sequential
import tensorflow.keras.backend as z
from tensorflow.keras.utils import plot_model
from tensorflow.keras.layers import Conv2D, MaxPool2D, BatchNormalization, Dropout, Flatten, Dense
from tensorflow.keras.callbacks import ModelCheckpoint, EarlyStopping
from tensorflow.keras.preprocessing import image
from tensorflow.keras.utils import to_categorical
from tensorflow.keras.layers import Dropout
import os
import cv2
from PIL import Image
from tensorflow.keras.regularizers import l2
```

</div>

<div class="cell code" execution_count="2"
executionInfo="{&quot;elapsed&quot;:2,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692593458365,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="XUE9jE77ZQ1w">

``` python
# from google.colab import drive
# drive.mount('/content/drive')
data_dir = '/content/drive/MyDrive/Northwestern MSDS/MSDS 458/458_Final_Notebooks/spectrogram_output'
```

</div>

<div class="cell markdown" id="HyKMQxD2dOW_">

# Preprocessing

</div>

<div class="cell code" execution_count="3"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:883753,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594342117,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="B229odF8eHLO" outputId="e6284bfe-fc8a-4ca0-f5d0-b8d01eb44868">

``` python
# Initialize a set to store unique classes (bird species)
unique_classes = set()

# Define a function to load and preprocess images
def load_and_preprocess_images(image_paths):
    images = []
    for path in image_paths:
        img = Image.open(path)
        img = img.resize((224, 224))  # Resize to your desired dimensions
        img = img.convert("RGB")  # Convert to RGB (remove alpha channel if present)
        img = np.array(img) / 255.0   # Normalize pixel values
        images.append(img)
    return np.array(images)

# Loop through directories and load images
all_images = []
for bird_folder in os.listdir(data_dir):
    bird_folder_path = os.path.join(data_dir, bird_folder)
    if os.path.isdir(bird_folder_path) and len(os.listdir(bird_folder_path)) > 1:
        # Add the current folder name to the set of unique classes
        unique_classes.add(bird_folder)

        image_paths = [os.path.join(bird_folder_path, img) for img in os.listdir(bird_folder_path)]
        images = load_and_preprocess_images(image_paths)
        all_images.extend(images)

all_images = np.array(all_images)

# Calculate the total number of classes
num_classes = len(unique_classes)
print("Number of classes:", num_classes)
```

<div class="output stream stdout">

    Number of classes: 110

</div>

</div>

<div class="cell code" execution_count="4"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:3,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594342117,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="QcOLzGuAf6Aw" outputId="eaf19a2f-0172-419e-a8d1-5b3a3de3a625">

``` python
# Load and preprocess labels
all_labels = []
for bird_folder in os.listdir(data_dir):
    bird_folder_path = os.path.join(data_dir, bird_folder)
    if os.path.isdir(bird_folder_path) and len(os.listdir(bird_folder_path)) > 1:
        label = bird_folder  # Assuming folder name is the label
        labels = [label] * len(os.listdir(bird_folder_path))
        all_labels.extend(labels)

# Convert labels to numerical format (e.g., one-hot encoding)
from sklearn.preprocessing import LabelEncoder, OneHotEncoder

label_encoder = LabelEncoder()
integer_encoded = label_encoder.fit_transform(all_labels)
onehot_encoder = OneHotEncoder(sparse=False)
encoded_labels = onehot_encoder.fit_transform(integer_encoded.reshape(-1, 1))
```

<div class="output stream stderr">

    /usr/local/lib/python3.10/dist-packages/sklearn/preprocessing/_encoders.py:868: FutureWarning: `sparse` was renamed to `sparse_output` in version 1.2 and will be removed in 1.4. `sparse_output` is ignored unless you leave `sparse` to its default value.
      warnings.warn(

</div>

</div>

<div class="cell code" execution_count="5"
executionInfo="{&quot;elapsed&quot;:1172,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594343287,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="nLFZ8OL2Y4nK">

``` python
from sklearn.model_selection import train_test_split

# Split data into training and temporary set (which includes validation and test data)
train_images, temp_images, train_labels, temp_labels = train_test_split(all_images, encoded_labels, test_size=0.2, random_state=42)

# Split temporary set into validation and test sets
val_images, test_images, val_labels, test_labels = train_test_split(temp_images, temp_labels, test_size=0.5, random_state=42)
```

</div>

<div class="cell code" execution_count="6"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:3,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594343288,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="QWtGgvJSY58c" outputId="d39aa12b-13bb-4f65-8495-15f6b0cd686f">

``` python
print("Train images shape:", train_images.shape)
print("Validation images shape:", val_images.shape)
print("Test images shape:", test_images.shape)
```

<div class="output stream stdout">

    Train images shape: (1725, 224, 224, 3)
    Validation images shape: (216, 224, 224, 3)
    Test images shape: (216, 224, 224, 3)

</div>

</div>

<div class="cell markdown" id="1d-toRWpdoPg">

# Neural Network

</div>

<div class="cell code" execution_count="7"
executionInfo="{&quot;elapsed&quot;:3458,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594346745,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="Obdl6bRidqy7">

``` python
start_time = time.time()

# Define your CNN model with Conv2D and Dropout layers
model = models.Sequential([
    layers.Conv2D(32, (3, 3), activation='relu', input_shape=(224, 224, 3)),
    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(64, (3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(128, (3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),

    layers.Conv2D(256, (3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),

    layers.Flatten(),

    # Add dropout layers
    layers.Dropout(0.5),  # Add dropout after flattening
    layers.Dense(128, activation='relu'),

    layers.Dropout(0.5),  # Add dropout after the first dense layer
    layers.Dense(num_classes, activation='softmax')  # num_classes is the number of bird species
])

# Compile the model
model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
```

</div>

<div class="cell code" execution_count="8"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:6,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594346745,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="aExSOdFWi9Ma" outputId="3f204c06-5123-46ef-e470-62247830ecf5">

``` python
# Print the model summary
model.summary()
```

<div class="output stream stdout">

    Model: "sequential"
    _________________________________________________________________
     Layer (type)                Output Shape              Param #   
    =================================================================
     conv2d (Conv2D)             (None, 222, 222, 32)      896       
                                                                     
     max_pooling2d (MaxPooling2D  (None, 111, 111, 32)     0         
     )                                                               
                                                                     
     conv2d_1 (Conv2D)           (None, 109, 109, 64)      18496     
                                                                     
     max_pooling2d_1 (MaxPooling  (None, 54, 54, 64)       0         
     2D)                                                             
                                                                     
     conv2d_2 (Conv2D)           (None, 52, 52, 128)       73856     
                                                                     
     max_pooling2d_2 (MaxPooling  (None, 26, 26, 128)      0         
     2D)                                                             
                                                                     
     conv2d_3 (Conv2D)           (None, 24, 24, 256)       295168    
                                                                     
     max_pooling2d_3 (MaxPooling  (None, 12, 12, 256)      0         
     2D)                                                             
                                                                     
     flatten (Flatten)           (None, 36864)             0         
                                                                     
     dropout (Dropout)           (None, 36864)             0         
                                                                     
     dense (Dense)               (None, 128)               4718720   
                                                                     
     dropout_1 (Dropout)         (None, 128)               0         
                                                                     
     dense_1 (Dense)             (None, 110)               14190     
                                                                     
    =================================================================
    Total params: 5,121,326
    Trainable params: 5,121,326
    Non-trainable params: 0
    _________________________________________________________________

</div>

</div>

<div class="cell code" execution_count="9"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:86701,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594433444,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="ghQc7tnPi_Xt" outputId="81a9a168-c9c9-4685-a0e6-a87327b81863">

``` python
# Train the model
history = model.fit(train_images, train_labels, epochs=200, batch_size=64,
                    validation_data=(val_images, val_labels),callbacks=[
                     tf.keras.callbacks.ModelCheckpoint("CNN_model.h5",save_best_only=True,save_weights_only=False)
                     ,tf.keras.callbacks.EarlyStopping(monitor='val_accuracy', patience=3),
                    ])

# Evaluate the model
test_loss, test_acc = model.evaluate(test_images, test_labels)
print('Test accuracy:', test_acc)
```

<div class="output stream stdout">

    Epoch 1/200
    27/27 [==============================] - 18s 156ms/step - loss: 4.6913 - accuracy: 0.0145 - val_loss: 4.6487 - val_accuracy: 0.0324
    Epoch 2/200
    27/27 [==============================] - 2s 62ms/step - loss: 4.6177 - accuracy: 0.0133 - val_loss: 4.5444 - val_accuracy: 0.0139
    Epoch 3/200
    27/27 [==============================] - 4s 151ms/step - loss: 4.4737 - accuracy: 0.0325 - val_loss: 4.3045 - val_accuracy: 0.0602
    Epoch 4/200
    27/27 [==============================] - 2s 70ms/step - loss: 4.1528 - accuracy: 0.0928 - val_loss: 3.8162 - val_accuracy: 0.2083
    Epoch 5/200
    27/27 [==============================] - 3s 118ms/step - loss: 3.6801 - accuracy: 0.1872 - val_loss: 3.4227 - val_accuracy: 0.2963
    Epoch 6/200
    27/27 [==============================] - 2s 76ms/step - loss: 3.1922 - accuracy: 0.2812 - val_loss: 2.9093 - val_accuracy: 0.3981
    Epoch 7/200
    27/27 [==============================] - 3s 110ms/step - loss: 2.7910 - accuracy: 0.3530 - val_loss: 2.6384 - val_accuracy: 0.4537
    Epoch 8/200
    27/27 [==============================] - 2s 58ms/step - loss: 2.3449 - accuracy: 0.4325 - val_loss: 2.3750 - val_accuracy: 0.4954
    Epoch 9/200
    27/27 [==============================] - 3s 131ms/step - loss: 2.0595 - accuracy: 0.4788 - val_loss: 2.1277 - val_accuracy: 0.5463
    Epoch 10/200
    27/27 [==============================] - 3s 106ms/step - loss: 1.7927 - accuracy: 0.5554 - val_loss: 1.9615 - val_accuracy: 0.5787
    Epoch 11/200
    27/27 [==============================] - 2s 86ms/step - loss: 1.5668 - accuracy: 0.5907 - val_loss: 1.9259 - val_accuracy: 0.5926
    Epoch 12/200
    27/27 [==============================] - 5s 183ms/step - loss: 1.3992 - accuracy: 0.6191 - val_loss: 1.8649 - val_accuracy: 0.6389
    Epoch 13/200
    27/27 [==============================] - 2s 56ms/step - loss: 1.3032 - accuracy: 0.6423 - val_loss: 1.8240 - val_accuracy: 0.6435
    Epoch 14/200
    27/27 [==============================] - 4s 134ms/step - loss: 1.2389 - accuracy: 0.6568 - val_loss: 1.7752 - val_accuracy: 0.6620
    Epoch 15/200
    27/27 [==============================] - 1s 50ms/step - loss: 1.0937 - accuracy: 0.6957 - val_loss: 1.8544 - val_accuracy: 0.6713
    Epoch 16/200
    27/27 [==============================] - 1s 50ms/step - loss: 1.0016 - accuracy: 0.7148 - val_loss: 1.8646 - val_accuracy: 0.6481
    Epoch 17/200
    27/27 [==============================] - 2s 68ms/step - loss: 0.9882 - accuracy: 0.7217 - val_loss: 1.8107 - val_accuracy: 0.6574
    Epoch 18/200
    27/27 [==============================] - 2s 74ms/step - loss: 0.8902 - accuracy: 0.7501 - val_loss: 1.8481 - val_accuracy: 0.6620
    7/7 [==============================] - 0s 22ms/step - loss: 2.1316 - accuracy: 0.6574
    Test accuracy: 0.6574074029922485

</div>

</div>

<div class="cell code" execution_count="10"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
executionInfo="{&quot;elapsed&quot;:297,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594433740,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="bkiBQKo336Pe" outputId="2ad97837-b3fa-409a-dd96-ad9daaff0c37">

``` python
end_time = time.time()
runtime = end_time - start_time
print('Total runtime:', runtime, 'seconds')
```

<div class="output stream stdout">

    Total runtime: 90.39768433570862 seconds

</div>

</div>

<div class="cell code" execution_count="11"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:472}"
executionInfo="{&quot;elapsed&quot;:402,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594434141,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="Bvwm5VwVp9TD" outputId="db723ccd-8aa8-46ce-d8ea-806c631f4c2d">

``` python
# Plot training and validation accuracy
plt.plot(history.history['accuracy'], label='Train Accuracy')
plt.plot(history.history['val_accuracy'], label='Validation Accuracy')
plt.xlabel('Epochs')
plt.ylabel('Accuracy')
plt.title('Training and Validation Accuracy')
plt.legend()
plt.show()
```

<div class="output display_data">

![](9005ea7d1b273e697ebe6bac98bbc900e97c8949.png)

</div>

</div>

<div class="cell code" execution_count="12"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:472}"
executionInfo="{&quot;elapsed&quot;:298,&quot;status&quot;:&quot;ok&quot;,&quot;timestamp&quot;:1692594434437,&quot;user&quot;:{&quot;displayName&quot;:&quot;Kevin Tong&quot;,&quot;userId&quot;:&quot;02567103695429705615&quot;},&quot;user_tz&quot;:420}"
id="LnoPC7t7sJ0C" outputId="70008507-36b0-49f5-bb42-de68d02cfc75">

``` python
# Plot test accuracy
plt.plot(history.history['accuracy'], label='Train Accuracy')
plt.plot(len(history.history['val_accuracy']), test_acc, 'ro', label='Test Accuracy')
plt.xlabel('Epochs')
plt.ylabel('Accuracy')
plt.title('Test Accuracy')
plt.legend()
plt.show()
```

<div class="output display_data">

![](aae8f6eae583a5847587e370c4b68e7085baefd2.png)

</div>

</div>
