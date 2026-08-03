---
layout: default
lang: en
title: Privacy Policy
description: Privacy Policy for LYR, an Android screen translation app — what we collect, why, who we share it with, and how long we keep it.
---

# Privacy Policy

**Last updated**: 2026-08-03 (Reorganized the disclosures on transfers outside Japan; documented the handling terms agreed with the translation API provider and the Zero Data Retention setting. Includes the countries where inference servers are located, a caution about information visible on your screen, how to request disclosure and where to file complaints, security measures, and the scope of Accessibility Service use.)  
**Brand / App name**: LYR (the "Service")  
**Developer**: Kento Nakai (individual developer, the "Developer")  
**Contact**: [hello@lyr.jp](mailto:hello@lyr.jp)

> **This is a translation.** The Japanese version of this Privacy Policy is the original. If there is any discrepancy between the two, [the Japanese version](../privacy.html) prevails.

---

## 1. Introduction

This Privacy Policy explains how LYR (the "Service") handles your information. By using the Service, you are deemed to have agreed to this Policy.

**Where the Service is offered**: The Service is offered to users in the countries and regions the Developer has selected for distribution on Google Play. **It is not offered in the European Economic Area (EEA), the United Kingdom, Türkiye, Russia, mainland China, Vietnam, or Indonesia.** Use from those regions is not contemplated, and the Service is not offered or advertised to users there.

---

## 2. Information We Collect and Why

The Service is a screen translation app that runs on your Android device. It processes only the following information.

### 2.1 Screen captures

- **Purpose**: To extract the text to be translated via OCR (optical character recognition)
- **How it is processed**: At the moment you run a translation, a screenshot is taken using Android's MediaProjection API and processed **entirely on your device**
- **External transmission**: The image itself is never transmitted outside your device
- **No continuous recording**: A capture is taken only at the moment you run a translation. However, please be sure to read section 2.2 regarding transmission of the **text** read from it

### 2.2 Text extracted by OCR

- **Purpose**: Input to the translation API
- **How it is processed**: The text extracted from your screen is sent over HTTPS to a translation service, by way of a relay server operated by the Developer (Cloudflare Workers)
- **What is sent**: The **text that was displayed on your screen** at the moment you ran the translation, together with the device identifier described below
- **Device identifier**: To prevent abuse and excessive requests, a random per-device identifier (UUID) is sent. It is generated on first launch and stored within the app; it is unrelated to any hardware ID, advertising ID, or account information. **It is lost when you uninstall the app, and a different value is generated if you reinstall.**

> ### ⚠️ About the information visible on your screen (important)
>
> The Service **reads the text displayed on your screen without distinguishing between kinds of text**.
> Accordingly, if **names, contact details, addresses, account information, descriptions relating to
> health, or similar information** happened to be on screen when you ran a translation, that
> information is also sent to the translation service as text to be translated.
>
> Likewise, if you translate a screen such as a messaging app, it may contain **information about
> people other than yourself** (for example, the person you are talking with).
>
> The Developer does not use such information for any purpose other than translation and does not
> store it on any server. Even so, **please do not run a translation on screens showing sensitive
> information or the personal information of others.** If you do translate information about other
> people, you are responsible for confirming that doing so is appropriate.

### 2.3 Local settings

The following are stored only in DataStore / SharedPreferences on your device and are not transmitted externally.

- Source and target language settings
- Theme setting (light / dark)
- Translation counters (reset daily)
- Package names of share-target apps (only those you select)

Token usage and plan type (free / paid) are stored on your device, but **are also transmitted in aggregate form as part of the usage data** (see section 3.2).

---

## 3. Disclosure to Third Parties / Transfers Outside Japan

### 3.1 Transfers outside Japan for translation processing (disclosure)

Text extracted by OCR is sent for translation by way of a relay server operated by the Developer (Cloudflare Workers). There are two processing routes, and **which one is used is determined automatically based on the type of processing (manga, live subtitles, full page, and so on) and on server availability**. You cannot choose between them.

On either route, **only the text to be translated is sent**. **The device identifier is consumed at the relay server and is sent to neither route.**

