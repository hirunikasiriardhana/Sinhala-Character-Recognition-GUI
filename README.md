# Sinhala-Character-Recognition-GUI
Sinhala Character Recognition GUI using Tkinter and KNN. Users draw Sinhala letters (`අ`, `එ`, `ඉ`, `උ`) on a canvas. Input is saved with Pillow and OpenCV, processed via NumPy, and classified using a trained KNN model. GUI provides Save, Predict, Clear, Exit buttons with real‑time feedback and character display.

<img width="167" height="251" alt="image" src="https://github.com/user-attachments/assets/1d50f365-829e-4b49-a81e-585cab613649" />




1. Dataset Preparation 
- Collect handwritten samples of Sinhala characters
  
  <img width="53" height="79" alt="1" src="https://github.com/user-attachments/assets/0a7d2ddf-f6fa-48d9-b411-23689f29259b" />
  <img width="47" height="109" alt="42" src="https://github.com/user-attachments/assets/e5ef94dd-646f-41b2-9e6a-0382b8373e66" />
  <img width="69" height="109" alt="1" src="https://github.com/user-attachments/assets/fbcd1a6f-fd73-4003-8f6f-a90d809ff8b2" />
  <img width="49" height="113" alt="1" src="https://github.com/user-attachments/assets/0387200d-02b9-48fb-ac98-fa6854d6e115" />

- Each image is converted to grayscale, resized to 8×8 pixels, and flattened into a 1×64 feature vector for training.
- <img width="117" height="118" alt="image" src="https://github.com/user-attachments/assets/f72b7f8f-c07f-4e88-a936-0596668c5ba2" />


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
- Display prediction results in a **status label**.

4. Image Handling 
- Use Pillow (PIL) to capture canvas drawings. 
- Convert to NumPy arrays for preprocessing. 
- Save images with OpenCV (cv2).

5. Prediction Integration 
- Load the saved KNN model. 
- Preprocess the drawn image (grayscale, resize, flatten). 
- Pass the vector to the model for classification. 
- Show the predicted Sinhala character in real time.

6. Testing & Validation 
- Test with multiple handwritten samples. 
- Evaluate accuracy and adjust KNN parameters (e.g., `n_neighbors`).

7. Future Improvements 
- Extend recognition to more Sinhala characters. 
- Add dataset augmentation for robustness. 
- Enhance GUI with live prediction while drawing.
