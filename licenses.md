---
layout: default
title: ライセンス表記
description: LYR (Android 画面翻訳アプリ) が利用しているオープンソースソフトウェア、フォント、機械学習モデルのライセンスと帰属表示。
---

# ライセンス表記

**最終更新日**: 2026-08-06
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
| LiteRT (TensorFlow Lite) | Apache License 2.0 | [google-ai-edge/LiteRT](https://github.com/google-ai-edge/LiteRT) |
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

Google ML Kit、Google Play サービス、Firebase、Google Play Billing Library は、
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

**日本語**
本サービスが独自に学習・保有するモデルです。第三者のライセンス条件の対象となる
構成要素は含まれていません。

---

## 帰属表示 (Attribution)

上記のうち、Creative Commons Attribution ライセンスのデータセットに由来するものについては、
以下に出典を明示します。

（現時点で該当なし）

---

## お問い合わせ

本ページの記載内容について誤り・不足がありましたら、下記までご連絡ください。
速やかに確認し、必要に応じて修正します。

[hello@lyr.jp](mailto:hello@lyr.jp)
