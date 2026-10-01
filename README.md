# Audio Cleaner Setup

## Requirements

- Windows 10 or later
- Python 3.10 or later, with Tkinter available
- Internet access for the initial package install

The `imageio-ffmpeg` package provides the FFmpeg executable used for compressed audio such as AAC and M4A. A separate system-wide FFmpeg install is not required.

## Install

Open PowerShell in the project folder (`f:\midterm`) and run:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install numpy scipy soundfile noisereduce imageio-ffmpeg
```

If PowerShell blocks environment activation, skip the activation command and replace `python` in the commands below with `\.venv\Scripts\python.exe`.

In VS Code, select the project interpreter with **Python: Select Interpreter**, then choose `.venv\Scripts\python.exe`.

## Run the App

Launch the graphical interface with either command:

```powershell
python cleaner.py
```

or:

```powershell
python try.py
```

Choose the input audio, output path and format, then select **Clean audio**. The default output is a WAV copy next to the source. Supported inputs include WAV, FLAC, OGG, MP3, AAC, M4A, WMA, OPUS, and MP4. Compressed formats that SoundFile cannot read are decoded through the bundled FFmpeg executable.

## Command-Line Use

Passing arguments to `cleaner.py` runs the command-line interface instead of opening the window:

```powershell
python cleaner.py "C:\Audio\interview.aac" --strength 0.85 --format wav
```

For speech-focused RNNoise processing, install its optional package:

```powershell
python -m pip install pyrnnoise
```

If RNNoise is unavailable or incompatible, the cleaner falls back to `noisereduce`.

## VS Code Tasks

The included `tasks.json` is at the project root. VS Code discovers project tasks from `.vscode\tasks.json`; move or copy it there if you want to use those tasks. On Windows, set each task's `command` to `.venv\Scripts\python.exe` so it uses the environment containing the audio dependencies.
