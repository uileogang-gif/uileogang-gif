| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Jonas Falk

```text
Localização:  Gotemburgo, Suécia (UTC+1 / UTC+2)
Foco:         Sistemas de Baixa Latência e Processamento Digital de Sinais (DSP)
Stack:        Rust, C++ Moderno (C++20), Zig, Áudio em Tempo Real no Linux
Status Atual: Desenvolvendo ferramentas abertas de áudio espacial e telemetria acústica
```

---

## Sobre Mim

Sou engenheiro de software de sistemas fascinado pela convergência entre acústica, matemática espacial e eficiência mecânica de computação. Passo a maior parte dos meus dias projetando algoritmos de áudio sem alocação dinâmica (zero-allocation), organizando layouts de memória para vetorização SIMD e programando firmware para matrizes de monitoramento acústico remoto alimentadas por energia solar.

Quando não estou analisando o desempenho de filas circulares sem travamento (lock-free) ou medindo a distorção de fase de filtros com um osciloscópio, costumo gravar cantos de pássaros migratórios em arquipélagos nórdicos ou restaurar gravadores analógicos de fita de rolo.

- 🔭 Arquitetura de grafos de áudio determinísticos e lock-free para tempo real.
- ⚡ Otimização de núcleos SIMD (AVX-512 e ARM NEON) para convolução de respostas ao impulso.
- ☕ Movido a café especial de torra clara e sistemas de compilação reproduzíveis.

---

## Stack Tecnológica & Ferramentas

| Domínio | Tecnologias Principais | Ferramentas de Medição & Diagnóstico |
| :--- | :--- | :--- |
| **Sistemas & Tempo Real** | Rust, C++20, Zig, C (C11) | eBPF, Valgrind, perf, criterion.rs |
| **DSP de Áudio & Espacialização** | Filtros HRTF, Ambisonics B-Format, Convolução SIMD | JACK Audio, ALSA, PortAudio, WebAudio |
| **Sistemas Embarcados & Hardware** | STM32 (Cortex-M4/M7), ESP32-S3, KiCad | Codecs I2S, Analisadores Lógicos, Osciloscópios |
| **Ambiente & Infraestrutura** | Arch Linux, NixOS, Alpine | Neovim, CMake, Ninja, Git, Docker |

---

## Projetos Open Source em Destaque

### `solstice-dsp`
> *Biblioteca de convolução de áudio espacial header-first em Rust, totalmente livre de alocação no heap.*
- **Arquitetura Principal**: Decodificador de Ambisonics formato B com convolução FFT particionada por SIMD.
- **Garantia de Latência**: Menos de 1,2 ms de tempo de processamento a 96 kHz com buffers de 64 amostras sem alocar memória dinâmica.
- **Plataformas**: Desktop nativo (Linux/macOS/Windows) e WebAssembly para sintetizadores interativos na web.

### `pulsefield`
> *Daemon de telemetria bioacústica de ultra-baixo consumo para estações remotas de observação ecológica.*
- **Integração de Hardware**: Firmware para STM32 integrado a enlaces LTE-M / LoRaWAN com fallback de buffer circular em cartão SD.
- **Compressão**: Empacotamento adaptativo de quadros FLAC otimizado para transmissões curtas e intermitentes movidas a energia solar.
- **Robustez**: Mecanismo de watchdog autorregenerativo projetado para suportar o rigoroso inverno nórdico.

### `decibel-tui`
> *Analisador de sonoridade em terminal estritamente alinhado às normas de transmissão ITU-R BS.1770-4 e EBU R128.*
- **Interface**: TUI desenvolvida com ratatui controlada inteiramente pelo teclado, com medição True-Peak em tempo real e histórico de integração LUFS.
- **Acesso ao Driver**: Conexão direta às camadas de ALSA e CoreAudio, ignorando mixadores intermediários do sistema operacional.

---

## Princípios de Engenharia

1. **Caminhos Críticos Determinísticos**: Na rotina de retorno (callback) de áudio em tempo real, nunca aloque memória, nunca dispute travas e nunca execute I/O não determinístico.
2. **Entendimento por Primeiros Princípios**: Domine a hierarquia de caches da CPU, a latência de instruções e os limites físicos do silício antes de introduzir abstrações de alto nível.
3. **Respeito à Longevidade do Hardware**: Escreva código modular e sem dependências desnecessárias, capaz de compilar e rodar sem manutenção em microcontroladores de baixo consumo daqui a dez anos.

---

## Contato & Chaves Públicas

- **Website / Notas Técnicas**: `https://jonasfalk.dev`
- **E-mail**: `jonas [at] jonasfalk.dev`
- **Matrix**: `@jonas:matrix.org`
- **Fingerprint GPG**: `7E9B 4410 82C9 52A1 D84F  2F0A 1B83 99C0 411E 32A5`
