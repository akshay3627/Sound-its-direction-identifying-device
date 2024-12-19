# Sound Direction and Object Identification

This project implements a sound localization and classification system using Python, TensorFlow, and additional libraries. The system captures audio signals from two microphones, identifies the sound source's direction, classifies the sound type, and provides the output using a text-to-speech engine.

## Features

- **Real-time Sound Classification**: Identifies the type of sound from pre-defined categories.
- **Sound Localization**: Calculates the angle and direction of the sound source using microphone signals.
- **Text-to-Speech Feedback**: Provides verbal feedback of the identified sound and its direction.
- **Pre-trained Model Support**: Uses a pre-trained TensorFlow model for sound classification.

## Requirements

- Python 3.x
- TensorFlow
- NumPy
- SoundDevice
- Pyttsx3
- SciPy

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/sound-direction-identification.git
   cd sound-direction-identification
   ```

2. Install the required dependencies:

   ```bash
   pip install tensorflow numpy sounddevice pyttsx3 scipy
   ```

3. Place your pre-trained model (`sound_identification_model.h5`) in the project directory or update the script with the correct model path.

## Usage

1. Ensure that two microphones are connected and configured correctly on your system.
2. Run the script:

   ```bash
   python sound_direction_identification.py
   ```

3. The program will capture audio from the microphones, classify the sound, determine its direction, and provide spoken feedback.

## How It Works

1. **Audio Capture**:
   - Records audio from two microphones sequentially.
2. **Sound Classification**:
   - Splits the combined audio into segments.
   - Extracts features and uses a pre-trained model to classify the sound into one of the following categories:
     - Air Conditioner
     - Car Horn
     - Children Playing
     - Dog Bark
     - Drilling
     - Engine Idling
     - Gun Shot
     - Jackhammer
     - Siren
     - Street Music
3. **Sound Localization**:
   - Calculates the time delay of arrival (TDOA) between the microphones using cross-correlation.
   - Determines the angle of arrival and infers the direction (Left, Right, Forward, Backward).
4. **Feedback**:
   - Speaks the detected sound type and direction using a text-to-speech engine.

## File Structure

- `sound_direction_identification.py`: Main Python script for sound localization and classification.
- `README.md`: Project documentation.
- `sound_identification_model.h5`: Pre-trained TensorFlow model (not included, add your own).

## Customization

- **Sound Labels**: Update the `LABELS` list with your desired sound classes.
- **Microphone Configuration**: Adjust the `MIC_DISTANCE` and `MIC_OFFSET` constants for your microphone setup.
- **Model Path**: Update the model path in the script:
  ```python
  model = load_model('path_to_your_model.h5')
  ```

## Contribution

Feel free to submit issues and pull requests to improve the functionality of this project.

## License

This project is licensed under the [MIT License](LICENSE).

