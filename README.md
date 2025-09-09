# Musicy

![Screenshots](https://nexo.sh/posts/why-i-built-a-native-mp3-player-in-swiftui/frame_source.webp)

Musicy is an **offline-first** music player for iOS that enables full control of your personal MP3 library without relying on Apple Music or iTunes Match. Built with SwiftUI and structured using a layered MVVM + Actor-based architecture, Musicy prioritizes offline use and searchability. It was designed out of frustration with Apple's closed ecosystem and lack of decent support for self-hosted MP3 libraries. 

## Why Musicy Exists

In 2025, Apple still restricts basic MP3 playback unless you pay for services like Apple Music or iTunes Match. Musicy was built from scratch as a personal response to these limitations. It allows users to:

- Import MP3 files from iCloud or Files app using persistent bookmarks
- Build and search their own curated music libraries
- Avoid subscriptions or cloud lock-in
- Leverage native performance and Swift concurrency for a smooth user experience

## Features

### 🎵 Music Library Management

- **Artists / Albums / Songs Views**: Browse, sort, and search with artwork and metadata
- **Full-Text Search (FTS5)**: Search across title, artist, album, and path with SQLite-powered fuzzy matching
- **Playlists**: Create custom playlists with drag-and-drop reordering
- **Library Sync**: Import music folders recursively from iCloud using background sync services

### 🎧 Advanced Playback

- **AVFoundation-Based Audio Playback**: Full support for MP3s with lock screen controls
- **Mini and Full Player UI**: Seamless transitions and persistent playback
- **Queue Management**: Shuffle, repeat, and reorder tracks
- **Background Playback**: Continues playing while the app is backgrounded

### 📁 Filesystem and iCloud Sync

- **Persistent File Access via Security-Scoped Bookmarks**: Stores references safely in SQLite
- **Fallback File Copying**: Copies MP3s into app container while bookmarks are still valid
- **Multi-source Import**: Add and merge multiple folder trees into a unified library

### 🔍 Full-Text Search Engine

- **Powered by SQLite FTS5**: Fast and lightweight search without any cloud dependencies
- **BM25 Ranking**: Smart search results prioritization
- **Async Upserts and Transaction Handling**: Keeps search indexes reliable and performant

### 🧠 Architecture Highlights

- **Swift Actors**: State-safe, concurrency-friendly domain logic
- **MVVM Layering**: Clear separation between View, ViewModel, Repository, and Domain layers
- **SQLite with FTS5**: Used instead of CoreData for tighter schema and query control

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Apple Developer Documentation (AVFoundation, SwiftUI, Combine)
- `SQLite` and [`SQLite.swift`](https://github.com/stephencelis/SQLite.swift)
- `AVAudioPlayer` and `MPRemoteCommandCenter`

