---
layout: default
lang: en
title: Open Source Licenses
description: Licenses and attribution for the open source software, fonts, and machine learning models used in LYR (a translation app for Android and iOS).
---

# Open Source Licenses

**Last updated**: 2026-10-27 (Reflects adding Firebase Analytics and RevenueCat to the iOS version, and adds the list for the iOS version to "1. Software libraries")
**Applies to**: LYR (Android and iOS). In addition to frameworks provided by Apple, the iOS app uses the libraries listed under "iOS" in 1. The server-side models in 4 and 5 are shared by both versions

LYR uses the software, fonts, and machine learning models listed below. Copyright in each
remains with its respective holder, and we use each item under the terms of its license.

---

## 1. Software libraries

### Android

| Name | License | Source |
|---|---|---|
| ONNX Runtime | MIT License | [microsoft/onnxruntime](https://github.com/microsoft/onnxruntime) |
| OkHttp | Apache License 2.0 | [square/okhttp](https://github.com/square/okhttp) |
| Gson | Apache License 2.0 | [google/gson](https://github.com/google/gson) |
| ICU4J | Unicode License | [unicode-org/icu](https://github.com/unicode-org/icu) |
| AndroidX / Jetpack Compose / Media3 | Apache License 2.0 | [Android Open Source Project](https://source.android.com/) |
| Kotlin / kotlinx.coroutines | Apache License 2.0 | [JetBrains/kotlin](https://github.com/JetBrains/kotlin) |
| Okio | Apache License 2.0 | [square/okio](https://github.com/square/okio) |
| Guava | Apache License 2.0 | [google/guava](https://github.com/google/guava) |
| Checker Framework (annotations) | MIT License | [typetools/checker-framework](https://github.com/typetools/checker-framework) |
| Error Prone (annotations) | Apache License 2.0 | [google/error-prone](https://github.com/google/error-prone) |
| J2ObjC (annotations) | Apache License 2.0 | [google/j2objc](https://github.com/google/j2objc) |
| JSR 305 (annotations) | Apache License 2.0 | [findbugsproject/findbugs](https://github.com/findbugsproject/findbugs) |
| javax.inject | Apache License 2.0 | [javax-inject/javax-inject](https://github.com/javax-inject/javax-inject) |

### iOS

| Name | License | Source |
|---|---|---|
| Firebase Apple SDK (FirebaseCore / FirebaseCoreInternal / FirebaseInstallations / FirebaseAnalytics) | Apache License 2.0 | [firebase/firebase-ios-sdk](https://github.com/firebase/firebase-ios-sdk) |
| GoogleUtilities | Apache License 2.0 | [google/GoogleUtilities](https://github.com/google/GoogleUtilities) |
| Promises (FBLPromises) | Apache License 2.0 | [google/promises](https://github.com/google/promises) |
| nanopb | zlib License | [nanopb/nanopb](https://github.com/nanopb/nanopb) |
| RevenueCat (purchases-ios) | MIT License | [RevenueCat/purchases-ios](https://github.com/RevenueCat/purchases-ios) |

Google App Measurement (the measurement part of Firebase Analytics) is distributed as a binary and is
used under the [Google APIs Terms of Service](https://developers.google.com/terms).
Full text of the Apache License 2.0: <https://www.apache.org/licenses/LICENSE-2.0>

### Common

In addition to the above, the app includes components provided under the Apache License 2.0 as
transitive dependencies of these libraries. Please contact us if you need the individual names
and full license texts.

Google Play services, Firebase and the Google Play Billing Library are used under the
[Google APIs Terms of Service](https://developers.google.com/terms) and the terms of each
service.

## 2. Fonts

| Name | License | Source |
|---|---|---|
| Bangers | SIL Open Font License 1.1 | [googlefonts/bangers](https://github.com/googlefonts/bangers) |
| Comic Neue | SIL Open Font License 1.1 | [crozynski/comicneue](https://github.com/crozynski/comicneue) |

The full license texts are bundled with the app.

## 3. On-device models, including optical character recognition (OCR)

**PaddleOCR (PP-OCRv5)**
The detection, recognition and angle classification models derive from PaddleOCR. Some
recognition models (for example, for vertical text) were further trained by us starting from
PaddleOCR models.
License: Apache License 2.0 / Source: [PaddlePaddle/PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)

**Speech bubble detection model**
The model that detects speech bubbles in manga was further trained by us on synthetic data only,
using the YOLOX training source code and starting from the pretrained YOLOX-Nano weights.
YOLOX license: Apache License 2.0 / Source: [Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)

Other on-device models (for example, for tracking text regions) were designed and trained by us.

## 4. Speech recognition (ASR)

Speech recognition for Audio mode **runs on servers operated by the Developer**. The current
app does not contain any speech recognition model (see the Privacy Policy for what is sent).

The servers use the following models and software. They are not distributed as part of the app,
but are listed for reference.

| Name | License | Source |
|---|---|---|
| Whisper large-v3 (OpenAI) | MIT License | [openai/whisper](https://github.com/openai/whisper) |
| faster-whisper | MIT License | [SYSTRAN/faster-whisper](https://github.com/SYSTRAN/faster-whisper) |
| CTranslate2 | MIT License | [OpenNMT/CTranslate2](https://github.com/OpenNMT/CTranslate2) |

## 5. Translation

Translation is performed either by a translation model on servers operated by the Developer or by
an external translation API. The server-side translation model uses part of Qwen3.6-27B (Qwen team,
Alibaba Cloud) to read the input, with the part that generates translations trained by us. It is
not distributed as part of the app, but is listed for reference.
Qwen license: Apache License 2.0 / Source: [Qwen/Qwen3.6-27B](https://huggingface.co/Qwen/Qwen3.6-27B)

---

## Attribution

The current app contains no components licensed under Creative Commons Attribution.

### Included in earlier versions

Earlier versions of the app (versionCode 5–8, versions 0.2.0–0.2.3, distributed for testing) performed speech recognition for
Audio mode on the device, downloading and using the speech recognition models below. We keep the
attribution for anyone who still has those versions.

| Language | Model | License | Source |
|---|---|---|---|
| Japanese | Trained and owned by us | — | Training data: [ReazonSpeech](https://research.reazon.jp/projects/ReazonSpeech/) |
| English | NVIDIA NeMo FastConformer | **CC BY 4.0** | [nvidia/stt_en_fastconformer_hybrid_large_streaming_multi](https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi) |
| Korean | Trained and owned by us | — | Training data: [YODAS](https://huggingface.co/datasets/espnet/yodas) (**CC BY 3.0**) |
| Portuguese | Trained and owned by us | — | Training data: [YODAS2](https://huggingface.co/datasets/espnet/yodas2) (**CC BY 3.0**) |

The Japanese model is trained and owned by us. Training was carried out as information
analysis under Article 30-4 of the Japanese Copyright Act (use not intended for the
enjoyment of the thoughts or sentiments expressed in the work).

The Korean and Portuguese models are likewise trained and owned by us. Because their
training data (YODAS / YODAS2) is distributed under CC BY 3.0, attribution is given below.
The Korean and Portuguese models were also trained with the MUSAN corpus for noise
robustness. MUSAN is distributed under CC BY 4.0, so it is likewise credited below.
Those versions used sherpa-onnx (Apache License 2.0, [k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx)) to run recognition.

#### English speech recognition model

- **Author**: NVIDIA Corporation
- **Title**: `stt_en_fastconformer_hybrid_large_streaming_multi`
- **Source**: <https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi>
- **License**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **Changes**: We converted the model to ONNX format and applied int8 quantization.
  No changes were made to the model weights themselves.

#### Training data for the Korean speech recognition model

- **Author**: Xinjian Li et al. (YODAS)
- **Title**: YODAS (`ko000` = manual-caption subset)
- **Source**: <https://huggingface.co/datasets/espnet/yodas>
- **License**: [Creative Commons Attribution 3.0 (CC BY 3.0)](https://creativecommons.org/licenses/by/3.0/)
- **Changes**: We used this dataset to train a speech recognition model. The dataset itself
  is not redistributed. The resulting model is owned by us.

#### Training data for the Portuguese speech recognition model

- **Author**: Xinjian Li et al. (YODAS)
- **Title**: YODAS2 (`pt000` = manual-caption subset)
- **Source**: <https://huggingface.co/datasets/espnet/yodas2>
- **License**: [Creative Commons Attribution 3.0 (CC BY 3.0)](https://creativecommons.org/licenses/by/3.0/)
- **Changes**: We used this dataset to train a speech recognition model. The dataset itself
  is not redistributed. The resulting model is owned by us.

#### Noise data used to train the Korean and Portuguese speech recognition models

- **Author**: David Snyder, Guoguo Chen, Daniel Povey
- **Title**: MUSAN: A Music, Speech, and Noise Corpus (arXiv:1510.08484)
- **Source**: <https://www.openslr.org/17/>
- **License**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **Changes**: We used the noise portion of this corpus for noise augmentation during
  training. The corpus itself is not redistributed.

---

## Contact

If you find an error or omission on this page, please let us know and we will review and
correct it promptly.

[hello@lyr.jp](mailto:hello@lyr.jp)
