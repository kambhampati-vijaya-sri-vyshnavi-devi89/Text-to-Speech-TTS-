
# Text-to-Speech (TTS) Using `pyttsx3`  

## Description  
This project converts text into speech using the `pyttsx3` library in Python. It allows users to modify speech properties like speed and voice.  

## Features  
✅ Converts text to speech  
✅ Supports different languages and voices (if available in the system)  
✅ Adjustable speech rate  

## Installation  
Make sure `pyttsx3` is installed:  
```sh
pip install pyttsx3
```

## Usage  

### 1. **Python Script (`tts.py`)**  
```python
import pyttsx3

def text_to_speech_function(text, lang='english'):
    engine = pyttsx3.init()
    rate = engine.getProperty('rate')
    engine.setProperty('rate', rate - 40)
    engine.setProperty('voice', lang)  # Note: Voice ID must be set correctly
    engine.say(text)
    engine.runAndWait()

text_to_speech_function('I love Python and I love myself')
```

### 2. **Run the script**  
```sh
python tts.py
```
You will hear the sentence:  
🎙️ *" I love myself."*  

## Changing Voices  
To use different voices, first, **list available voices**:  
```python
engine = pyttsx3.init()
voices = engine.getProperty('voices')
for index, voice in enumerate(voices):
    print(f"Voice {index}: {voice.name} ({voice.id})")
```
Then, update the script to use a specific voice:  
```python
engine.setProperty('voice', voices[1].id)  # Change voice (Male/Female)
```

## Notes  
- The script will **speak out loud** when executed.  
- Voice selection depends on the **installed voices** on your system.  
- You might need to **adjust the `lang` parameter** using a valid **voice ID** instead of `'english'`.  

