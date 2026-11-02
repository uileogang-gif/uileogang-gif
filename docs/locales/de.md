| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Jonas Falk

```text
Standort:     Göteborg, Schweden (UTC+1 / UTC+2)
Schwerpunkt:  Systemnahe Software & Digitale Signalverarbeitung (DSP)
Stack:        Rust, Modernes C++ (C++20), Zig, Linux-Echtzeitaudio
Status:       Entwicklung von Open-Source-Raumaudio-Tools & akustischer Telemetrie
```

---

## Über Mich

Ich bin Senior Systems-Software-Entwickler mit Spezialisierung auf deterministische Echtzeit-Audioarchitekturen, räumliche Akustik und hardwarenahe Recheneffizienz. Mein ingenieurtechnischer Schwerpunkt liegt auf der Entwicklung von Audio-Pipelines ohne dynamische Speicherallokation (Zero-Allocation), dem Entwurf lock-freier Nebenläufigkeitsprimitive und der Ausrichtung von Speicherstrukturen für optimale SIMD-Vektorisierung.

Wenn ich nicht gerade lock-freie Ringpuffer mittels Hardware-Countern profiliere oder Phasenlinearitäten von Filtern am Oszilloskop messe, nehme ich an der schwedischen Westküste Vogelzug-Akustikmuster im Feld auf oder restauriere analoge Tonbandelektronik.

- 🔭 Entwurf deterministischer, lock-freier Echtzeit-Audionetzwerke.
- ⚡ Optimierung von SIMD-Kernels (AVX-512 & ARM NEON) für partitionierte Impulsfaltungen.
- 🛡️ Härtung von Embedded-Akustiksensor-Firmware durch strikte Speicherisolation.
- ☕ Angetrieben von hell geröstetem Single-Origin-Kaffee und reproduzierbaren Build-Systemen.

---

## Technischer Stack & Werkzeuge

| Fachbereich | Kerntechnologien | Analyse- & Messwerkzeuge |
| :--- | :--- | :--- |
| **System- & Echtzeitprogrammierung** | Rust, C++20, Zig, C (C11) | eBPF, Valgrind, perf, criterion.rs |
| **Audio-DSP & Raumklang** | HRTF-Filter, B-Format Ambisonics, SIMD-Faltung | JACK Audio, ALSA, PortAudio, WebAudio |
| **Embedded & Hardware** | STM32 (Cortex-M4/M7), ESP32-S3, KiCad | I2S-Codecs, Logikanalysatoren, Oszilloskope |
| **Umgebung & Infrastruktur** | Arch Linux, NixOS, Alpine | Neovim, CMake, Ninja, Git, Docker |

---

## Ausgewählte Open-Source-Projekte

### `solstice-dsp`
> *Header-first Bibliothek für räumliche Audiofaltung in Rust – vollständig allokationsfrei.*
- **Kernarchitektur**: B-Format-Ambisonics-Decoder mit SIMD-partitionierter FFT-Faltung.
- **Latenzgarantie**: Unter 1,2 ms Verarbeitungszeit bei 96 kHz / 64 Samples Puffergröße ohne Nutzung des Heaps.
- **Zielsysteme**: Nativer Desktop (Linux/macOS/Windows) sowie WebAssembly für interaktive Web-Synthesizer.

### `pulsefield`
> *Akustischer Telemetrie-Daemon mit extrem geringer Leistungsaufnahme für ökologische Fernabhörstationen.*
- **Hardware-Integration**: Eigene STM32-Firmware mit LTE-M / LoRaWAN-Anbindung und Ringspeicher-Fallback auf SD-Karten.
- **Kompression**: Adaptives FLAC-Frame-Packing, optimiert für schmalbandige, solar bedingte Übertragungsspitzen.
- **Zuverlässigkeit**: Hardware-Watchdog-Timer und fehlertolerante Wiederherstellungsroutinen, konzipiert für subpolare skandinavische Winter.

### `decibel-tui`
> *Terminalbasierter Lautheitsanalysator nach den Rundfunkstandards ITU-R BS.1770-4 und EBU R128.*
- **Benutzeroberfläche**: Tastaturgesteuerte ratatui-Oberfläche mit Echtzeit-True-Peak-Messung und LUFS-Integrationsprotokoll.
- **Treiberebene**: Direkter Zugriff auf ALSA- und CoreAudio-Subsysteme ohne Zwischenschaltung des Desktop-Mixers.

---

## Ingenieursgrundsätze

1. **Deterministische Pfade**: In der Echtzeit-Audioschleife darf unter keinen Umständen Speicher allokiert, ein Mutex gesperrt oder unvorhersehbare Ein-/Ausgabe getätigt werden.
2. **Erste Prinzipien verstehen**: Zuerst die Hardware-Cache-Hierarchie, Befehlslatenzen und die physikalischen Grenzen des Siliziums verstehen, bevor Abstraktionen geschichtet werden.
3. **Respekt vor Langlebigkeit**: Modularen, abhängigkeitsfreien Code schreiben, der auch in zehn Jahren noch ohne Wartung auf sparsamen Mikrochips kompiliert und fehlerfrei läuft.

---

## Kontakt & Öffentliche Schlüssel

- **Website / Technische Notizen**: `https://jonasfalk.dev`
- **E-Mail**: `jonas [at] jonasfalk.dev`
- **Matrix**: `@jonas:matrix.org`
- **GPG-Fingerprint**: `7E9B 4410 82C9 52A1 D84F  2F0A 1B83 99C0 411E 32A5`
