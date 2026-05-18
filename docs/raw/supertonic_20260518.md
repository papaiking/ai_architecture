# Supertonic — Lightning Fast, On-Device, Accurate TTS

Source: https://github.com/supertone-inc/supertonic
Accessed: 2026-05-18

**Supertonic** is a lightning-fast, on-device multilingual text-to-speech system designed for local inference with minimal overhead. Powered by ONNX Runtime, it runs entirely on your device—no cloud, no API calls, no privacy concerns.

### Highlights

- ⚡ **Blazingly Fast** — Low-latency, real-time synthesis across desktop, browser, mobile, and edge
- 🌍 **31-Language Multilingual** — Synthesize directly from text across 31 languages
- 🪶 **99M-Parameter Open-Weight Model** — Compact checkpoint, fraction of 0.7B–2B class TTS systems
- 📱 **Edge-Device Ready** — Runs on desktop, mobile, browsers, Raspberry Pi, e-readers, zero network dependency
- 🔊 **44.1kHz High-Quality Audio** — Studio-grade 44.1kHz 16-bit WAV directly
- 🎭 **Expression Tags** — 10 inline tags (e.g. `<laugh>`, `<breath>`, `<sigh>`)
- 🛠️ **Multi-Runtime SDKs** — Python, Node.js, Browser (WebGPU), Java, C++, C#, Go, Swift, iOS, Rust, Flutter

### Supported Languages (31)

Arabic, Bulgarian, Croatian, Czech, Danish, Dutch, English, Estonian, Finnish, French, German, Greek, Hindi, Hungarian, Indonesian, Italian, Japanese, Korean, Latvian, Lithuanian, Polish, Portuguese, Romanian, Russian, Slovak, Slovenian, Spanish, Swedish, Turkish, Ukrainian, Vietnamese

### Update News

- **2026.04.29** - Supertonic 3 released with 31-language support
- **2026.01.22** - Voice Builder live: turn your voice into a deployable, edge-native TTS
- **2026.01.06** - Supertonic 2 released with 5-language support
- **2025.12.10** - `supertonic` PyPI package available
- **2025.12.10** - Added 6 new voice styles (M3-M5, F3-F5)
- **2025.12.08** - Optimized ONNX models via OnnxSlim

### Quick Start

```bash
pip install supertonic
```

```python
from supertonic import TTS

tts = TTS(auto_download=True)
style = tts.get_voice_style(voice_name="M1")
text = "Supertonic is a lightning fast, on-device TTS system."
wav, duration = tts.synthesize(
    text=text, lang="en", voice_style=style,
    total_steps=8, speed=1.05,
)
tts.save_audio(wav, "output.wav")
```

### Technical Details

- **Runtime**: ONNX Runtime for cross-platform inference
- **Browser Support**: onnxruntime-web for client-side inference
- **Batch Processing**: Supports batch inference
- **Audio Output**: 44.1kHz 16-bit WAV

### Performance Highlights

- **Reading Accuracy**: Competitive WER/CER against VoxCPM2, OmniVoice, Qwen3-TTS
- **Runtime**: Fast CPU inference vs GPU baselines, substantially less memory
- **Model Size**: ~99M parameters, much smaller than 0.7B-2B class TTS systems

### Models & Versions

| | Supertonic 3 | Supertonic 2 | Supertonic 1 |
|---|---|---|---|
| Status | Latest | Stable | Legacy |
| Parameters | ~99M | ~66M | ~66M |
| Languages | 31 | 5 | 1 (en) |
| Expression Tags | 10 tags | — | — |

### Citation

```bibtex
@article{kim2025supertonic,
  title={SupertonicTTS: Towards Highly Efficient and Streamlined Text-to-Speech System},
  author={Kim, Hyeongju and Yang, Jinhyeok and Yu, Yechan and Ji, Seunghun and Morton, Jacob and Bous, Frederik and Byun, Joon and Lee, Juheon},
  journal={arXiv preprint arXiv:2503.23108},
  year={2025},
  url={https://arxiv.org/abs/2503.23108}
}
```

### License

- Code: MIT License
- Model: OpenRAIL-M License
