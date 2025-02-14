# Speech to Text (STT) Project

This project leverages `Selenium` and `webdriver_manager` to utilize Chrome's built-in text-to-speech feature. It's designed for simplicity and ease of use, allowing you to configure continuous text-to-speech functionality and optional English translation.

## Features

- **Continuous Speech-to-Speech**: Decide if you want the text-to-speech functionality to run continuously.
- **Optional English Translation**: Choose whether to translate text to English before speaking.
- **100% accuracy**: Gives you the 100% accuracy in listening by google chrome's algorithm.

## Prerequisites

- `Selenium`
- `webdriver_manager`

## Setup

1. **Install dependencies**:
    ```sh
    pip install selenium webdriver_manager mtranslate
    ```

2. **Create Configuration Files**:
    - `write_text_file_path.txt`: This file will be the file in which the text is written by converting from speech.

## Parameters

* `write_text_file_path.txt`: This file will be the file in which the text is written by converting from speech.
* `translate` (bool): Set to True to translate the text to English before speaking, False otherwise.

## Usage

To use the text-to-speech functionality, import the `Listener` class from `python-speech-to-text` and initialize it with the appropriate parameters.

If you want the speech-to-text functionality to run continuously, it is recommended to use threading. This will prevent the function from blocking the execution of further code until it is stopped.

Example with Threading

```python
import os
import threading
from python-speech-to-text import Listener

a = Listener(os.path.join(os.getcwd(), "text.txt"))

listener_thread = threading.Thread(target=a.listen) # It is compulsory to use threading or it will just block the execution of other code and also won't stop if needed.
listener_thread.start() # start the thread

# Now for stop listening

a.StopRecognition()
listener_thread.join() # wait until the thread finishes
```

To make the program listen properly, speak a bit loud and clear words.

**This project is managed by Artex AI. Soon an improved and stable version will roll out**