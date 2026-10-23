---
layout: default
title: ライセンス表記
description: LYR (Android 画面翻訳アプリ) が利用しているオープンソースソフトウェア、フォント、機械学習モデルのライセンスと帰属表示。
---

# ライセンス表記

**最終更新日**: 2026-XX-XX (Audio モードの音声認識をサーバーへ移し、端末内の音声認識モデルと sherpa-onnx の配布をやめたことを反映。サーバー側で使用するモデルを参考として追記し、以前の版で配布していた音声認識モデルの帰属表示は「以前の版に含まれていたもの」へ移動)
**対象**: LYR (Android 画面翻訳アプリ)

本サービスは、以下のソフトウェア・フォント・機械学習モデルを利用しています。各項目の著作権は
それぞれの権利者に帰属します。ここに掲げるライセンスの条件に従って利用しています。

---

## 1. ソフトウェアライブラリ

| 名称 | ライセンス | 出典 |
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

## 3. 文字認識 (OCR) などの端末内モデル

**PaddleOCR (PP-OCRv5)**
検出・認識・角度分類の各モデルは PaddleOCR に由来します。一部の認識モデル（縦書きなど）は、
PaddleOCR のモデルをもとに本サービスが追加で学習したものです。
ライセンス: Apache License 2.0 / 出典: [PaddlePaddle/PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)

