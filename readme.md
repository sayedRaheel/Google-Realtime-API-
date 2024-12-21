# Google Realtime API Integration

This project demonstrates real-time audio and video interaction using Google's Gemini API. It allows for live audio conversations and video streaming through either your camera or screen sharing.

## Features

- Real-time audio conversation with Gemini AI
- Video streaming options:
  - Camera mode
  - Screen sharing mode
  - No video mode
- Bi-directional audio support
- Text input capability

## Prerequisites

- Python 3.11 or later (if using earlier versions, the script includes compatibility imports)
- Google AI API key from [Google AI Studio](https://aistudio.google.com)
- Headphones (recommended to prevent audio feedback)

## Installation

1. Clone this repository or download the script

2. Install the required dependencies:
```bash
pip install google-genai opencv-python pyaudio pillow mss
```

3. Set up your Google API key:

For Unix/Mac:
```bash
export GOOGLE_API_KEY='your_api_key_here'
```

For Windows Command Prompt:
```cmd
set GOOGLE_API_KEY=your_api_key_here
```

For Windows PowerShell:
```powershell
$env:GOOGLE_API_KEY = 'your_api_key_here'
```

## Usage

### Basic Usage (Camera Mode)
```bash
python live_api_starter.py
```

### Screen Sharing Mode
```bash
python live_api_starter.py --mode screen
```

### No Video Mode
```bash
python live_api_starter.py --mode none
```

## Command Options

The script accepts the following mode options:
- `camera`: Uses your computer's camera (default)
- `screen`: Captures your screen
- `none`: Disables video input

## Important Notes

1. **Use Headphones**: Using headphones is strongly recommended to prevent audio feedback, as the system default audio input/output might not include echo cancellation.

2. **Token Limits**: Be aware of token limits in your conversations. If you receive a token limit error, try breaking up your input into smaller chunks.

3. **Audio Quality**: The script uses the following audio configurations:
   - Input Sample Rate: 16000 Hz
   - Output Sample Rate: 24000 Hz
   - Format: 16-bit PCM
   - Channels: Mono (1 channel)

## Troubleshooting

### Common Issues:

1. **Token Limit Errors**
   - Error message: `generic::invalid_argument: Input request contains (XXXXX) tokens`
   - Solution: Reduce the length of your input or break it into smaller segments

2. **Audio Device Issues**
   - Ensure your default audio input/output devices are properly configured
   - Check if PyAudio can detect your audio devices

3. **Video Device Issues**
   - Make sure your camera is not being used by another application
   - Check if your camera permissions are properly set

## License

- Google Project 

## Acknowledgments

This implementation uses Google's Gemini API and various Python libraries including:
- google-genai
- opencv-python
- pyaudio
- pillow
- mss

## Disclaimer

This is a demonstration project and should be used in accordance with Google's API terms of service and usage guidelines. Make sure to review and comply with all applicable terms and conditions.