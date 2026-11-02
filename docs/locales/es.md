| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Jonas Falk

```text
Ubicación: Gotemburgo, Suecia (UTC+1 / UTC+2)
Especialidad: Sistemas de Baja Latencia y Procesamiento Digital de Señales (DSP)
Stack: Rust, C++ Moderno (C++20), Zig, Audio Linux en Tiempo Real
Estado: Creando herramientas abiertas de espacialización de audio y telemetría acústica
```

---

## Sobre Mí

Soy un ingeniero de software de sistemas apasionado por el punto de encuentro entre la acústica, las matemáticas espaciales y la eficiencia mecánica del silicio. Dedico la mayor parte de mi tiempo al diseño de algoritmos de audio con cero asignaciones dinámicas (zero-allocation), la optimización de disposiciones de memoria para ejecución SIMD y el desarrollo de firmware para estaciones remotas de monitorización acústica alimentadas por energía solar.

Cuando no estoy perfilando buffers circulares libres de bloqueos (lock-free) o midiendo la distorsión de fase de filtros con un osciloscopio, suelo estar grabando cantos de aves migratorias en los archipiélagos nórdicos o restaurando magnetófonos analógicos de bobina abierta.

- 🔭 Diseñando grafos de audio deterministas y sin bloqueos para tiempo real.
- ⚡ Optimizando núcleos SIMD (AVX-512 y ARM NEON) para convolución de impulsos acústicos.
- ☕ Impulsado por café de tueste claro de origen único y sistemas de compilación reproducibles.

---

## Tecnologías y Herramientas

| Dominio | Tecnologías Principales | Utilidades y Diagnóstico |
| :--- | :--- | :--- |
| **Sistemas y Tiempo Real** | Rust, C++20, Zig, C (C11) | eBPF, Valgrind, perf, criterion.rs |
| **DSP y Espacialización de Audio** | Filtros HRTF, Ambisonics B-Format, Convolvedor SIMD | JACK Audio, ALSA, PortAudio, WebAudio |
| **Hardware y Embebidos** | STM32 (Cortex-M4/M7), ESP32-S3, KiCad | Códecs I2S, Analizadores lógicos, Osciloscopios |
| **Entorno e Infraestructura** | Arch Linux, NixOS, Alpine | Neovim, CMake, Ninja, Git, Docker |

---

## Proyectos Destacados de Código Abierto

### `solstice-dsp`
> *Librería de convolución de audio espacial header-first y sin asignación en memoria dinámica escrita en Rust.*
- **Arquitectura Base**: Decodificador Ambisonics B-format con convolución FFT particionada mediante SIMD.
- **Garantía de Latencia**: Menos de 1.2 ms de tiempo de procesamiento a 96 kHz / 64 muestras de buffer sin tocar el heap.
- **Plataformas**: Escritorio nativo (Linux/macOS/Windows) y WebAssembly para sintetizadores web interactivos.

### `pulsefield`
> *Demonio de telemetría acústica de ultrabajo consumo para estaciones de escucha ecológica en lugares remotos.*
- **Integración de Hardware**: Firmware para microcontrolador STM32 con enlace LTE-M / LoRaWAN y buffer circular en tarjeta SD.
- **Compresión**: Empaquetado adaptativo de tramas FLAC optimizado para transmisiones solares intermitentes de bajo ancho de banda.
- **Fiabilidad**: Secuencia de recuperación automática por watchdog pensada para resistir los inviernos escandinavos.

### `decibel-tui`
> *Analizador de sonoridad en terminal que cumple rigurosamente las normas ITU-R BS.1770-4 y EBU R128.*
- **Interfaz de Usuario**: TUI basada en ratatui completamente operable por teclado con medición True-Peak y registro LUFS integrado.
- **Acceso a Controladores**: Conexión directa con las capas inferiores de ALSA y CoreAudio sin mezcladores intermedios.

---

## Principios de Ingeniería

1. **Rutas Críticas Deterministas**: En el bucle de procesamiento de audio en tiempo real nunca se debe asignar memoria, bloquear hilos ni realizar operaciones de entrada/salida no deterministas.
2. **Comprensión desde los Primeros Principios**: Entender la jerarquía de cachés de la CPU, la latencia de instrucciones y los límites del silicio antes de añadir capas de abstracción.
3. **Respeto por la Longevidad del Hardware**: Desarrollar software modular y sin dependencias superfluas que pueda compilarse y funcionar sin intervención en silicio de bajo consumo dentro de diez años.

---

## Contacto y Claves Públicas

- **Sitio Web / Notas Técnicas**: `https://jonasfalk.dev`
- **Correo Electrónico**: `jonas [at] jonasfalk.dev`
- **Matrix**: `@jonas:matrix.org`
- **Huella GPG**: `7E9B 4410 82C9 52A1 D84F  2F0A 1B83 99C0 411E 32A5`
