# Candidate Interview Audio Analysis

## Overview
This project extracts and analyzes audio from candidate interview videos to evaluate communication skills through transcription and sentiment analysis.

## Table of Contents
- [Candidate Interview Audio Analysis](#candidate-interview-audio-analysis)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Additional Notes for Installation](#additional-notes-for-installation)
      - [FFmpeg Installation](#ffmpeg-installation)
  - [Usage](#usage)
  - [Features](#features)
  - [How It Works](#how-it-works)
  - [Contributing](#contributing)

## Installation
To run this project, you need to have Python and the required libraries installed. You can install the necessary libraries using the provided `requirements.txt` file.

1. Make sure you have Python installed on your machine.
2. Create a virtual environment (optional but recommended)
3. Install the required libraries using pip:

```bash
pip install -r requirements.txt
```
### Additional Notes for Installation

#### FFmpeg Installation
`pydub` and `moviepy` require **FFmpeg** for audio and video processing. Follow the instructions below to install FFmpeg based on your operating system:

- **macOS**: Install FFmpeg via Homebrew:
  ```
  brew install ffmpeg
  ```

- **Windows**: Download and install FFmpeg from [FFmpeg's official website](https://ffmpeg.org/download.html). 
  - After downloading, add FFmpeg to your system’s PATH for easy access.

- **Linux**: Use the following commands based on your Linux distribution:
  - **Debian-based (Ubuntu, etc.)**:
    ```
    sudo apt install ffmpeg
    ```
  - **Red Hat-based (CentOS, Fedora, etc.)**:
    ```
    sudo yum install ffmpeg
    ```

Make sure FFmpeg is correctly installed and accessible from the command line to avoid issues with audio and video processing.


## Usage
1. Place your video file (e.g., `candidate_interview.mp4`) in the `data` folder.
2. Run the Jupyter Notebook to execute the code for audio extraction, preprocessing, feature extraction, and sentiment analysis:
   - **Step 1**: Import the required libraries.
   - **Step 2**: Extract audio from the video file using the provided function.
   - **Step 3**: Split the extracted audio into manageable chunks (5 minutes or less).
   - **Step 4**: Transcribe each audio chunk into text.
   - **Step 5**: Analyze the sentiment of the transcribed text and categorize it as positive, neutral, or negative.
3. Review the results of the audio analysis and sentiment evaluation in the output cells of the Jupyter Notebook.


## Features
- **Audio Extraction**: Extracts audio from video files in various formats, ensuring compatibility with different input sources.
- **Audio Splitting**: Automatically splits long audio files into manageable chunks of 5 minutes or less for easier transcription.
- **Speech Transcription**: Uses the Google Speech Recognition API to transcribe audio chunks into text accurately.
- **Sentiment Analysis**: Utilizes the TextBlob library to perform sentiment analysis on the transcribed text, categorizing the overall sentiment as:
  - **Positive**: Indicates a favorable or optimistic tone in the candidate's responses.
  - **Neutral**: Suggests an unbiased or indifferent tone in the candidate's responses.
  - **Negative**: Reflects an unfavorable or pessimistic tone in the candidate's responses.
- **Communication Skills Evaluation**: Provides insights into the candidate's communication skills based on audio features and sentiment analysis results.


## How It Works
1. **Audio Extraction**: The project uses `moviepy` to extract the audio track from the video file and save it as a .wav file. This ensures that the audio is in a suitable format for further processing.
2. **Audio Splitting**: The audio file is split into smaller chunks of 5 minutes or less using the `pydub` library. This is done to make transcription manageable and to avoid limitations imposed by the Google Speech Recognition API.
3. **Transcription**: Each audio chunk is transcribed into text using the `speech_recognition` library, specifically leveraging the Google Speech Recognition API. The transcriptions are collected and combined into a single text string for analysis.
4. **Sentiment Analysis**: The combined transcribed text is analyzed using the `TextBlob` library. The sentiment analysis categorizes the overall sentiment of the text into three classes:
   - **Positive**: Indicates that the tone of the responses is favorable or optimistic.
   - **Neutral**: Suggests that the tone of the responses is unbiased or indifferent.
   - **Negative**: Reflects that the tone of the responses is unfavorable or pessimistic.
5. **Communication Skills Evaluation**: The results of the audio analysis and sentiment evaluation provide insights into the candidate's communication skills, which can be used for further evaluation.

## Contributing
Contributions are welcome! Please feel free to open an issue or submit a pull request.


