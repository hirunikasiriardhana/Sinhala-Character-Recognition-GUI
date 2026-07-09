# Sinhala-Character-Recognition-GUI
Sinhala Character Recognition GUI using Tkinter and KNN. Users draw Sinhala letters (`අ`, `එ`, `ඉ`, `උ`) on a canvas. Input is saved with Pillow and OpenCV, processed via NumPy, and classified using a trained KNN model. GUI provides Save, Predict, Clear, Exit buttons with real‑time feedback and character display.

<img width="467" height="551" alt="image" src="https://github.com/user-attachments/assets/1d50f365-829e-4b49-a81e-585cab613649" />

1. Dataset Preparation 
- Collect handwritten samples of Sinhala characters
  
  <img width="53" height="79" alt="1" src="https://github.com/user-attachments/assets/0a7d2ddf-f6fa-48d9-b411-23689f29259b" />
  <img width="47" height="109" alt="42" src="https://github.com/user-attachments/assets/e5ef94dd-646f-41b2-9e6a-0382b8373e66" />
  <img width="69" height="109" alt="1" src="https://github.com/user-attachments/assets/fbcd1a6f-fd73-4003-8f6f-a90d809ff8b2" />
  <img width="49" height="113" alt="1" src="https://github.com/user-attachments/assets/0387200d-02b9-48fb-ac98-fa6854d6e115" />

- Each image is converted to grayscale, resized to 8×8 pixels, and flattened into a 1×64 feature vector for training.
- <img width="417" height="418" alt="image" src="https://github.com/user-attachments/assets/f72b7f8f-c07f-4e88-a936-0596668c5ba2" />


2. Model Training (KNN) 
- Use `scikit-learn`s `KNeighborsClassifier`. 
- Train the model with labeled data 
- Save the trained model (e.g., `KNN_model.sav`).

3. GUI Development (Tkinter) 
- Create a canvas for drawing characters. 
- Add buttons: 
- Save → stores the drawn image. 
- Predict → loads the model and predicts the character. 
- Clear → resets the canvas. 
- Exit → closes the application. 
- Display prediction results in a status label.
<img width="577" height="663" alt="image" src="https://github.com/user-attachments/assets/be394070-51c6-402f-bff7-17072aba751f" />


4. Image Handling 
- Use Pillow (PIL) to capture canvas drawings. 
- Convert to NumPy arrays for preprocessing. 
- Save images with OpenCV (cv2).


5. Prediction Integration 
- Load the saved KNN model. 
- Preprocess the drawn image (grayscale, resize, flatten). 
- Pass the vector to the model for classification. 
- Show the predicted Sinhala character in real time.
<img width="551" height="663" alt="image" src="https://github.com/user-attachments/assets/55e39bae-c457-4bac-98d8-6083b2cd9c9b" />
<img width="548" height="663" alt="image" src="https://github.com/user-attachments/assets/069f87be-698b-42bb-beb4-20694cac4e0b" />
<img width="543" height="661" alt="image" src="https://github.com/user-attachments/assets/9e479cb6-8381-4aa1-8d5d-e756c5a69641" />
<img width="540" height="663" alt="image" src="https://github.com/user-attachments/assets/ad3cae82-6ddb-4791-9ee7-de67f520ddc1" />


6. Testing & Validation 
- Test with multiple handwritten samples. 
- Evaluate accuracy and adjust KNN parameters (e.g., `n_neighbors`).
- KNN model accuracy is 81%, meaning 19% misclassifications. This happens due to non‑optimal k, unscaled features, noise, or imbalanced data. Improve results by scaling features, tuning k with cross‑validation, trying different distance metrics, and applying dimensionality reduction or balancing techniques for better generalization.

<img width="545" height="658" alt="image" src="https://github.com/user-attachments/assets/58bd322f-37c8-4ed8-b54c-48b2f069c6ca" />


7. Future Improvements 
- Extend recognition to more Sinhala characters. 
- Add dataset augmentation for robustness. 
- Enhance GUI with live prediction while drawing.
