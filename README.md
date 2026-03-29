# CutToTheChase - Cross-Platform Video Editor

<div align="center">
  <br>
  <p><b>CutToTheChase</b></p>
  A swiss army knife of lossless video/audio editing
  <br>
</div>

## Overview

CutToTheChase is a powerful cross-platform desktop application for extremely fast and lossless operations on video, audio, subtitle, and other media files. Built with Electron and FFmpeg, it enables professional-grade editing without quality loss.

## Key Features

- **Lossless Trimming**: Cut and trim video/audio without re-encoding
- **Segment Reordering**: Rearrange video segments without quality loss
- **Multi-Track Editing**: Work with multiple video, audio, and subtitle tracks
- **Format Conversion**: Remux into different containers (MP4, MKV, MOV)
- **Snapshots**: Extract high-resolution JPEG/PNG screenshots
- **Timeline Tools**: Zoom, frame navigation, and keyframe seeking
- **Waveform Display**: Visual audio waveform for precise editing
- **Chapter Marks**: Import/export MP4/MKV chapter marks
- **Subtitle Viewing**: Display and work with embedded subtitles
- **Keyboard Shortcuts**: Efficient keyboard-driven workflow
- **Project Files**: Save and load cut segments for later
- **CLI & API**: Command-line and HTTP API for automation
- **GPS Track Display**: View embedded GPS data on map (DJI drones)

## Supported Formats

**Video Codecs**: H264, H265/HEVC, AV1, VP8, VP9, Theora
**Audio Codecs**: FLAC, MP3, Opus, PCM, Vorbis, AAC
**Containers**: MP4, MOV, WebM, Matroska (MKV), OGG, WAV

Formats not natively supported can be played via FFmpeg-assisted playback, with full lossless export.

## Tech Stack

- **Framework**: Electron
- **Media Processing**: FFmpeg
- **Frontend**: React with TypeScript
- **Player**: Chromium HTML5 Video
- **Build**: electron-builder
- **Platforms**: macOS, Windows, Linux

## Architecture

```
lossless-cut/
├── src/
│   ├── main/                  # Electron main process
│   │   ├── index.ts          # Entry point
│   │   ├── ffmpeg.ts        # FFmpeg wrapper
│   │   └── ipc.ts           # IPC handlers
│   ├── renderer/             # React frontend
│   │   ├── components/       # UI components
│   │   ├── hooks/           # React hooks
│   │   └── utils/           # Utilities
│   └── shared/              # Shared types
├── docs/                     # Documentation
├── static/                   # Static assets
└── package.json
```

## Lossless Operations

The application performs "direct data copy" operations using FFmpeg, preserving original quality:

```
Input → [Demux] → [Edit/Trim] → [Remux] → Output
```

This approach offers:

- Near-instant processing (no re-encoding)
- Original quality preservation
- Minimal CPU usage

## Use Cases

- **Camera Footage**: Trim GoPro/drone footage before editing
- **Commercial Removal**: Cut out commercials from recordings
- **Format Conversion**: Convert H264/H265 MKV to MOV for iPhone
- **Track Extraction**: Extract audio tracks from video
- **Multi-Track Audio**: Add music/subtitles to videos
- **Chapter Editing**: Import/export chapter markers
- **Loop Creation**: Repeat clips without re-encoding
- **Speed Changes**: Adjust playback speed without re-encoding

## Installation

### Download Releases

Available from the releases page.

### Package Managers

- **macOS**: Mac App Store
- **Windows**: Microsoft Store
- **Linux**: Snap, Flatpak

## Development

### Prerequisites

- Node.js 18+
- FFmpeg (system binary)
- pnpm

### Setup

```bash
pnpm install
```

### Development Mode

```bash
pnpm dev
```

### Build

```bash
pnpm build
```

### Package

```bash
pnpm package
```

## CLI Usage

```bash
lossless-cut -i input.mp4 -o output.mp4 -ss 00:01:00 -to 00:02:00
```

## HTTP API

Start with: `lossless-cut --server`

```bash
# Get media info
curl http://localhost:5000/api/info?file=video.mp4

# Cut video
curl -X POST http://localhost:5000/api/cut \
  -H "Content-Type: application/json" \
  -d '{"inputFile": "video.mp4", "outputFile": "cut.mp4", "segments": [{"start": 0, "end": 60}]}'
```

## Key Implementation Details

### FFmpeg Integration

- Spawns FFmpeg processes for all media operations
- Parses FFprobe output for media metadata
- Handles complex filtering and encoding

### Timeline Rendering

- Web Audio API for waveform generation
- Canvas-based timeline visualization
- Efficient chunked file loading

### Electron IPC

- Main process handles file I/O and FFmpeg
- Renderer process provides React UI
- Secure context isolation

## License

MIT License - see [LICENSE](LICENSE) for details.