| Item | **(a) External LLM API service** (processing entrusted to a service provider) | **(b) Inference servers operated by the Developer** |
|---|---|---|
| **Recipient** | An LLM API provider located in the United States. **The provider's name will be disclosed on request to the contact address at the end of this Policy.** It may change without notice based on quality, speed, cost, and similar considerations | **The Developer.** Translation content is not handed to a third party; it is processed on servers the Developer rents |
| **Country of the recipient** | **United States** | One of **Taiwan, the United States, Canada, or Japan.** We switch among these depending on speed, cost, and availability. **If we add a country beyond this set, we will update this Policy in advance** |
| **Data transferred** | Only the **text to be translated**, extracted from the screen by OCR | Same as at left |
| **Data not transferred** | Device identifier, screen images, account information, usage data | Same as at left |
| **Purpose of transfer** | Solely to obtain the translation result | Same as at left |
| **Timing of transfer** | Each time you run a translation | Same as at left |
| **Method of transfer** | API communication encrypted with HTTPS (TLS) | Same as at left |
| **Retention and use period** | Until translation processing completes. **Discarded afterwards and not stored** | Same as at left |
| **Data protection regime of the recipient country** | None of the countries above is recognized as having a level of protection equivalent to Japan's (as the EU and the UK are). For an overview of each country's regime, please refer to the [survey of foreign personal information protection systems](https://www.ppc.go.jp/personalinfo/legal/kaiseihogohou/#gaikoku) published by Japan's Personal Information Protection Commission | Same as at left |
| **Measures taken at the recipient** | Communications are encrypted with HTTPS (TLS) and what is sent is limited to the text to be translated. In addition, our contract with the provider (data processing terms) confirms the following — that **the text we send will not be used to train or tune AI models**; that it will not be used or retained beyond what is necessary to provide the service; that security measures including encryption at rest and in transit and multi-factor authentication are in place, along with third-party audit (SOC 2 Type II); that a list of sub-processors is published and prior notice is given before additions; that we will be notified **within 72 hours** in the event of a breach; and that we may request deletion of data on termination. Furthermore, the Developer has **enabled Zero Data Retention**, so **inputs and outputs are not stored by the provider** | In addition to the encryption above, the servers are configured with **authentication so that only the Developer can access them** |

**If you do not want these transfers**: Sending text for translation is the core function of the Service, so the Service cannot be used without it. If you do not want these transfers, please refrain from using the Service. Note that "3.2 Usage Data" and "3.3 Crash Reports" are separate from translation and **can each be turned off individually from the settings screen**.

If there is a material change, we will update the "Last updated" date of this Policy to notify you.

### 3.2 Usage data (analytics)

To improve the quality of the Service, we collect and transmit the **usage data** listed below. It does not include information that directly identifies you personally, such as your name, email address, phone number, contacts, or precise location.

However, this is not "anonymized data" — it is **pseudonymized data linked to a random identifier assigned per app installation**. Activity within the same installation can be correlated.

Data transmitted:

- Translation latency (processing time), and the mean and 95th percentile of OCR processing time
- Whether the response could be served from cache
- How often each mode (Page / Box / Live / manual) is used, and switches between them
- How often features such as copy and horizontal fling are used, and the number of characters copied (the text itself is not sent)
- Counts of translation failures by type (ECHO / WRONG_LANG / DUPLICATION / network error / limit reached / other)
- Retry counts and retry rate
- How often each language pair occurs (for example, English → Japanese), and the quality tier label for that pair
- The number of text blocks recognized in a single translation
- Identifiers for the model and route that handled the translation (whether it was processed on our own servers or an external API)
- Plan type in use (free / paid), and how many times the free tier limit was reached
- The grant / deny outcome of permission requests (overlay, screen capture, notifications, and so on)
- A record of detection when the text recognition engine takes abnormally long to initialize
- Input and output token counts for translation requests, and the approximate cost calculated from them
- Per-session duration and subtitle display count for real-time translation (Live), and a breakdown of the stage at which processing ended (no screen change, no text detected, translation timeout, and so on)
- The number of times the paid plan screen was shown, the outcome there (purchase / later / left the screen), and how many seconds it was displayed
- Information automatically added by Firebase Analytics: a random identifier per app installation, the originating IP address (used by Google to estimate approximate country and region), device model, OS version, app version, language setting, and basic events such as app launch and session start

**What is not transmitted**: Text read by OCR, translation results, and screen content or images are **never included** in telemetry (everything above consists of counts, durations, success/failure, and similar aggregates).

Recipients:

- Firebase Analytics, provided by Google LLC (United States)
- Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)
- The telemetry above is also stored per event in Google BigQuery (Google Cloud, United States) managed by the Developer, for analysis (see "4. Retention Periods" for how long)

**Opt-out**: You can stop the transmissions described in this section at any time by turning off the switch at Settings → "Info & Privacy" → "Usage Data" in the Service. When it is off, nothing in this section is transmitted, including the automatic collection described above.

### 3.3 Crash reports

When the app terminates abnormally or an unexpected error occurs, the following information is sent to **Firebase Crashlytics** (United States), provided by Google LLC, in order to identify the cause.

