---
layout: default
lang: en
title: Privacy Policy
description: Privacy Policy for LYR, a translation app for Android and iOS — what we collect, why, who we share it with, and how long we keep it.
---

# Privacy Policy

**Last updated**: 2026-10-26 (Revised for the launch of the iOS version. Main changes: 1 and 2 add the iOS version / 2.1, 2.2, 2.5, 3.2, 3.3 and 6 are marked as Android only / 2.3 adds how the iOS version captures audio, its recent-subtitle context and device identifier / 2.4 adds what the iOS version keeps on the device, including its activity log / 3.1 adds the route used by the iOS version / 3.5 adds paid-plan purchases (Google Play and App Store) / 4, 8 and 8-3 add how the iOS version is handled (the device identifier and activity log are excluded from backups) / 5 splits permissions into Android and iOS / 3.5 adds feedback and inquiries (the iOS version receives them by email) and 4 adds how long we keep them)
**Brand / App name**: LYR (the "Service")  
**Developer**: Kento Nakai (individual developer, the "Developer")  
**Contact**: [hello@lyr.jp](mailto:hello@lyr.jp)

> **This is a translation.** The Japanese version of this Privacy Policy is the original. If there is any discrepancy between the two, [the Japanese version](../privacy.html) prevails.

---

## 1. Introduction

This Privacy Policy explains how LYR (the "Service") handles your information. In addition to the app (Android and iOS versions), this Policy also applies to the early-tester application form on the website lyr.jp (see 2.6). By using the Service, you are deemed to have agreed to this Policy.

**Where the Service is offered**: The Service is offered to users in the countries and regions the Developer has selected for distribution on Google Play and the App Store. **It is not offered in the European Economic Area (EEA), the United Kingdom, Switzerland, Türkiye, Russia, mainland China, Vietnam, or Indonesia.** Use from those regions is not contemplated, and the Service is not offered or advertised to users there.

---

## 2. Information We Collect and Why

The Service is a translation app that runs on Android devices and on iOS devices (iPhone). **The iOS version offers audio translation only (Audio mode, see 2.3)** and has no features that read text on the screen (2.1, 2.2). It processes only the following information.

### 2.1 Screen captures (Android only)

- **Purpose**: To extract the text to be translated via OCR (optical character recognition)
- **How it is processed**: At the moment you run a translation (and, in real-time translation (Live), at regular intervals while it is running), a screenshot is taken using Android's MediaProjection API and processed **entirely on your device**
- **External transmission**: The image itself is never transmitted outside your device
- **No continuous recording**: Captures are taken only while a translation is running. However, please be sure to read section 2.2 regarding transmission of the **text** read from it

### 2.2 Text extracted by OCR, and recent translation history (Android only)

- **Purpose**: Input to translation processing
- **How it is processed**: The text extracted from your screen is sent over HTTPS for translation (see 3.1), by way of a relay server operated by the Developer (Cloudflare Workers). **However, in real-time translation (Live), when the title glossary (see 2.5) is available, the subtitle text is sent directly to the inference servers operated by the Developer (route (b) in 3.1).** In that case the same pass as in 2.3 is sent along with it (the recent history is not sent)
- **What is sent**: The **text that was displayed on your screen** at the moment you ran the translation, together with the device identifier described below
- **Recent translation history (context)**: To keep subjects and names translated consistently, in manga, real-time translation (Live) and audio translation (Audio) we send **the source text you translated just before, together with its translation**, along with the new text. This covers up to the 3 most recent items in Live and Audio, and up to 5 speech bubbles from the previous page in manga. It is not sent for full-page translation (Page). In manga, when route (a) is used, no history is sent on the paid plan. In manga, the on-screen positions of the speech bubbles are also sent. The history is kept only in memory on your device and is discarded when you stop translating or switch modes or languages. In addition, if there is a gap of more than about 5 seconds in Live, about 30 seconds in Audio, or about 2 minutes in manga, the older history is discarded when the next item is added. It is never stored on any server
- **Device identifier**: To prevent abuse and excessive requests, a random per-device identifier (UUID) is sent. It is generated on first launch and stored within the app; it is unrelated to any hardware ID, advertising ID, or account information. **It is lost when you uninstall the app, and a different value is generated if you reinstall.** When you purchase the paid plan, a hash of this identifier is attached to the Google Play purchase record to prevent fraudulent reuse of purchases (this hash is passed to Google LLC (United States), but the Developer never learns your Google account)

