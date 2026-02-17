# 🎧 Piper TTS for GoldenDict-ng

Fast, local, and private neural text-to-speech.

## 🚀 Quick Start

1. Open **Edit** -> **Dictionaries** -> **Sources** -> **Programs**.
2. Click **Add**, set type to **Audio**, and paste a command from below.
3. **Requirements:** [Piper Engine](https://github.com/rhasspy/piper) & [FFmpeg (ffplay)](https://ffmpeg.org/download.html).
4. **Get Voices:** [Official Voice Hub](https://huggingface.co/rhasspy/piper-voices/tree/main) (Download both `.onnx` and `.json` files).

---

## 🪟 Windows

_Path: `C:\piper\piper.exe` | Voices: `C:\piper\voices\`_

- **Bryce (Natural):**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\en_US-bryce-medium.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan High (HQ):**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\en_US-ryan-high.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan Medium:**
  `cmd /v:on /c "echo %GDWORD%|C:\piper\piper.exe -m C:\piper\voices\en_US-ryan-medium.onnx --output-raw | C:\piper\ffplay.exe -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🐧 Linux

- **Bryce:** `sh -c "echo '%GDWORD%' | piper -m ./voices/en_US-bryce-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan High:** `sh -c "echo '%GDWORD%' | piper -m ./voices/en_US-ryan-high.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan Medium:** `sh -c "echo '%GDWORD%' | piper -m ./voices/en_US-ryan-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🍎 macOS

- **Bryce:** `zsh -c "echo '%GDWORD%' | ./piper -m ./voices/en_US-bryce-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan High:** `zsh -c "echo '%GDWORD%' | ./piper -m ./voices/en_US-ryan-high.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`
- **Ryan Medium:** `zsh -c "echo '%GDWORD%' | ./piper -m ./voices/en_US-ryan-medium.onnx --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -"`

---

## 🛠 Tuning

Add these flags before `--output-raw`:

- **Slower:** `--length_scale 1.1`
- **Faster:** `--length_scale 0.9`
- **Natural Pause:** `--sentence_silence 0.2`
