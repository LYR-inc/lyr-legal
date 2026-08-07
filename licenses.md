---
layout: default
title: ライセンス表記
description: LYR (Android 画面翻訳アプリ) が利用しているオープンソースソフトウェア、フォント、機械学習モデルのライセンスと帰属表示。
---

# ライセンス表記

**最終更新日**: 2026-08-08
**対象**: LYR (Android 画面翻訳アプリ)

本サービスは、以下のソフトウェア・フォント・機械学習モデルを利用しています。各項目の著作権は
それぞれの権利者に帰属します。ここに掲げるライセンスの条件に従って利用しています。

---

## 1. ソフトウェアライブラリ

| 名称 | ライセンス | 出典 |
|---|---|---|
| ONNX Runtime | MIT License | [microsoft/onnxruntime](https://github.com/microsoft/onnxruntime) |
| sherpa-onnx | Apache License 2.0 | [k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) |
| OkHttp | Apache License 2.0 | [square/okhttp](https://github.com/square/okhttp) |
| Gson | Apache License 2.0 | [google/gson](https://github.com/google/gson) |
| ICU4J | Unicode License | [unicode-org/icu](https://github.com/unicode-org/icu) |
| AndroidX / Jetpack Compose | Apache License 2.0 | [Android Open Source Project](https://source.android.com/) |
| Kotlin / kotlinx.coroutines | Apache License 2.0 | [JetBrains/kotlin](https://github.com/JetBrains/kotlin) |
| Okio | Apache License 2.0 | [square/okio](https://github.com/square/okio) |
| Guava | Apache License 2.0 | [google/guava](https://github.com/google/guava) |
| Checker Framework (annotations) | MIT License | [typetools/checker-framework](https://github.com/typetools/checker-framework) |
| Error Prone (annotations) | Apache License 2.0 | [google/error-prone](https://github.com/google/error-prone) |
| J2ObjC (annotations) | Apache License 2.0 | [google/j2objc](https://github.com/google/j2objc) |
| JSR 305 (annotations) | Apache License 2.0 | [findbugsproject/findbugs](https://github.com/findbugsproject/findbugs) |
| javax.inject | Apache License 2.0 | [javax-inject/javax-inject](https://github.com/javax-inject/javax-inject) |

上記のほか、これらのライブラリが依存する形で Apache License 2.0 のもとで提供される
コンポーネントを含みます。個別の名称と全文が必要な場合はお問い合わせください。

Google Play サービス、Firebase、Google Play Billing Library は、
[Google API 利用規約](https://developers.google.com/terms) および各サービスの利用条件に
基づいて利用しています。

## 2. フォント

| 名称 | ライセンス | 出典 |
|---|---|---|
| Bangers | SIL Open Font License 1.1 | [googlefonts/bangers](https://github.com/googlefonts/bangers) |
| Comic Neue | SIL Open Font License 1.1 | [crozynski/comicneue](https://github.com/crozynski/comicneue) |

ライセンス全文はアプリに同梱しています。

## 3. 文字認識 (OCR) モデル

**PaddleOCR (PP-OCRv5)**
検出・認識・角度分類の各モデルは PaddleOCR に由来します。
ライセンス: Apache License 2.0 / 出典: [PaddlePaddle/PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)

## 4. 音声認識 (ASR) モデル

Audio モードで使用する音声認識モデルです。**認識処理は端末内で完結**します。

| 対応言語 | モデル | ライセンス | 出典 |
|---|---|---|---|
| 日本語 | 本サービスが独自に学習 | — | 学習データ: [ReazonSpeech](https://research.reazon.jp/projects/ReazonSpeech/) |
| 英語 | NVIDIA NeMo FastConformer | **CC BY 4.0** | [nvidia/stt_en_fastconformer_hybrid_large_streaming_multi](https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi) |

日本語モデルは本サービスが独自に学習・保有するものです。学習にあたっては
日本国著作権法第30条の4 (著作物に表現された思想又は感情の享受を目的としない利用) に
基づき情報解析の用に供しています。

---

## 帰属表示 (Attribution)

上記のうち、Creative Commons Attribution ライセンスに基づくものについて、
以下に出典と権利者を明示します。

### 英語 音声認識モデル

- **著作者**: NVIDIA Corporation
- **名称**: `stt_en_fastconformer_hybrid_large_streaming_multi`
- **出典**: <https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi>
- **ライセンス**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **変更の有無**: 本サービスでは、上記モデルを ONNX 形式へ変換し、int8 量子化を施したものを
  利用しています。モデルの重み自体に学習等の変更は加えていません。

---

## お問い合わせ

本ページの記載内容について誤り・不足がありましたら、下記までご連絡ください。
速やかに確認し、必要に応じて修正します。

[hello@lyr.jp](mailto:hello@lyr.jp)
