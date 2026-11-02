| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Jonas Falk

```text
Localisation : Göteborg, Suède (UTC+1 / UTC+2)
Domaine :      Systèmes à faible latence et traitement du signal numérique (DSP)
Technologies : Rust, C++ Moderne (C++20), Zig, Audio Linux Temps Réel
Activité :     Conception d'outils d'audio spatial et de télémétrie bioacoustique
```

---

## À Propos de Moi

Je suis ingénieur logiciel système, passionné par le point de rencontre entre l'acoustique, la géométrie spatiale et l'efficacité intrinsèque du matériel. Je consacre la majeure partie de mon temps à concevoir des algorithmes audio sans aucune allocation dynamique (zero-allocation), à agencer la mémoire pour l'exécution SIMD et à développer le micrologiciel de stations de surveillance acoustique solaires autonomes.

Lorsque je ne profile pas des files d'attente circulaires sans verrou (lock-free) ou que je ne mesure pas la distorsion de phase de filtres à l'oscilloscope, je parcours les archipels scandinaves pour enregistrer sur le terrain les chants d'oiseaux migrateurs, ou je restaure des magnétophones analogiques à bande magnétique.

- 🔭 Conception de graphes audio déterministes et non-bloquants en temps réel.
- ⚡ Optimisation de noyaux SIMD (AVX-512 et ARM NEON) pour la convolution d'impulsions acoustiques.
- ☕ Mû par des cafés d'origine unique à torréfaction claire et des chaînes de compilation reproductibles.

---

## Compétences Techniques & Outillage

| Domaine | Technologies Clés | Outils de Mesure & Analyse |
| :--- | :--- | :--- |
| **Systèmes & Temps Réel** | Rust, C++20, Zig, C (C11) | eBPF, Valgrind, perf, criterion.rs |
| **DSP Audio & Spatialisation** | Filtres HRTF, Ambisonie B-Format, Convoluteur SIMD | JACK Audio, ALSA, PortAudio, WebAudio |
| **Embarqué & Matériel** | STM32 (Cortex-M4/M7), ESP32-S3, KiCad | Codecs I2S, Analyseurs logiques, Oscilloscopes |
| **Environnement & Infra** | Arch Linux, NixOS, Alpine | Neovim, CMake, Ninja, Git, Docker |

---

## Projets Open Source Notables

### `solstice-dsp`
> *Bibliothèque de convolution audio spatiale header-first, exempte d'allocation sur le tas, écrite en Rust.*
- **Architecture Centrale** : Décodeur ambisonique B-format articulé autour d'une convolution FFT partitionnée par SIMD.
- **Garantie de Latence** : Moins de 1,2 ms de budget de traitement à 96 kHz pour des tampons de 64 échantillons sans allocation mémoire.
- **Cibles** : Bureau natif (Linux/macOS/Windows) et WebAssembly pour synthétiseurs audio web interactifs.

### `pulsefield`
> *Démon de télémétrie acoustique ultra-basse consommation destiné aux postes d'écoute écologique isolés.*
- **Intégration Matérielle** : Micrologiciel STM32 sur mesure communiquant par LTE-M / LoRaWAN avec sauvegarde sur carte SD en cas de panne réseau.
- **Compression** : Empaquetage adaptatif de trames FLAC spécialement calibré pour les transmissions intermittentes par énergie solaire.
- **Résilience** : Boucle de surveillance watchdog auto-réparatrice capable d'affronter les rigueurs de l'hiver nordique.

### `decibel-tui`
> *Analyseur de sonie en ligne de commande strictement conforme aux normes de diffusion ITU-R BS.1770-4 et EBU R128.*
- **Interface Utilisateur** : Interface terminal ratatui entièrement pilotable au clavier avec mesure True-Peak et calcul LUFS intégré en continu.
- **Accès Matériel** : Connexion directe aux sous-systèmes ALSA et CoreAudio sans transiter par les couches de mixage du bureau.

---

## Principes d'Ingénierie

1. **Chemins Critiques Déterministes** : Dans la boucle de traitement audio temps réel, il ne faut jamais allouer de mémoire, poser de verrous ni déclencher d'entrées/sorties non déterministes.
2. **Compréhension par les Premiers Principes** : Assimiler la hiérarchie des caches CPU, les cycles d'instructions et les limites du silicium avant d'empiler des niveaux d'abstraction.
3. **Pérennité Matérielle** : Écrire un code modulaire, aux dépendances réduites au strict minimum, capable de compiler et de tourner sans maintenance sur des puces basse consommation dans dix ans.

---

## Contact & Clés Publiques

- **Site Web / Notes Techniques** : `https://jonasfalk.dev`
- **Courriel** : `jonas [at] jonasfalk.dev`
- **Matrix** : `@jonas:matrix.org`
- **Empreinte GPG** : `7E9B 4410 82C9 52A1 D84F  2F0A 1B83 99C0 411E 32A5`
