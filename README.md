# MediaPlayer LocalCache Cache Key Correlator

A forensic utility for correlating Windows Media Player (UWP) cached thumbnails located in:

C:\Users\<User>\AppData\Local\Packages\Microsoft.ZuneMusic_8wekyb3d8bbwe\LocalCache\Image

with URI values stored in:

MediaPlayer.db

## 🔎 Purpose

This tool reconstructs cache filenames using:

SHA256(URI_string_UTF8)
→ dash-separated hexadecimal
→ append "-0-<width>-<height>"

It allows deterministic correlation between:

- MediaPlayer.db entries (Video.Uri / File.Uri)
- Cached thumbnail artefacts
- Original media file paths

## ⚙️ Features

- Auto-discovers URI/path-like columns in MediaPlayer.db
- Supports SHA1 and SHA256
- Generates dash-hex and signed-decimal formats
- Supports multiple thumbnail sizes
- Outputs structured CSV report

## 🚀 Usage
python mediaplayer_cache_matcher.py --cache-dir "C:\Users\username\AppData\Local\Packages\Microsoft.ZuneMusic_8wekyb3d8bbwe\LocalCache\Image" --db "MediaPlayer.db path"
