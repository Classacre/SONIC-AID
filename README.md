<a target="_blank" href="https://colab.research.google.com/github/Classacre/SONIC-AID/blob/main/4_0_SonicAid.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# SonicAid v4.0

SonicAid is an advanced educational tool designed to assist in the transcription and processing of lecture content from various formats, including audio, video, and PDF files. With the capability to handle multiple languages, SonicAid aims to enhance the learning experience by providing accessible educational materials.

## Features

- **Multimedia Input Support**: SonicAid v4.0 supports audio, video, and, as of this version, PDF files.
- **Language Support**: Transcribe content in English, Japanese, Chinese, Korean, Hindi, and Indonesian.
- **Integration with AI Services**: Utilizes OpenAI and other machine learning technologies to process and transcribe content.

## Installation

Before using SonicAid, ensure you have Python installed on your system. SonicAid is tested with Python 3.10. Follow these steps to set up the project:

```bash
pip install -q pipx pytube openai langchain tiktoken PyMuPDF
apt-get install -qq python3.10-venv > /dev/null
pipx install insanely-fast-whisper
pipx ensurepath
```

## Usage

### Configuration

Set the desired language in the script to match the primary language of your educational content:

```python
language = "english" # Choose from: english, japanese, chinese, korean, indian (Hindi), indonesian
```

### Running SonicAid

SonicAid can be executed within a Jupyter environment or as a standalone Python script. For the latter, you can convert the `.ipynb` file to a `.py` script using Jupyter's export functionality.

### File Processing

To process files:

1. **Upload your files**: Audio, video, or PDFs.
2. **Run the script**: The script will automatically detect the file type and apply the appropriate processing method.

### YouTube and Web Links

SonicAid can also handle direct YouTube links or other web links to audio/video files:

```python
options = "Youtube" # Other options: File, Weblink, Google Drive
```

Input the link when prompted, and SonicAid will handle the downloading and processing.

#Flowchart
    Initialization: Setup environment, install necessary libraries, and ensure Python paths are configured correctly.
    Language Selection: The user selects the language for transcription.
    Input Selection: The user chooses the input type (YouTube, File, Weblink, or Google Drive).
    File Processing:
        For YouTube, the link is processed to download video, extract audio, and transcribe.
        For direct file uploads, depending on the file type (audio, video, PDF), the file is either directly transcribed or converted (PDF to images).
        For web links, the link is analyzed to determine if it's a video or audio, downloaded, and processed.
        For Google Drive, the path is checked, the file is accessed, and processed based on type.
    Transcription and Processing:
        Audio and video files are transcribed locally using the GPU - the google colab notebook leverages googles free GPU to run "insanely-fast-whisper".
        PDF files are converted to images and sent to the OpenAI gpt4o to convert images into flashcards.
    Output Generation: Transcription or image conversion results are presented to the user.



## Contributing

Contributions to SonicAid are welcome. Please fork the repository and submit pull requests with your suggested changes.

## License

This software is provided "as is", without warranty of any kind. You are free to modify and use the software for personal and educational purposes, but redistribution or commercial use is not permitted.

## Contact

For any inquiries or support, please contact me at [Mika Martin's Email](nieuwenhuyzenmikamartin@gmail.com).
