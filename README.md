| [KR 한국어](./docs/locales/ko.md) | [US English](./README.md) | [JP 日本語](./docs/locales/ja.md) | [CN 简体中文](./docs/locales/zh-CN.md) | [ES Español](./docs/locales/es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./docs/locales/fr.md) | [DE Deutsch](./docs/locales/de.md) | [RU Русский](./docs/locales/ru.md) | [SA العربية](./docs/locales/ar.md) | [IN हिन्दी](./docs/locales/hi.md) |

---

# Jonas Falk

```text
Location: Gothenburg, Sweden (UTC+1 / UTC+2)
Focus:    Low-Latency Systems & Digital Signal Processing (DSP)
Stack:    Rust, Modern C++ (C++20), Zig, Linux Real-Time Audio
Status:   Building open audio spatialization tooling & remote acoustic telemetry
```

---

## About Me

I am a systems software engineer with a deep fascination for the intersection of acoustics, spatial mathematics, and mechanical computing efficiency. Most of my working hours are spent crafting zero-allocation audio algorithms, optimizing memory layouts for SIMD execution, and writing firmware for outdoor solar-powered acoustic monitoring arrays.

When I am not profiling lock-free ring buffers or measuring filter phase distortions with an oscilloscope, you can usually find me field-recording bird migration patterns across Nordic archipelagos or restoring analog reel-to-reel tape decks.

- 🔭 Designing deterministic, lock-free real-time audio graphs.
- ⚡ Optimizing SIMD kernels (AVX-512 & ARM NEON) for acoustic impulse convolutions.
- ☕ Powered by single-origin light roasts and reproducible build systems.

---

## Technical Stack & Tooling

| Domain | Primary Technologies | Practical Utilities |
| :--- | :--- | :--- |
| **Systems & Real-Time** | Rust, C++20, Zig, C (C11) | eBPF, Valgrind, perf, criterion.rs |
| **Audio DSP & Spatialization** | HRTF Filters, B-Format Ambisonics, SIMD Convolver | JACK Audio, ALSA, PortAudio, WebAudio |
| **Embedded & Hardware** | STM32 (Cortex-M4/M7), ESP32-S3, KiCad | I2S Codecs, Logic Analyzers, Oscilloscopes |
| **Environment & Infrastructure** | Arch Linux, NixOS, Alpine | Neovim, CMake, Ninja, Git, Docker |

---

## Featured Open Source Projects

### `solstice-dsp`
> *Zero-allocation, header-first spatial audio convolution library written in Rust.*
- **Core Architecture**: B-format Ambisonics decoder featuring SIMD-partitioned FFT convolution.
- **Latency Guarantee**: Sub-1.2ms processing budget at 96kHz / 64 buffer samples without dynamic heap allocation.
- **Targets**: Native desktop (Linux/macOS/Windows) and WebAssembly target for interactive web synthesizers.

### `pulsefield`
> *Ultra-low power acoustic telemetry daemon for remote ecological listening stations.*
- **Hardware Integration**: Custom STM32 firmware communicating via LTE-M / LoRaWAN with fall-back SD card ring buffer.
- **Compression**: Adaptive FLAC frame packing optimized for narrow-bandwidth intermittent solar bursts.
- **Reliability**: Self-healing watchdog pipeline designed to withstand harsh Scandinavian winter conditions.

### `decibel-tui`
> *Terminal-based broadcast loudness analyzer adhering strictly to ITU-R BS.1770-4 and EBU R128 standards.*
- **User Interface**: Keyboard-driven ratatui interface with real-time true-peak metering and LUFS integration logs.
- **Driver Support**: Direct ALSA and CoreAudio backend hook without intermediary desktop mixing layers.

---

## Engineering Principles

1. **Deterministic Hot Paths**: The audio processing callback must never allocate memory, acquire locks, or perform non-deterministic disk/network I/O.
2. **First-Principles Understanding**: Always understand the hardware cache hierarchies, instruction latency, and transistor limits before introducing high-level abstractions.
3. **Respect for Physical Longevity**: Write modular, dependency-minimal code that can compile and operate unmaintained on low-power silicon a decade from now.

---

## Contact & Public Keys

- **Website / Tech Notes**: `https://jonasfalk.dev`
- **Email**: `jonas [at] jonasfalk.dev`
- **Matrix**: `@jonas:matrix.org`
- **GPG Fingerprint**: `7E9B 4410 82C9 52A1 D84F  2F0A 1B83 99C0 411E 32A5`