- The stack trace at the time of the crash (a record of the execution point inside the program)
- Technical information such as device model, OS version, app version, and memory state
- A random identifier generated by Crashlytics per app installation

**Text read by OCR, translation results, and screen content are not included.**

- Privacy policy: [https://policies.google.com/privacy](https://policies.google.com/privacy)

**Opt-out**: You can stop the transmissions described in this section at any time by turning off the switch at Settings → "Info & Privacy" → "Crash Reports" in the Service. This is a separate switch from "3.2 Usage Data"; each can be toggled independently.

### 3.4 Other

We do not provide information to any third parties other than those listed in 3.1 through 3.3. We do not use advertising networks.

---

## 4. Retention Periods

- **Screen captures**: Discarded from memory immediately after translation processing ends
- **OCR text / translation results**: Stored in an on-device translation cache (keyed by MD5 hash) and deleted completely when you uninstall the app
- **Server-side storage**: The relay server operated by the Developer (Cloudflare Workers) stores **only usage counters**. The device identifier and originating IP address are hashed and used as counter keys; the original values are not stored. **Text to be translated and translation results are not stored on the server**
- **Counter retention**: Counters are aggregated per minute and per day and are overwritten when the period rolls over. They are not accumulated as a usage history
- **Retention of usage data / crash reports**: Data transmitted under 3.2 and 3.3 is stored in Firebase and in Google BigQuery (United States) managed by the Developer. Event-level data is retained for **up to 14 months**, and data past that limit is deleted on a rolling basis. However, statistics aggregated so that individual events cannot be identified (such as daily usage counts and average processing times) may be retained beyond that limit. None of this includes OCR text, translation results, or screen content. If you turn off "Usage Data" or "Crash Reports" in settings, the corresponding data is no longer transmitted from then on

---

## 5. Permissions

The Service uses the following permissions.

| Permission | Purpose |
|---|---|
| `SYSTEM_ALERT_WINDOW` | Displaying translation results as an overlay |
| `FOREGROUND_SERVICE` / `FOREGROUND_SERVICE_MEDIA_PROJECTION` | Running screen capture as a resident service |
| `POST_NOTIFICATIONS` | Displaying the foreground service notification |
| `VIBRATE` | Haptic feedback for interactions |
| `INTERNET` / `ACCESS_NETWORK_STATE` | Sending translation requests to the translation API and checking connectivity |
| `WAKE_LOCK` | Preventing processing from being interrupted during real-time translation |
| Accessibility Service | Detecting scroll stop, identifying the foreground app, and locating the main content area in browsers (see section 6; text content is not read) |

---

## 6. About Our Use of Accessibility Service

The Service uses Accessibility Service for only the following three purposes.

- **Detecting when scrolling stops** (deciding when to run a translation)
- **Identifying the foreground app** (deciding whether the screen being translated has changed)
- **Locating the main content area in browsers** (to exclude the address bar and navigation areas from translation)

Technically, we enable the permission that allows retrieving screen information (`canRetrieveWindowContent`). This is because, under Android's design, **this permission is required even just to learn the name of the foreground app** (window information does not carry the app name directly; it can only be obtained by way of screen elements).

However, **what we actually reference is only the app's package name, the type of screen elements, and their position on screen** — **we do not read the text content on your screen or your input**. We also do not grant the permission to perform touch gestures (`canPerformGestures`).

---

## 7. Age Requirement

The Service is not intended for use by anyone **under the age of 13**. If you are under 13, please use the Service with the consent of a parent or guardian, or refrain from using it.

---

## 8. Deleting and Exporting Data

All on-device data (translation cache and settings) is deleted when you uninstall the app. Text to be translated and translation results are not stored on either the relay server or the translation service.

By contrast, the data transmitted under "3.2 Usage Data" and "3.3 Crash Reports" remains in Firebase and in Google BigQuery managed by the Developer for a limited period (see "4. Retention Periods"). This is statistical data linked to a random per-installation identifier, and **the Developer has no means of connecting it to you personally**. For that reason, we may be unable to act on requests to delete specific data. If you want to stop future transmissions, please turn them off from the settings screen.

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

- **Encryption in transit**: All communications among the app, the relay server, and the translation service are encrypted with HTTPS (TLS)
- **Access control**: Access to the relay server and the inference servers is limited to the Developer. Credentials are not embedded in the app and are managed server-side
- **Minimizing storage**: Text to be translated and translation results are not stored on servers and are discarded once processing completes. The device identifier and originating IP address are hashed and used only for aggregating usage counts; the original values are not stored
- **Protecting on-device data**: The translation cache and settings are stored inside Android's app sandbox and cannot be read by other apps. The translation cache, settings, and device identifier are excluded from device backup and device-to-device transfer
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