**吹き出し検出モデル**
マンガの吹き出しを検出するモデルは、YOLOX-Nano の構成をもとに、本サービスが合成データのみで
学習したものです。
YOLOX のライセンス: Apache License 2.0 / 出典: [Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
【要確認: YOLOX の事前学習済み重み・ソースコードを使ったか（使っていなければ、構成の参照だけで帰属表示は不要。この段落を残すかを決める）】

上記以外の端末内のモデル（文字領域の追跡など）は、本サービスが独自に設計・学習したものです。

## 4. 音声認識 (ASR)

Audio モードの音声認識は、**開発者が運用するサーバーで行います**。現在のアプリには
音声認識モデルは含まれていません（送信される情報についてはプライバシーポリシーをご確認ください）。

サーバーでは次のモデル・ソフトウェアを使用しています。これらはアプリとして配布するものでは
ありませんが、参考として記載します。

| 名称 | ライセンス | 出典 |
|---|---|---|
| Whisper large-v3 (OpenAI) | MIT License | [openai/whisper](https://github.com/openai/whisper) |
| faster-whisper | MIT License | [SYSTRAN/faster-whisper](https://github.com/SYSTRAN/faster-whisper) |
| CTranslate2 | MIT License | [OpenNMT/CTranslate2](https://github.com/OpenNMT/CTranslate2) |

## 5. 翻訳

翻訳は、開発者が運用するサーバー上の翻訳モデル、または外部の翻訳 API で行います。
サーバー上の翻訳モデルは、Qwen3.6-27B (Alibaba Cloud Qwen チーム) の一部を入力の読み取りに使い、
訳文を生成する部分を本サービスが独自に学習したものです。アプリとして配布するものではありませんが、
参考として記載します。
Qwen のライセンス: Apache License 2.0【要確認: Qwen3.6-27B のモデルカードのライセンス表記を一次情報で確認】 / 出典: [Qwen](https://huggingface.co/Qwen)

---

## 帰属表示 (Attribution)

現在のアプリに含まれるもののうち、Creative Commons Attribution ライセンスに基づくものはありません。

### 以前の版に含まれていたもの

以前の版のアプリ（versionCode 5〜8、バージョン 0.2.0〜0.2.3 のテスト配布版）【要確認: 端末内の音声認識を
使っていた版の範囲】では、Audio モードの音声認識を端末内で行っており、次の音声認識モデルを
端末へダウンロードして使用していました。これらの版をお持ちの方のために、帰属表示を残します。

| 対応言語 | モデル | ライセンス | 出典 |
|---|---|---|---|
| 日本語 | 本サービスが独自に学習 | — | 学習データ: [ReazonSpeech](https://research.reazon.jp/projects/ReazonSpeech/) |
| 英語 | NVIDIA NeMo FastConformer | **CC BY 4.0** | [nvidia/stt_en_fastconformer_hybrid_large_streaming_multi](https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi) |
| 韓国語 | 本サービスが独自に学習 | — | 学習データ: [YODAS](https://huggingface.co/datasets/espnet/yodas) (**CC BY 3.0**) |
| ポルトガル語 | 本サービスが独自に学習 | — | 学習データ: [YODAS2](https://huggingface.co/datasets/espnet/yodas2) (**CC BY 3.0**) |

日本語モデルは本サービスが独自に学習・保有するものです。学習にあたっては
日本国著作権法第30条の4 (著作物に表現された思想又は感情の享受を目的としない利用) に
基づき情報解析の用に供しています。

韓国語モデルとポルトガル語モデルも本サービスが独自に学習・保有するものですが、
学習データである YODAS / YODAS2 が CC BY 3.0 で提供されているため、
下記のとおり帰属表示を行います。
また、韓国語・ポルトガル語モデルの学習では雑音への強さを高めるために MUSAN コーパスを
用いています。MUSAN は CC BY 4.0 で提供されているため、同じく帰属表示を行います。
これらの版では、音声認識の実行に sherpa-onnx (Apache License 2.0、[k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx)) を使用していました。

#### 英語 音声認識モデル

- **著作者**: NVIDIA Corporation
- **名称**: `stt_en_fastconformer_hybrid_large_streaming_multi`
- **出典**: <https://huggingface.co/nvidia/stt_en_fastconformer_hybrid_large_streaming_multi>
- **ライセンス**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **変更の有無**: 本サービスでは、上記モデルを ONNX 形式へ変換し、int8 量子化を施したものを
  利用していました。モデルの重み自体に学習等の変更は加えていません。

#### 韓国語 音声認識モデルの学習データ

- **著作者**: Xinjian Li ほか (YODAS)
- **名称**: YODAS (`ko000` = 人手字幕サブセット)
- **出典**: <https://huggingface.co/datasets/espnet/yodas>
- **ライセンス**: [Creative Commons Attribution 3.0 (CC BY 3.0)](https://creativecommons.org/licenses/by/3.0/)
- **変更の有無**: 本サービスでは、上記データセットを音声認識モデルの学習に利用しました
  (データセットそのものは再配布していません)。学習して得られたモデルは本サービスが
  保有するものです。

#### ポルトガル語 音声認識モデルの学習データ

- **著作者**: Xinjian Li ほか (YODAS)
- **名称**: YODAS2 (`pt000` = 人手字幕サブセット)
- **出典**: <https://huggingface.co/datasets/espnet/yodas2>
- **ライセンス**: [Creative Commons Attribution 3.0 (CC BY 3.0)](https://creativecommons.org/licenses/by/3.0/)
- **変更の有無**: 本サービスでは、上記データセットを音声認識モデルの学習に利用しました
  (データセットそのものは再配布していません)。学習して得られたモデルは本サービスが
  保有するものです。

#### 韓国語・ポルトガル語 音声認識モデルの学習に用いた雑音データ

- **著作者**: David Snyder, Guoguo Chen, Daniel Povey
- **名称**: MUSAN: A Music, Speech, and Noise Corpus (arXiv:1510.08484)
- **出典**: <https://www.openslr.org/17/>
- **ライセンス**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **変更の有無**: 本サービスでは、上記コーパスのうち雑音 (noise) を学習時の雑音重畳に
  利用しました (コーパスそのものは再配布していません)。

---

## お問い合わせ

本ページの記載内容について誤り・不足がありましたら、下記までご連絡ください。
速やかに確認し、必要に応じて修正します。

[hello@lyr.jp](mailto:hello@lyr.jp)