> ### ⚠️ About the information visible on your screen (important)
>
> The Service **reads the text displayed on your screen without distinguishing between kinds of text**.
> Accordingly, if **names, contact details, addresses, account information, descriptions relating to
> health, or similar information** happened to be on screen when you ran a translation, that
> information is also sent for translation as text to be translated. As part of the history described
> above, **it may be sent again with the next translation**.
>
> Likewise, if you translate a screen such as a messaging app, it may contain **information about
> people other than yourself** (for example, the person you are talking with).
>
> The Developer does not use such information for any purpose other than translation and does not
> store it on any server. Even so, **please do not run a translation on screens showing sensitive
> information or the personal information of others.** If you do translate information about other
> people, you are responsible for confirming that doing so is appropriate.

### 2.3 Audio being played (Audio mode; Android and iOS)

Collected only when you use Audio mode.

- **Purpose**: Extracting text for translation via speech recognition
- **What is captured**: **Audio being played on your device**
  - **Android**: We use Android's AudioPlaybackCapture API to capture sound played by other apps
  - **iOS**: We use iOS screen recording (a ReplayKit Broadcast Upload Extension) to receive sound played by other apps.
    Recording happens only when you start it from the iOS screen-recording controls, and while it is running iOS shows a recording indicator at the top of the screen.
    Screen recording also hands the screen video to the app, but the Service **discards the video as soon as it is received and never processes, stores, or sends it**

- **We do not use the microphone**: Microphone audio is never used for translation, stored, or transmitted
  - **Android**: We declare the `RECORD_AUDIO` permission, but only because Android requires it
    for the playback capture described above. **It is not used for microphone input**
  - **iOS**: The app does not ask for microphone permission. Even if you turn the microphone on in the screen-recording
    controls, **microphone audio is discarded without being used, stored, or transmitted**

- **How it is processed (the audio is sent off your device)**: Speech recognition runs on
  **an inference server operated by the Developer**. The app splits the audio into stretches
  of speech (roughly 1 to 5 seconds each); each segment is encrypted with HTTPS (TLS), sent to
  the server, and the recognized text is returned. The audio reaches the inference server
  by way of the network of Cloudflare, Inc. (a tunnel connection)

- **Translation after recognition**:
  - **Android**: Normally performed on the same inference server, using the
    same recent history as in 2.2 (recognized source text and its translation, up to 3 items).
    If the inference server cannot translate, the **recognized text** (not the audio) is sent
    to route (a) in 3.1 for translation
  - **iOS**: Recognition and translation are both performed on the same inference server. To keep translations consistent,
    **up to 2 recent subtitles (source text and translation)** are sent together with the new audio, along with the source and target
    languages, the translation instructions, and the pass (see below). This history is kept only in
    memory on your device and is discarded **when you stop recording or switch languages**; it is never stored on the server.
    **The iOS version does not use route (a) in 3.1** (if the inference server is unavailable, no subtitles are shown)

- **Also recognize English (iOS setting)**: When turned on, the inference server decides for each segment whether it is in the
  language you selected or in English. No additional information is sent for this (only the same audio, together with the
  instructions for translating it if it turns out to be English)

- **Countries it is sent to**: **Taiwan, the United States, Canada, Japan, or a member state of the European Union (EU).** See "3.1"
  for how it is handled in each country and the safeguards we apply

- **Retention**: **Audio is not stored.** On the server it is held only in memory and
  discarded as soon as recognition finishes. It is never written out as a file
  (this applies to the distributed versions — Google Play, App Store, and TestFlight. Only development builds that the Developer runs on
  their own devices have a feature that saves audio on the device for troubleshooting)

- **Device identifier**: To prevent abuse, the app sends a device identifier (on Android, the same one as in 2.2; on iOS, see below)
  to the relay server, which issues a **short-lived pass (valid for 20 minutes)**. The pass
  contains the device identifier and is sent to the inference server together with the audio,
  but the inference server uses it **only to check that the pass is valid** and **does not record it**
  - **Device identifier on iOS**: A random per-installation identifier (UUID), generated the first time you start recording and stored
    within the Service's storage. **It is unrelated to any hardware ID, advertising ID, or Apple Account, and is lost when you delete the app**.
    It is excluded from iCloud and other backups and from device-to-device transfer (the same treatment as on Android)

- **When offline**: Because speech recognition runs on the server, **Audio mode cannot be
  used without a network connection, or while the inference server is down**

> ### ⚠️ About the audio you play (important)
>
> Audio mode treats **all audio played on your device** as input for recognition. If you
> play a call, or a recording that contains other people's speech, **that audio itself**
> is sent to the server for recognition, and text generated from it is translated.
>
> **Please do not use Audio mode with sensitive content, or with audio containing other
> people's speech.** If you translate someone else's voice, you are responsible for
> confirming that doing so is permitted (including any consent required for recording
> and translation).

