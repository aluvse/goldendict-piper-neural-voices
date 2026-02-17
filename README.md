````markdown
# Piper TTS for GoldenDict-ng

Fast, local, and private neural text-to-speech integration.

## Setup

1. **Requirements**: [Piper Engine](https://github.com/rhasspy/piper) and [FFmpeg](https://ffmpeg.org/download.html) (ffplay).
2. **Voices**: Download `.onnx` and `.json` files from the [Hugging Face Hub](https://huggingface.co/rhasspy/piper-voices/tree/main).
3. **Integration**: Add a new **Program** in GoldenDict (Type: Audio) and use the command template below.

## Command Template

```bash
echo %GDWORD% | [path_to_piper] -m [path_to_model.onnx] --output-raw | ffplay -ar 22050 -ac 1 -f s16le -nodisp -autoexit -i -
```
````

## Tuning

Add these flags to the piper command to refine the output:

- **Speed**: `--length_scale 1.1` (slower) or `0.8` (faster). Default is `1.0`.
- **Phoneme Silence**: `--sentence_silence 0.2` (adds a delay between sentences).
- **Variability**: `--noise_scale 0.667` (emotional range) and `--noise_w 0.8` (duration variability).
- **GPU Acceleration**: `--use-cuda` (if supported by your build and hardware).
- **Speaker ID**: `--speaker [ID]` (for multi-speaker models, e.g., `--speaker 0`).

```

```
