# 🎵 FakeAVCeleb - Advanced Audio Classification System

## Overview
FakeAVCeleb is an advanced audio classification system that combines UrbanSound8K environmental sounds with AI-generated speech samples. It uses deep learning with librosa feature extraction to classify audio files and detect human voices.

## 📁 Project Structure
```
TrainANDtest/
├── app.py                          # Root-level entry point
├── quickstart.py                   # Quick start verification script
├── README.md                       # This file
└── FakeAVCeleb/
    ├── app.py                      # Flask web application
    ├── advanced_audio_classifier.py # Advanced ML model
    ├── audio_classifier_model.py   # Basic classifier
    ├── build_combined_dataset.py   # Dataset builder
    ├── quick_audio_integration.py  # Audio integration script
    ├── models/
    │   ├── advanced_audio_classifier.pkl
    │   ├── advanced_label_encoder.pkl
    │   ├── feature_scaler.pkl
    │   ├── audio_classifier.pkl
    │   └── label_encoder.pkl
    └── dataset/
        ├── combined_audio_dataset.csv
        ├── unified_audio_dataset_with_transcriptions.csv
        ├── UrbanSound8K.csv
        ├── unified_audio_dataset.csv
        └── AI AUDIO/
            ├── FlashSpeech/
            ├── NaturalSpeech3/
            ├── OpenAI/
            ├── PromptTTS2/
            ├── real_samples/
            ├── seedtts_files/
            ├── VALLE/
            ├── VoiceBox/
            └── xTTS/
```

## 🚀 Quick Start



## 📊 Dataset Information

### Combined Dataset (13,179 samples)
- **UrbanSound8K**: 8,732 environmental sound samples
- **AI Audio**: 4,447 generated speech samples

### Audio Classes (20+)
#### Environmental Sounds
1. Air Conditioner
2. Car Horn
3. Children Playing
4. Dog Bark
5. Drilling
6. Engine Idling
7. Gun Shot
8. Jackhammer
9. Siren
10. Street Music

#### AI-Generated Speech
1. AI Speech - FlashSpeech
2. AI Speech - NaturalSpeech3
3. AI Speech - OpenAI
4. AI Speech - PromptTTS2
5. AI Speech - Real Samples
6. AI Speech - SeedTTS
7. AI Speech - VALLE
8. AI Speech - VoiceBox
9. AI Speech - xTTS

## 🤖 Model Details

### Architecture
- **Type**: Gradient Boosting Classifier
- **Framework**: scikit-learn with Pipeline
- **Feature Dimension**: 96

### Feature Extraction (using Librosa)
- **MFCC**: 13 coefficients with statistics (mean, std, max, min)
- **Spectral Features**: Centroid, Rolloff, Bandwidth
- **Temporal Features**: Zero Crossing Rate, Tempogram
- **Energy**: RMS Energy statistics
- **Chroma**: Chroma STFT features

### Input Formats
- WAV (✓)
- MP3 (✓)
- OGG (✓)
- FLAC (✓)

## 🎯 Key Features

### 1. Audio Classification
- Upload audio files and get instant classifications
- Confidence scores for predictions
- Support for 20+ audio classes

### 2. Human Voice Detection
- Automatically detects AI-generated speech vs environmental sounds
- Classifies audio source (AI Generated / Environmental)
- Human voice indicator in results

### 3. Dataset Management
- Combined dataset with both environmental and AI-generated audio
- Comprehensive metadata and statistics
- Easy-to-use dashboard with visualizations

### 4. Advanced Feature Extraction
- Librosa-based audio processing
- 96-dimensional feature vectors
- Multiple domain features (temporal, spectral, energy, harmonic)

## 📈 Application Interface

### Dashboard Sections
1. **Dataset Statistics**: Total samples, classes, unique files, training folds
2. **Audio Classes**: Distribution of samples across all classes
3. **Class Distribution Chart**: Visual representation of class balance
4. **Sample Audio Files**: Browse dataset samples with metadata
5. **Audio Classification Tool**: Upload and classify audio files

## 🔧 Configuration

### Environment Variables
- `PORT`: Server port (default: 5000)
- `UPLOAD_FOLDER`: Upload directory (default: 'uploads')
- `ALLOWED_EXTENSIONS`: Supported file formats (wav, mp3, ogg, flac)

### Model Files
All trained models are stored in `FakeAVCeleb/models/`:
- `advanced_audio_classifier.pkl`: Main classifier
- `advanced_label_encoder.pkl`: Class label encoder
- `feature_scaler.pkl`: Feature scaling transformer

### Dataset Files
All datasets are stored in `FakeAVCeleb/dataset/`:
- `combined_audio_dataset.csv`: Main dataset with all samples
- `UrbanSound8K.csv`: Original environmental sounds
- `AI AUDIO/`: Folder containing AI-generated speech samples

## 📝 API Endpoints

### GET /
Main dashboard page with statistics and file upload interface

### POST /classify
Classify an uploaded audio file
- **Request**: Multipart form with audio file
- **Response**: JSON with class, confidence, and metadata

### GET /api/stats
Get dataset statistics
- **Response**: JSON with dataset metadata and class distribution

## 🛠️ Building Models and Dataset

### Build Combined Dataset
```bash
cd FakeAVCeleb
python build_combined_dataset.py
```

### Build Advanced Model
```bash
cd FakeAVCeleb
python advanced_audio_classifier.py
```

### Quick Audio Integration
```bash
cd FakeAVCeleb
python quick_audio_integration.py
```

## 📦 Dependencies
- Flask
- pandas
- numpy
- scikit-learn
- librosa
- joblib
- werkzeug

## 🐛 Troubleshooting

### Issue: "No module named 'advanced_audio_classifier'"
**Solution**: Make sure you're running from the FakeAVCeleb directory or the root TrainANDtest directory with the app.py file

### Issue: "Combined dataset not found"
**Solution**: Run `python build_combined_dataset.py` in FakeAVCeleb directory

### Issue: "Model files not found"
**Solution**: Run `python advanced_audio_classifier.py` in FakeAVCeleb directory

### Issue: Audio upload fails
**Solution**: Ensure file is in supported format (wav, mp3, ogg, flac) and less than 100MB

## 📊 Example Usage

1. **Start the server**:
   ```bash
   python app.py
   ```

2. **Open browser**: http://localhost:5000

3. **Upload audio file**:
   - Click the upload area or drag-and-drop an audio file
   - Select a WAV, MP3, OGG, or FLAC file

4. **View results**:
   - Predicted class name
   - Confidence percentage
   - Audio type (AI Generated / Environmental)
   - Human voice detection status

## 📄 License
© 2026 FakeAVCeleb Project

## 👤 Author
AI Audio Classification System

## 📞 Support
For issues or questions, check the troubleshooting section above or review the code documentation.

---

**Last Updated**: March 14, 2026
**Version**: 2.0 (with AI Audio Support)
