# 🥗 MacroProxy Architecture

Welcome to the **MacroProxy** engineering organization. This ecosystem contains a modular suite of open-source mobile packages and services designed to streamline multi-modal dietary logging.

MacroProxy operates as an **Input & Processing Engine**. It ingests physical inputs (barcodes, photos, voice notes), resolves metadata locally or via free open endpoints, corrects portion scaling mismatches, and exports clean natural-language payloads directly to system clipboards for target tracking apps (e.g., MacroFactor, Cronometer).

---

## 🏛 Ecosystem & Repository Matrix

This project uses a **Polyrepo / Modular Architecture** to keep functional boundaries explicit and allow independent package testing/updates.

| Repository | Role |
| :--- | :--- |
| [**`app-main`**](https://github.com/MacroProxy/app-main) | Orchestrates package pipelines, renders UI, handles portion scaling, writes clipboard strings. |
| [**`pkg-vision`**](https://github.com/MacroProxy/pkg-vision) | Multi-label food classification executing locally via quantized computer vision models. |
| [**`pkg-speech`**](https://github.com/MacroProxy/pkg-speech) | Native speech recognition wrapper with custom portion keyword and multiplier parsing. |
| [**`pkg-barcode`**](https://github.com/MacroProxy/pkg-barcode) | High-speed, 60fps on-device barcode string extraction (UPC-A / EAN-13). |
| [**`pkg-openfood`**](https://github.com/MacroProxy/pkg-openfood) | Asynchronous client for Open Food Facts REST endpoints. |

---

## 🔄 Data & Program Pipeline

TODO: Add flowchart or something

---

## 🧪 Package Integration (`pubspec.yaml`)

Individual `pkg-*` modules can be imported into external Flutter projects independently:

```yaml
dependencies:
  pkg_vision:
    git:
      url: [https://github.com/MacroProxy/pkg-vision.git](https://github.com/MacroProxy/pkg-vision.git)
      ref: main

  pkg_speech:
    git:
      url: [https://github.com/MacroProxy/pkg-speech.git](https://github.com/MacroProxy/pkg-speech.git)
      ref: main

  pkg_barcode:
    git:
      url: [https://github.com/MacroProxy/pkg-barcode.git](https://github.com/MacroProxy/pkg-barcode.git)
      ref: main

  pkg_openfood:
    git:
      url: [https://github.com/MacroProxy/pkg-openfood.git](https://github.com/MacroProxy/pkg-openfood.git)
      ref: main

```