### 2.4 Local settings and on-device activity log

**Android**: The following are stored only in DataStore / SharedPreferences on your device and are not transmitted externally.

- Source and target language settings
- Theme setting (light / dark)
- Translation and usage-time counters (reset daily)
- Package names of share-target apps (only those you select)

Token usage and plan type (free / paid) are stored on your device, but **are also transmitted in aggregate form as part of the usage data** (see section 3.2).

**iOS**: The following are stored on your device (within the Service's storage). The source and target languages are also included in translation requests (see 2.3); nothing else here is transmitted externally.

- Source and target languages, how the original text is shown, and the "Also recognize English" setting
- A record that you agreed to the first-run explanation
- Time used on the free plan today (reset daily)
- **Activity log**: Operational information such as when recording started and stopped, whether subtitles could be shown,
  processing times, the audio format, and the recognized language and its probability. **It does not include audio, recognized
  text, or translation results.** The Developer never sees it unless you choose to provide it. See section 4 for how long it is kept. The activity log is excluded from iCloud and other backups

### 2.5 Title of the content being played (Android only; optional; only if you enable notification access)

Used in Audio mode and real-time translation (Live) to translate proper nouns such as people's
names correctly. Collected **only if you grant the Service "Notification access" in Android's
settings.** The Service works without it, and nothing is collected if you do not grant it.

- **What is collected**: Only the **title and channel (creator) name** that video and music apps
  publish to Android while playing. **The content of your notifications is not read**

- **Where it is sent**: The relay server (Cloudflare Workers). Only the title, channel name and the
  translation language pair are sent — **the device identifier is not sent** (the relay server is
  configured to reject such requests if they carry a device identifier)

- **How it is used**: The relay server extracts candidate words such as names from the title (using
  an external LLM API — the same provider as route (a) in 3.1), looks those words up through the
  public APIs of Wikipedia and Wikidata (both Wikimedia Foundation, United States), and builds a glossary of proper
  nouns. The inference server consults this glossary when translating

- **Retention**: The title and channel name are stored temporarily on the relay server (Cloudflare)
  to build the glossary and are deleted automatically **within 6 hours at most**. The mapping between
  words extracted from titles and the matching Wikipedia articles is kept for up to 21 days, because it
  is reused when building glossaries for other users. Separately, to understand which words are
  commonly needed, we keep **daily counts per language** of the words extracted from titles for up to
  60 days. None of these is linked to the device identifier or IP address

### 2.6 Early tester recruitment (application form on the website lyr.jp)

To recruit early testers for the Service, the application form on the website (lyr.jp) accepts the following information. It is not required to use the app.

- **Information collected**: Your email address (the one for the Google account you will use to join the Google Play test), the date and time of your application, the language of the page you applied from, the country estimated from your connection, information showing which ad or link brought you to the form (UTM parameters: source, medium, campaign name, and ad content), and, if you choose to answer, "what you want to translate" and "the main languages you want to translate"
- **Purposes**:
  - Inviting you to the test and contacting you as needed for the test (how to join, your coupon code, requests for feedback, and notice that the test has ended)
  - Registering you for the Google Play closed test (your email address is added to the tester list in Google Play Console)
  - Aggregation to learn which ads and links bring the most applications, and which uses and languages are in demand (handled as counts per campaign and per answer; not used for ad delivery or any other purpose)
- **Preventing repeated submissions**: To prevent many applications in a short time from the same connection, the originating IP address is hashed and used only to count the number of applications
- **Capacity and waiting list**: The number of early testers is limited. Applications beyond that limit are kept on a waiting list so that we can contact you about the next round
- **Linking with the app**: Application information is not used in combination with the app's device identifier or with the content of your translations (linking them through the coupon code is technically possible, but it is not used for anything other than running the test). The table matching the coupon codes sent to testers with their email addresses is kept in the same Google Sheet as the applicant list (see 3.4) and is accessible only under the Developer's account
- **What we do not send**: We do not send unsolicited promotional email. Links in our emails do not contain any mechanism for tracking opens or clicks

---

## 3. Disclosure to Third Parties / Transfers Outside Japan

### 3.1 Transfers outside Japan for translation processing (disclosure)

Text extracted by OCR is sent for translation by way of a relay server operated by the Developer (Cloudflare Workers). There are two processing routes, and **which one is used is determined automatically based on the type of processing (manga, live subtitles, audio, full page, and so on), the language pair, and server availability**. You cannot choose between them.

Currently, **full-page translation (Page) uses (a)**. **Manga, real-time translation (Live) and audio translation (Audio) use (b) first**, and are translated **via (a)** when (b) is down or overloaded, or when (b) does not support the language pair. This allocation may change without notice based on quality, speed, and cost.
**The iOS version uses only (b) and never uses (a)** (see 2.3).

**On Android**, on either route, what is sent is the **text to be translated and the recent history described in 2.2** (except for the direct Live sending described below, which does not include the history).
**In Audio mode only, the audio itself and the pass (see 2.3) are additionally sent to the inference server in (b).**
**In Live, when the title glossary (see 2.5) is available, the subtitle text and the pass are sent directly to (b) without going through the relay server** (see 2.2).
Otherwise, **the device identifier is consumed at the relay server and is sent to neither route.**

**On iOS**, what is sent to (b) is **the stretches of device playback audio identified as speech, up to 2 recent subtitles (source text and translation), the source and target languages with the translation instructions, and the pass** (see 2.3). Recognized text is produced on the inference server, so it is not sent from the device.

| Item | **(a) External LLM API service** (processing entrusted to a service provider) | **(b) Inference servers operated by the Developer** (processing entrusted to a service provider) |
|---|---|---|
| **Recipient** | An LLM API provider located in the United States. **The provider's name will be disclosed on request to the contact address at the end of this Policy.** It may change without notice based on quality, speed, cost, and similar considerations | The Developer runs translation and speech recognition models on servers rented from the cloud GPU provider **RunPod (Runpod, Inc., United States)**. Processing takes place in the server's memory. The rented servers are either in data centers contracted by RunPod (Secure Cloud) or on **machines owned by third-party businesses or individuals vetted by RunPod** (Community Cloud); in the latter case, the machine's owner has physical access to it. We therefore treat (b) as a provision to third parties in a foreign country (the provider and the machine owners) as well (the provider may change based on quality, speed, cost, and similar considerations, in which case we will update this Policy) |
| **Country of the recipient** | **United States** | One of **Taiwan, the United States, Canada, Japan, or a member state of the European Union (EU).** We switch among these depending on speed, cost, and availability (servers outside this set are automatically refused at startup). **If we add a country beyond this set, we will update this Policy in advance** |
| **Data transferred** | (Android only) The **text to be translated** extracted from the screen by OCR, and the **recent history** (2.2). In Audio mode when (b) is unavailable, the **recognized text** and the recent history | Android: same as at left. **In Audio mode, additionally the stretches of device playback audio identified as speech, and the pass** (see "2.3"). In the Live case described above, the subtitle text and the pass. **iOS: the stretches of audio identified as speech, up to 2 recent subtitles, the source and target languages with the translation instructions, and the pass** |
| **Data not transferred** | Device identifier, screen images, audio, account information, usage data | Screen images, account information, usage data (the device identifier only as contained in the pass in Audio mode and in the Live case described above) |
| **Purpose of transfer** | Solely to obtain the translation result | Solely to obtain the translation result (in Audio mode, speech recognition and translation) |
| **Timing of transfer** | Each time you run a translation | Same as at left. In Audio mode, once per stretch of speech |
| **Method of transfer** | API communication encrypted with HTTPS (TLS) | Same as at left (by way of Cloudflare's network) |
| **Retention and use period** | Until translation processing completes. **Discarded afterwards and not stored** | Same as at left. **Audio likewise is discarded from memory as soon as recognition finishes and is not stored as a file** |
| **Data protection regime of the recipient country** | The country above is not recognized as having a level of protection equivalent to Japan's (as the EU and the UK are). For an overview of each country's regime, please refer to the [survey of foreign personal information protection systems](https://www.ppc.go.jp/personalinfo/legal/kaiseihogohou/#gaikoku) published by Japan's Personal Information Protection Commission | Taiwan, the United States, and Canada are not recognized as having a level of protection equivalent to Japan's. **EU member states are recognized as having an equivalent level.** For an overview of each country's regime, see the survey at left |
| **Measures taken at the recipient** | Communications are encrypted with HTTPS (TLS) and what is sent is limited to the text to be translated and the recent history. In addition, our contract with the provider (data processing terms) confirms the following — that **the text we send will not be used to train or tune AI models**; that it will not be used or retained beyond what is necessary to provide the service; that security measures including encryption at rest and in transit and multi-factor authentication are in place, along with third-party audit (SOC 2 Type II); that a list of sub-processors is published and prior notice is given before additions; that we will be notified **within 72 hours** in the event of a breach; and that we may request deletion of data on termination. Furthermore, the Developer has **enabled Zero Data Retention**, so **inputs and outputs are not stored by the provider** | In addition to the encryption above, the servers are configured with **authentication so that only the Developer can access them**. RunPod's terms of service prohibit machine owners from inspecting or analyzing data inside customers' servers (this is a contractual rule, not a technical guarantee). Audio and text are **handled only in the server's memory and are not stored as files**. The servers' operational logs are also configured **not to retain the text to be translated, translation results, audio, or speech recognition results** — only operational information such as language, number of lines, audio duration and processing time (see 4) |

**Legal basis (your consent)**: Provision to (a) and (b) is made based on your consent, after presenting the information above (the recipient country, its system for protecting personal information, and the measures taken at the recipient). For audio translation (Audio), before you start using it, a confirmation screen (on iOS, the last page of the first-launch guide) tells you that audio is processed on servers that may be outside your country, and asks for your consent.

**About the relay server (Cloudflare)**: The relay server runs on the infrastructure of Cloudflare, Inc. (United States). Cloudflare only provides the infrastructure that relays and processes the communication and is not contracted to handle the content itself, so we do not treat this as a provision to Cloudflare. To keep communication with the inference servers fast, the relay server is configured to **run at Cloudflare locations near Japan (Tokyo)**. Usage counters (see 4) are stored at Cloudflare locations in the Asia-Pacific region or the United States (each counter stays where it was first created, and processing used to take place in the United States). Your device's connection, however, is received at the Cloudflare location nearest to you and reaches the relay server over Cloudflare's network.

**If you do not want these transfers**: Sending text for translation is the core function of the Service, so the Service cannot be used without it. If you do not want these transfers, please refrain from using the Service. Note that "3.2 Usage Data" and "3.3 Crash Reports" (Android) are separate from translation and **can each be turned off individually from the settings screen**. "2.5 Title of the content being played" is not sent if you do not grant (or you revoke) notification access.

If there is a material change, we will update the "Last updated" date of this Policy to notify you.

### 3.2 Usage data (analytics; Android only)

**The iOS version does not send this data** (it does not include Firebase).

To improve the quality of the Service, we collect and transmit the **usage data** listed below. It does not include information that directly identifies you personally, such as your name, email address, phone number, contacts, or precise location.

However, this is not "anonymized data" — it is **pseudonymized data linked to a random identifier assigned per app installation**. Activity within the same installation can be correlated.

Data transmitted:

- Translation latency (processing time), and the mean and 95th percentile of OCR processing time
- Whether the response could be served from cache
- How often each mode (Page / Manga / Live) is used, and switches between them
- Counts of translation failures by type (ECHO / WRONG_LANG / DUPLICATION / network error / limit reached / other)
- Retry counts and retry rate
- How often each language pair occurs (for example, English → Japanese), and the quality tier label for that pair; when the source language is detected automatically, the detected language
- The number of text blocks recognized in a single translation, and counts of structural problems such as a translation whose line count differs from the source or that came back empty
- Identifiers for the model and route that handled the translation (whether it was processed on our own servers or an external API, and the response status of our own servers)
- Plan type in use (free / paid), and how many times the free tier limit was reached
- The grant / deny outcome of permission requests (overlay, screen capture, accessibility)
- A record of detection when the text recognition engine takes abnormally long to initialize
- Input and output token counts for translation requests, and the approximate cost calculated from them
- Per-session duration and subtitle display count for real-time translation (Live), and a breakdown of the stage at which processing ended (no screen change, no text detected, translation timeout, and so on)
- For audio translation (Audio): whether starting succeeded, and per session the duration, number of speech segments, the number of segments whose subtitles were / were not shown and a breakdown of the reasons, processing speed, the share of silence, and whether it was stopped by the free allowance
- The number of times the paid plan screen was shown, the outcome there (purchase / later / left the screen), how many seconds it was displayed; whether a purchase succeeded and which plan (monthly / annual) was chosen; and, if a purchase failed, the reason code
- Whether a coupon code was applied successfully, and the end of its period (the code itself is not sent)
- Display of the how-to guide, and the items chosen in it
- Information automatically added by Firebase Analytics: a random identifier per app installation, the originating IP address (used by Google to estimate **approximate location, down to city level**; we do not obtain precise location such as from GPS), device model, device brand, screen resolution, OS version, app version, language setting, the app's install source, and basic events such as app launch and session start

**What is not transmitted**: Text read by OCR, audio, speech recognition results, translation results, screen content or images, the title of content being played, and the name of the foreground app are **never included** in telemetry (everything above consists of counts, durations, success/failure, and similar aggregates).

Recipients:

- Firebase Analytics, provided by Google LLC (United States)
- Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)
- The telemetry above is also stored per event in Google BigQuery (Google Cloud, United States) managed by the Developer, for analysis (see "4. Retention Periods" for how long)

**Opt-out**: You can stop the transmissions described in this section at any time by turning off the switch at Settings → "Info & Privacy" → "Usage Data" in the Service. When it is off, nothing in this section is transmitted, including the automatic collection described above.

### 3.3 Crash reports (Android only)

**The iOS version does not send these reports.** Crash information reaches the Developer through Apple only if you
have allowed "Share With App Developers" in iOS settings (subject to Apple's privacy policy).

When the app terminates abnormally or an unexpected error occurs, the following information is sent to **Firebase Crashlytics** (United States), provided by Google LLC, in order to identify the cause.

- The stack trace at the time of the crash (a record of the execution point inside the program)
- Technical information such as device model, OS version, app version, and memory state
- A random identifier generated by Crashlytics per app installation

**Text read by OCR, audio, translation results, and screen content are not included.**

- Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Opt-out**: You can stop the transmissions described in this section at any time by turning off the switch at Settings → "Info & Privacy" → "Crash Reports" in the Service. This is a separate switch from "3.2 Usage Data"; each can be toggled independently.

### 3.4 Where early-tester application data is held

The application information in 2.6 is stored and processed on the services of the following providers. All are managed under the Developer's own accounts and are not used for any other purpose.

- **Google LLC (United States)**: The list of applicants and the coupon code table (Google Sheets) and sending email (Google Workspace); registering testers for Google Play (Google Play Console), and the list file used for that registration (Google Drive)
- **Cloudflare, Inc. (United States)**: Receiving submissions from the application form (Cloudflare Workers); a copy of each received application (temporary storage so that no application is lost)

### 3.5 Other

**Paid-plan purchases**: On Android the paid plan is purchased on Google Play (Google LLC (United States)); on iOS, on the App Store
(Apple Inc. (United States)). Payments are handled by each store. On iOS, purchases are verified on the device using the purchase
record issued by Apple, and **the device identifier is not attached to the purchase record** (for Android, see the end of 2.2).

**Feedback and inquiries**:
- **Feedback form (such as from the Android app's settings screen)**: We receive it through Google Forms (Google LLC (United States)). What is sent is the content you enter yourself, along with the app version, device model, OS version, and display language. The "Contact" field is optional; if you fill it in, we use it only to contact you to ask more about your feedback
- **Email (Send feedback in the iOS app's settings screen, and inquiries from our website)**: We receive these by email to hello@lyr.jp. In the iOS app, the app version, device model, OS version, and display language are added to the end of the email body in advance, and you can review or delete them before sending. Email is received through Google Workspace (Google LLC (United States))
- We use the email addresses, contact details and content you send us only to reply to you, to investigate problems, and to improve the Service

We do not provide information to any third parties other than those listed in 2.5 and 3.1 through 3.5. We do not use advertising networks and do not collect the advertising ID.

The relay server (Cloudflare Workers) and the network that carries audio run on the infrastructure of Cloudflare, Inc. (United States), and communications pass through its network.

---

## 4. Retention Periods

- **Screen captures (Android)**: Discarded from memory immediately after translation processing ends (on iOS, screen video is discarded as soon as it is received; see 2.3)
- **Audio (Audio mode)**: In the distributed versions, held **only in memory** on both the device and the server, and discarded as soon as recognition finishes. It is **never written out as a file** on either (when compressing audio on the device to reduce data usage, a temporary file may be created in the app's private storage; it is deleted as soon as compression finishes, before sending)
- **OCR text / translation results (Android)**: Kept only in a translation cache **in memory** on your device and discarded when the app's process ends. **They are not saved as files** (from version 0.3.13; cache files created by earlier versions are deleted the first time you use translation after updating)
- **Recent translation history**: Kept only in memory on your device. On Android it is discarded when you stop translating or switch modes or languages (for how gaps are handled, see 2.2); on iOS it is discarded when you stop recording or switch languages (see 2.3)
- **Server-side storage**: The relay server operated by the Developer (Cloudflare Workers) stores **only usage counters**. The device identifier and originating IP address are hashed and used as counter keys; the original values are not stored. **Text to be translated and translation results are not stored on the server**
- **Inference server operational logs**: We record **only operational information** such as language, number of lines, processing time, audio duration, and whether an error occurred. **Audio, recognized text, text to be translated, and translation results are not recorded.** These logs contain no device identifier and are not in a form that can be linked to an individual user. Per-request records are overwritten oldest-first once they exceed a fixed size (100 MB × 2 generations). They are not taken off the server and are deleted when the server is decommissioned
- **Relay server operational logs**: A feature of the relay server's provider (Cloudflare) keeps the error and status messages output by the Developer for about 10% of requests, for up to 7 days. **The device identifier, originating IP address, text to be translated, and translation results are not logged**
- **Title of the content being played**: Up to 6 hours on the relay server (see 2.5). Mapping between extracted words and articles: up to 21 days. Daily per-language counts of extracted words: up to 60 days
- **Feedback and inquiries (see 3.5)**: Deleted one year after we finish handling them (so that we can check the history if the same problem is reported again). If you would like them deleted, please contact us at any time at the address at the end of this Policy
- **Early-tester application information (see 2.6)**: Deleted 90 days after the test ends. The waiting list is kept until the end of the next recruitment round and then deleted. The copies of received applications (Cloudflare) are deleted automatically after 60 days. If you would like your information deleted, please contact us at any time at the address at the end of this Policy (we will also remove you from the tester list in Google Play Console)
- **On-device activity log (iOS, see 2.4)**: **The 10 most recent sessions** (one per app launch) are kept; older ones are deleted automatically when the app starts
- **Counter retention**: Counters are aggregated counts per fixed period (1 minute, 1 hour, 1 day) and contain neither translation content nor records of individual uses
- **Retention of usage data / crash reports (Android)**: Data transmitted under 3.2 and 3.3 is stored in Firebase and in Google BigQuery (United States) managed by the Developer. Event-level data is retained for **up to 14 months**, and data past that limit is deleted on a rolling basis. However, statistics aggregated so that individual events cannot be identified (such as daily usage counts and average processing times) may be retained beyond that limit. None of this includes OCR text, translation results, or screen content. If you turn off "Usage Data" or "Crash Reports" in settings, the corresponding data is no longer transmitted from then on

---

## 5. Permissions

The Service uses the following permissions and features.

### Android

| Permission | Purpose |
|---|---|
| `SYSTEM_ALERT_WINDOW` | Displaying translation results, subtitles and control buttons as an overlay |
| `FOREGROUND_SERVICE` / `FOREGROUND_SERVICE_MEDIA_PROJECTION` | Capturing the screen and playback audio as a resident service while translation is running |
| `POST_NOTIFICATIONS` | Displaying the notification that shows the service is running |
| `VIBRATE` | Haptic feedback for interactions |
| `INTERNET` / `ACCESS_NETWORK_STATE` | Sending translation and speech recognition requests and checking connectivity |
| `RECORD_AUDIO` | **Capturing device playback audio in Audio mode.** Android requires this permission for AudioPlaybackCapture. **It is not used for microphone recording** (see "2.3") |
| `com.android.vending.BILLING` | Purchasing the paid plan on Google Play |
| Quick Settings tile (optional) | To start translation from the Quick Settings panel (only if you add the tile) |
| Accessibility Service | Detecting scroll stop, identifying the foreground app, and locating the main content area in browsers and similar apps (see section 6; text on the screen is not read) |
| Notification access (Notification Listener) | **Optional.** Obtaining the title and channel name of the content being played (see 2.5; the content of notifications is not read). The app introduces this feature on first use and on the settings screen, but you grant the permission yourself in Android's settings, and you can revoke it at any time. The Service works without it |

In addition, the libraries we use (Firebase and Google Play services) declare permissions such as `WAKE_LOCK` for scheduling data transmission and similar purposes.

### iOS

| Feature | Purpose |
|---|---|
| Screen recording (Broadcast Upload Extension) | Receiving sound played by other apps (see 2.3). You start and stop it from iOS. Screen video and microphone audio are discarded as soon as they are received |
| Picture in Picture | Showing subtitles on top of other apps. Subtitles are drawn on the device |
| Background audio | Keeping the Service running while subtitles are shown in Picture in Picture. **It neither plays nor records sound** |
| In-App Purchase (StoreKit) | Purchasing the paid plan on the App Store (see 3.5) |

The app does not ask for access to the microphone, camera, photos, location, contacts, or notifications.

---

## 6. About Our Use of Accessibility Service (Android only)

The Service uses Accessibility Service for only the following three purposes.

- **Detecting when scrolling stops** (deciding when to run a translation)
- **Identifying the foreground app** (deciding whether the screen being translated has changed)
- **Locating the main content area in browsers and similar apps** (to exclude the address bar and navigation areas from translation)

Technically, we enable the permission that allows retrieving screen information (`canRetrieveWindowContent`). This is because, under Android's design, **this permission is required even just to learn the name of the foreground app** (window information does not carry the app name directly; it can only be obtained by way of screen elements).

However, **what we actually reference is only the foreground app's package name, and the type, on-screen position and size of the component that displays web pages (WebView)** — **we do not read the text content on your screen or your input**. The package name and positions are used only on your device and are **neither stored nor transmitted** (the foreground app's package name is also used on your device to match the content title described in 2.5). We also do not grant the permission to perform touch gestures (`canPerformGestures`).

---

## 7. Age Requirement

The Service is not intended for use by anyone **under the age of 13** (**under the age of 14 if you are in South Korea**). If this applies to you, please use the Service with the consent of a parent or guardian, or refrain from using it.

---

## 8. Deleting and Exporting Data

All on-device data (translation cache and settings, and the iOS activity log and device identifier) is deleted when you uninstall the app. Because the device identifier and activity log are excluded from backups, restoring from a backup does not bring them back. Text to be translated, translation results, and audio are not stored on the relay server, the inference servers, or the translation service. Titles of content being played are deleted automatically once the period in section 4 has passed.

By contrast, the data transmitted under "3.2 Usage Data" and "3.3 Crash Reports" (Android) remains in Firebase and in Google BigQuery managed by the Developer for a limited period (see "4. Retention Periods"). This is statistical data linked to a random per-installation identifier, and **the Developer has no means of connecting it to you personally**. For that reason, we may be unable to act on requests to delete specific data. If you want to stop future transmissions, please turn them off from the settings screen.

---

## 8-2. Your Rights (Requests for Disclosure and Similar)

You may request **notification of the purpose of use, disclosure, correction, addition, deletion, suspension of use, erasure, and disclosure of records of third-party provision** with respect to information about you held by the Developer. There is no charge.

- **How to request**: Please email the contact address at the end of this Policy
- **Identity verification**: We will respond to the extent we can confirm the correspondence between the request and you

Note that the data transmitted under "3.2 Usage Data" and "3.3 Crash Reports" is **statistical data linked to a random per-installation identifier**, and the Developer has no means of connecting it to you personally. Accordingly, for that data we **may be unable to identify you and may be unable to act on individual requests**. If you want to stop future transmissions, you can turn them off from the settings screen at any time.

### Where to file complaints

In addition to the contact address above, complaints about how the Service handles personal information may be filed with the **Personal Information Protection Commission** of Japan ([https://www.ppc.go.jp/](https://www.ppc.go.jp/)).

### Information about the Developer

The Developer's name is stated at the top of this Policy. The address will be provided without delay on request to the contact address above.

---

## 8-3. Security Measures

The Developer takes the following security measures for the information it handles.

- **Encryption in transit**: All communications among the app, the relay server, the inference servers, and the translation service are encrypted with HTTPS (TLS)
- **Access control**: Access to the relay server and the inference servers is limited to the Developer. Credentials for the external translation service and the inference servers are not embedded in the app and are managed server-side. Connecting to the inference server in Audio mode requires a short-lived pass issued by the relay server
- **Minimizing storage**: Text to be translated, translation results, and audio are not stored on servers and are discarded once processing completes, and they are not written to server logs either. The device identifier and originating IP address are hashed and used only for aggregating usage counts; the original values are not stored
- **Protecting on-device data**: The translation cache and settings are stored inside Android's app sandbox and cannot be read by other apps. The translation cache, the device identifier, and coupon records are excluded from device backup and device-to-device transfer (settings such as languages are included).
  On iOS, settings, the activity log, and the device identifier are stored inside the app's sandbox and cannot be read by other apps.
  On iOS as well, the device identifier and the activity log are excluded from iCloud and other backups and from device-to-device transfer (settings such as languages are included).
- **Handling outside Japan**: The same measures apply when processing takes place in the countries listed in section 3.1

---

## 9. Changes to This Policy

This Policy may be revised as needed. If there is a material change, we will notify you through an in-app notice or by updating the "Last updated" date at the top of this Policy.

---

## 10. Contact

For questions about this Policy, please contact us at:

- **Email**: [hello@lyr.jp](mailto:hello@lyr.jp)

---

## 11. Governing Law

This Policy is governed by the laws of Japan.
