<div align="center">

  <img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/6.x/svgs/solid/bolt-lightning.svg" width="64" height="64" alt="SnapFlow Logo" />

  # ⚡ SnapFlow
  ### The Ultimate All-in-One 4K Media Downloader, Status Saver & Offline Music Player

  [![Flutter](https://img.shields.io/badge/Flutter-3.22+-02569B?logo=flutter&logoColor=white)](https://flutter.dev)
  [![Dart](https://img.shields.io/badge/Dart-3.4+-0175C2?logo=dart&logoColor=white)](https://dart.dev)
  [![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)](https://www.android.com)
  [![Version](https://img.shields.io/badge/Release-v1.0.0-8B5CF6)](https://github.com)
  [![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
  [![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)](CONTRIBUTING.md)

  <p align="center">
    <strong>SnapFlow</strong> is a high-performance, ad-free Android media discovery and background download suite built with Flutter, SQLite, and native Android platform services. It replaces 5+ separate apps by combining multi-platform 4K video downloads, WhatsApp status saving, and an offline music studio into a seamless AMOLED-ready dark interface.
  </p>

  <p align="center">
    <a href="#-key-features">Key Features</a> •
    <a href="#-tech-stack">Tech Stack</a> •
    <a href="#-getting-started">Getting Started</a> •
    <a href="#-how-to-build-apk">Build APK</a> •
    <a href="#-disclaimer">Disclaimer</a>
  </p>

</div>

---

## 🚀 Key Features

### 🎥 1. Multi-Platform 4K Video Downloader
- **Instagram**: One-tap downloads for Reels, Stories, and Carousels in original 1080p resolution.
- **TikTok**: Clean watermark-free HD downloads directly to your device storage.
- **Facebook**: Instant extraction of HD/SD progressive streams from Watch, Reels, and public posts.
- **YouTube**: Multi-stream extraction ranging from 4K (2160p), 2K, 1080p Full HD down to lightweight 360p.
- **Twitter / X**: Instant video resolution via high-speed API fallback.

### 🟢 2. WhatsApp & WA Business Status Saver
- **Dual Support**: Automatically detects media from both standard WhatsApp and WhatsApp Business.
- **Zero Compression**: Saves photos and videos in their original clarity directly to your gallery.
- **Smart Scanner**: Auto-indexes newly viewed statuses with batch-save functionality.

### 🎵 3. Studio MP3 Extractor & Offline Music Player
- **Direct Audio Extraction**: Converts any video stream into crystal-clear 320kbps MP3 audio.
- **Full Offline Music Player**: Built-in background audio player with lock-screen media controls, playlists, and album art support.
- **Sleep Timer**: Auto-pause audio playback whenever you fall asleep.

### 🌐 4. Private In-App Browser & Smart Sniffer
- **Automated Stream Detection**: Detects video and audio feeds in real-time as you browse.
- **Ad-Shield Engine**: Built-in ad-blocking filters that block trackers and popups.
- **Zero Tracking**: Clean private sessions with no browsing history leaks.

### ⚡ 5. Resumable Concurrency Download Manager
- **Multi-Threaded Queue**: Download multiple files concurrently with full priority control.
- **Network Resiliency**: Automatic pause & resume on connection drops with Wi-Fi only mode option.
- **Rich Notifications**: Native Android notification actions (Pause, Resume, Cancel) with live speed meters.

---

## 🛠️ Tech Stack & Architecture

SnapFlow follows **Feature-First Clean Architecture** with strict modularity:

| Domain | Technology / Package |
|---|---|
| **Framework** | [Flutter](https://flutter.dev) (Dart 3.4+) |
| **State Management** | [Riverpod 2.5](https://riverpod.dev) |
| **Navigation & Routing** | [GoRouter](https://pub.dev/packages/go_router) |
| **HTTP & Networking** | [Dio](https://pub.dev/packages/dio) with custom mobile client headers |
| **Local Database** | [SQLite](https://pub.dev/packages/sqflite) with DAOs and indexed queries |
| **Audio Processing** | [JustAudio](https://pub.dev/packages/just_audio) & [AudioSession](https://pub.dev/packages/audio_session) |
| **In-App WebView** | [webview_flutter](https://pub.dev/packages/webview_flutter) |
| **YouTube Pipeline** | [YoutubeExplode Dart](https://pub.dev/packages/youtube_explode_dart) |
| **Native Notifications** | [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications) |

---

## 📂 Project Structure

```text
lib/
├── app/                  # App initialization, routing, theme, and typography
├── core/
│   ├── database/         # SQLite database management & schemas
│   ├── network/          # Dio client configurations & interceptors
│   ├── notifications/    # Foreground & background notification channels
│   ├── services/         # Download service, Media resolver, Audio player
│   ├── storage/          # Scoped storage & media library sync
│   └── utils/            # Validators, sanitizers, and formatters
├── features/
│   ├── browser/          # In-app browser with background media sniffing
│   ├── downloader/       # Interactive download dialog & format selection
│   ├── downloads/        # Active tasks & download history dashboard
│   ├── home/             # URL input, clipboard detection & quick shortcuts
│   ├── music_player/     # Offline audio player, playlists & full modal
│   └── status_saver/     # WhatsApp status storage watcher & gallery
└── shared/               # Cross-cutting data models & base entities
