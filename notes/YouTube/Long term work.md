- [ ] need to study for the iot
- [ ] need to start the project

Here's a full implementation of the lab assignment, where you will implement a CNN on the Intel Image Classification dataset, visualize samples, design the CNN architecture, train and evaluate the model, and optimize its performance using data augmentation.

### Step 1: Import Libraries and Load Dataset

```python
import numpy as np
import matplotlib.pyplot as plt
import tensorflow as tf
from tensorflow.keras.preprocessing.image import ImageDataGenerator
from tensorflow.keras import layers, models
from sklearn.metrics import confusion_matrix, classification_report
import seaborn as sns
import os

# Download dataset from https://www.kaggle.com/datasets/puneet6060/intel-image-classification and extract it

train_dir = 'Intel_Image_Classification/seg_train/seg_train'
test_dir = 'Intel_Image_Classification/seg_test/seg_test'
```

### Step 2: Visualizing Dataset Samples

```python
# Define a function to display sample images
def visualize_samples(data_dir, categories, n_samples=5):
    plt.figure(figsize=(12, 8))
    for i, category in enumerate(categories):
        folder_path = os.path.join(data_dir, category)
        for j, img_name in enumerate(os.listdir(folder_path)[:n_samples]):
            img_path = os.path.join(folder_path, img_name)
            img = plt.imread(img_path)
            plt.subplot(len(categories), n_samples, i * n_samples + j + 1)
            plt.imshow(img)
            plt.title(category)
            plt.axis('off')
    plt.tight_layout()
    plt.show()

categories = ['buildings', 'forest', 'glacier', 'mountain', 'sea', 'street']
visualize_samples(train_dir, categories)
```

### Step 3: CNN Model Architecture

```python
# Image augmentation and data preparation
train_datagen = ImageDataGenerator(
    rescale=1./255,
    rotation_range=20,
    width_shift_range=0.2,
    height_shift_range=0.2,
    shear_range=0.2,
    zoom_range=0.2,
    horizontal_flip=True,
    fill_mode='nearest',
    validation_split=0.2  # Use 20% of training data for validation
)

test_datagen = ImageDataGenerator(rescale=1./255)

train_generator = train_datagen.flow_from_directory(
    train_dir,
    target_size=(150, 150),
    batch_size=32,
    class_mode='categorical',
    subset='training'
)

validation_generator = train_datagen.flow_from_directory(
    train_dir,
    target_size=(150, 150),
    batch_size=32,
    class_mode='categorical',
    subset='validation'
)

test_generator = test_datagen.flow_from_directory(
    test_dir,
    target_size=(150, 150),
    batch_size=32,
    class_mode='categorical'
)

# CNN Model Architecture
model = models.Sequential([
    layers.Conv2D(32, (3, 3), activation='relu', input_shape=(150, 150, 3)),
    layers.BatchNormalization(),
    layers.MaxPooling2D((2, 2)),
    
    layers.Conv2D(64, (3, 3), activation='relu'),
    layers.BatchNormalization(),
    layers.MaxPooling2D((2, 2)),
    
    layers.Conv2D(128, (3, 3), activation='relu'),
    layers.BatchNormalization(),
    layers.MaxPooling2D((2, 2)),
    
    layers.Flatten(),
    layers.Dense(128, activation='relu'),
    layers.Dropout(0.5),
    layers.Dense(6, activation='softmax')  # 6 classes
])

# Compile the model
model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])

model.summary()
```

### Step 4: Model Training

```python
# Train the model
history = model.fit(
    train_generator,
    steps_per_epoch=train_generator.samples // 32,
    validation_data=validation_generator,
    validation_steps=validation_generator.samples // 32,
    epochs=20  # Train for 20 epochs
)
```

### Step 5: Evaluation

```python
# Evaluate the model on test data
test_loss, test_acc = model.evaluate(test_generator)
print(f"Test Accuracy: {test_acc * 100:.2f}%")

# Plotting training and validation accuracy/loss
def plot_performance(history):
    acc = history.history['accuracy']
    val_acc = history.history['val_accuracy']
    loss = history.history['loss']
    val_loss = history.history['val_loss']
    
    epochs = range(1, len(acc) + 1)
    
    plt.figure(figsize=(12, 5))
    
    # Accuracy plot
    plt.subplot(1, 2, 1)
    plt.plot(epochs, acc, 'bo-', label='Training Accuracy')
    plt.plot(epochs, val_acc, 'ro-', label='Validation Accuracy')
    plt.title('Training and Validation Accuracy')
    plt.legend()
    
    # Loss plot
    plt.subplot(1, 2, 2)
    plt.plot(epochs, loss, 'bo-', label='Training Loss')
    plt.plot(epochs, val_loss, 'ro-', label='Validation Loss')
    plt.title('Training and Validation Loss')
    plt.legend()
    
    plt.tight_layout()
    plt.show()

plot_performance(history)
```

### Confusion Matrix and Classification Report

```python
# Generate predictions
predictions = model.predict(test_generator)
y_pred = np.argmax(predictions, axis=1)
y_true = test_generator.classes

# Confusion Matrix
cm = confusion_matrix(y_true, y_pred)
plt.figure(figsize=(8, 6))
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues', xticklabels=categories, yticklabels=categories)
plt.xlabel('Predicted')
plt.ylabel('True')
plt.show()

# Classification report
print(classification_report(y_true, y_pred, target_names=categories))
```

### Step 6: Optimization (Data Augmentation)

```python
# Data Augmentation strategies have already been implemented during the data preparation phase
# Experiment with changing augmentation parameters or fine-tuning learning rate

# Example: Changing learning rate
from tensorflow.keras.optimizers import Adam
new_optimizer = Adam(learning_rate=0.0001)  # Reduced learning rate

# Recompile model with new optimizer
model.compile(optimizer=new_optimizer, loss='categorical_crossentropy', metrics=['accuracy'])

# Retrain the model
history_fine_tune = model.fit(
    train_generator,
    steps_per_epoch=train_generator.samples // 32,
    validation_data=validation_generator,
    validation_steps=validation_generator.samples // 32,
    epochs=10  # Fine-tune for 10 more epochs
)

plot_performance(history_fine_tune)
```

### Conclusion

1. We visualized some samples from the dataset and explored their corresponding labels.
2. Designed and trained a CNN with 3 convolution layers and used techniques like batch normalization and dropout to improve generalization.
3. We evaluated the model using accuracy, confusion matrix, and classification report.
4. We optimized the model using data augmentation and fine-tuned the learning rate to improve performance.