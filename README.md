# ClearTone Studio — Voice & Background Noise Divider

## Requirements

- Windows 10 or later (also works on Linux/macOS via CLI or Web UI)
- Python 3.10 or later, with Tkinter available
- Internet access only for the initial package install

The `imageio-ffmpeg` package provides the FFmpeg executable used for MP3, AAC, M4A, WMA, OPUS, and MP4 audio. A separate system-wide FFmpeg install is not required.

## Install

Open PowerShell in the project folder and run:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install numpy scipy soundfile noisereduce imageio-ffmpeg
```

If PowerShell blocks environment activation, replace `python` in the commands below with `.venv\Scripts\python.exe`.

## Features

- **Divide Voice & Background Noise**: Splits a single `.mp3`, `.wav`, `.flac`, `.m4a`, `.ogg`, etc. file into separate **Human Voice** and **Background Noise** stems in low-RAM chunked blocks (~100-180 MB RAM, tuned for dual-core CPUs without GPU).
- **Recognize Background Noise Types**: Analyzes the background stem to identify **Wind / Gusts**, **Animal (Birds, Dog/Bark, Insects/Crickets)**, **Rain / Water**, **Traffic / Engine / Hum**, **Clicks / Impacts**, **Crowd / Chatter**, **Static / Hiss**, and **Music / Tonal Bed**, along with time-segment breakdowns.
- **Choose What to Delete & Download**:
  - **Delete Background Noise** (keep clean Human Voice)
  - **Delete Human Voice** (keep Background Noise)
  - **Custom / Selective Delete** (delete Human Voice and/or specific recognized noise types such as Wind or Animal)
  - Export/download as **WAV**, **MP3**, **FLAC**, or **OGG**, or download both stems.

## Run the Graphical Studio

Launch the upgraded Desktop Studio:

```powershell
python cleaner.py
```

or:

```powershell
python try.py
```

Or launch the lightweight local **Web Studio** in your browser (or click **Open Web UI** inside the desktop window):

```powershell
python cleaner.py --web
```

## Command-Line Use

Divide an MP3 into Human Voice + Background Noise stems and recognize noise categories:

```powershell
python cleaner.py "C:\Audio\recording.mp3" --divide --format mp3
```

Delete Human Voice and keep only Background Noise:

```powershell
python cleaner.py "C:\Audio\recording.mp3" --delete voice -o background_only.wav
```

Selectively delete specific recognized noises (e.g., Wind):

```powershell
python cleaner.py "C:\Audio\outdoor.wav" --delete custom --remove-noise wind -o outdoor_no_wind.wav
```

Analyze and print the background noise report only:

```powershell
python cleaner.py "C:\Audio\outdoor.mp3" --analyze
```

Legacy stationary spectral-gating denoising remains supported via `--engine noisereduce`.

# Here's the Perfect Version of Noise remover and Divider

## What's New?
Now you can select and play background noise separate from Human voice, you can play also Human voice separate in background noise.
Detect what noise is it, if be an animal, wind, truck, etc.....
Wave view of Human and Background sound
Can download the output 
Desktop and UI(local) for browser
Can run even in Low-end Laptop and desktop


<img width="1366" height="768" alt="ui noise divider" src="https://github.com/user-attachments/assets/2cb9ea11-3094-489d-be2b-335265912cc4" />
<img width="1366" height="768" alt="noise dvider1" src="https://github.com/user-attachments/assets/414f8692-e4f8-40b9-a53a-6d637e1cb086" />
<img width="1366" height="768" alt="noise" src="https://github.com/user-attachments/assets/4dae2f32-efe7-4c06-a181-fbcc0f5c4ddc" />
<img width="1366" height="768" alt="noise divider" src="https://github.com/user-attachments/assets/12d6091a-9ecf-4edb-8af0-dce1ed3d8269" />
<img width="1366" height="768" alt="noises" src="https://github.com/user-attachments/assets/a4ea4473-47f9-4ec7-9949-7d8a8b81ad2d" />
