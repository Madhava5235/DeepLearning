
# Voice Morphing Detection using Custom CNN and Streamlit Interface

This project implements a custom CNN model to detect morphed voices from audio files. The model is trained on mel spectrograms extracted from audio files, and a **Streamlit** interface is provided for real-time predictions. The app also supports deployment via **ngrok** for sharing the application over the internet.

---

## Features

- **Custom CNN Model**: Designed for binary classification (Real vs. Morphed).
- **Audio Preprocessing**: Converts audio files into mel spectrograms for visual representation.
- **Streamlit Web Interface**: User-friendly interface for uploading WAV files and displaying results.
- **Deployment with ngrok**: Easily share the app online using ngrok.

---

## Prerequisites

### Libraries and Tools

- Python 3.7+
- TensorFlow 2.x
- Keras
- Librosa
- Streamlit
- Matplotlib
- Pyngrok

You can install all dependencies using:

```bash
pip install -r requirements.txt
```

---

## Dataset Preparation

1. **Audio Files**: Collect audio files labeled as either `real` or `morphed`.
2. **Spectrogram Generation**: Convert audio files into mel spectrogram images using the script:
   ```bash
   python generate_spectrograms.py
   ```
3. **Directory Structure**:
   ```
   /content/spectrograms/
       ├── train/
       │   ├── real/
       │   ├── morphed/
       └── validation/
           ├── real/
           ├── morphed/
   ```

---

## Model Training

1. Modify the dataset path in `train_model.py`.
2. Train the model using the provided script:
   ```bash
   python train_model.py
   ```
3. The trained model will be saved as `my_model.hdf5`.

---

## Running the Streamlit Application

### Steps to Run Locally

1. Launch the Streamlit app:
   ```bash
   streamlit run app.py
   ```
2. Open the provided local URL (e.g., `http://localhost:8501`) in your browser.

### Deploying with ngrok

1. Install pyngrok:
   ```bash
   pip install pyngrok
   ```
2. Run the app with ngrok:
   ```bash
   ngrok http 8501
   ```
3. Use the public ngrok URL to share your app.

---

## Project Structure

```
.
├── README.md                # Project documentation
├── requirements.txt         # Python dependencies
├── train_model.py           # Model training script
├── app.py                   # Streamlit web application
├── generate_spectrograms.py # Spectrogram generation script
├── spectrogram_images/      # Directory for spectrogram images
├── my_model.hdf5            # Trained model
```

---

## Usage

1. **Upload WAV Files**: Use the Streamlit app to upload an audio file.
2. **View Spectrogram**: The app will display the mel spectrogram of the uploaded audio.
3. **Prediction**: The model will classify the audio as "Real" or "Morphed" and display the confidence score.

---

## Results

- The model achieves an accuracy of `XX%` on the validation dataset.
- Predictions are displayed in real-time on the Streamlit interface.

---

## Future Improvements

- Enhance model performance with additional layers and hyperparameter tuning.
- Add multi-class support for different morphing techniques.
- Incorporate deployment to cloud platforms (e.g., AWS, Google Cloud).

---

