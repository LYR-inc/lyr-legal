---
layout: default
lang: en
title: Open Source Licenses
description: Licenses and attribution for the open source software, fonts, and machine learning models used in LYR (Android screen translation app).
---

# Open Source Licenses

**Last updated**: 2026-08-06
**Applies to**: LYR (Android screen translation app)

LYR uses the software, fonts, and machine learning models listed below. Copyright in each
remains with its respective holder, and we use each item under the terms of its license.

Model files downloaded after first launch are also covered by this page.

---

## 1. Software libraries

| Name | License | Source |
|---|---|---|
| ONNX Runtime | MIT License | [microsoft/onnxruntime](https://github.com/microsoft/onnxruntime) |
| sherpa-onnx | Apache License 2.0 | [k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) |
| OkHttp | Apache License 2.0 | [square/okhttp](https://github.com/square/okhttp) |
| Gson | Apache License 2.0 | [google/gson](https://github.com/google/gson) |
| ICU4J | Unicode License | [unicode-org/icu](https://github.com/unicode-org/icu) |
| LiteRT (TensorFlow Lite) | Apache License 2.0 | [google-ai-edge/LiteRT](https://github.com/google-ai-edge/LiteRT) |
| AndroidX / Jetpack Compose | Apache License 2.0 | [Android Open Source Project](https://source.android.com/) |
| Kotlin / kotlinx.coroutines | Apache License 2.0 | [JetBrains/kotlin](https://github.com/JetBrains/kotlin) |

Google ML Kit, Google Play services, Firebase and the Google Play Billing Library are used
under the [Google APIs Terms of Service](https://developers.google.com/terms) and the terms
of each service.

## 2. Fonts

| Name | License | Source |
|---|---|---|
| Bangers | SIL Open Font License 1.1 | [googlefonts/bangers](https://github.com/googlefonts/bangers) |
| Comic Neue | SIL Open Font License 1.1 | [crozynski/comicneue](https://github.com/crozynski/comicneue) |

The full license texts are bundled with the app.

## 3. Optical character recognition (OCR) models

**PaddleOCR (PP-OCRv5)**
The detection, recognition and angle classification models derive from PaddleOCR.
License: Apache License 2.0 / Source: [PaddlePaddle/PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)

**Manga OCR**
Downloaded by the app on first use. The upstream model
[kha-white/manga-ocr-base](https://huggingface.co/kha-white/manga-ocr-base) is published under
the Apache License 2.0; we use its ONNX conversion
[l0wgear/manga-ocr-2025-onnx](https://huggingface.co/l0wgear/manga-ocr-2025-onnx).

## 4. Automatic speech recognition (ASR) models

**Japanese**
Trained and owned by us. It contains no components subject to third-party license terms.

---

## Attribution

For any component derived from a dataset under a Creative Commons Attribution license, the
source is credited below.

(None at present)

---

## Contact

If you find an error or omission on this page, please let us know and we will review and
correct it promptly.

[hello@lyr.jp](mailto:hello@lyr.jp)
