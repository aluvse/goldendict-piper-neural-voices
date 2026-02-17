# 🎧 Piper TTS for GoldenDict-ng

Fast, local, and private neural text-to-speech integration for GoldenDict-ng. This project provides optimized command-line presets to use [Piper](https://github.com/rhasspy/piper) as an external audio source.

## 🚀 Quick Start

1. **Install Piper:** Download the [Piper Engine](https://github.com/rhasspy/piper) for your OS.
2. **Install FFmpeg:** Ensure [ffplay](https://ffmpeg.org/download.html) is available in your PATH.
3. **Download Voices:** - Go to the [Official Voice Hub](https://huggingface.co/rhasspy/piper-voices/tree/main).
   - Choose a language (e.g., `en/en_US/bryce/medium/`).
   - Download **both** `.onnx` and `.onnx.json` files.
4. **Setup GoldenDict:**
   - Open **Edit** -> **Dictionaries** -> **Sources** -> **Programs**.
   - Click **Add**, set type to **Audio**, and paste a command from below.

---

## 🪟 Windows

_Recommended path: `C:\piper\piper.exe` | Voices: `C:\piper\voices\`_

- **Bryce (Natural):**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\en_US-bryce-medium.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan High (HQ):**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\en_US-ryan-high.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Thorsten (German):**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\de_DE-thorsten-high.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🐧 Linux

- **Bryce:** `sh -c "echo '%GDWORD%' | piper -m ./voices/en_US-bryce-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan High:** `sh -c "echo '%GDWORD%' | piper -m ./voices/en_US-ryan-high.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🍎 macOS

- **Bryce:** `zsh -c "echo '%GDWORD%' | ./piper -m ./voices/en_US-bryce-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🛠 Tuning

Add these flags before `--output-raw` in the command:

- **Slower:** `--length_scale 1.1`
- **Faster:** `--length_scale 0.9`
- **Natural Pause:** `--sentence_silence 0.2`

---

_Note: This repository does not host voice models. Download them from the Official Voice Hub link above._
