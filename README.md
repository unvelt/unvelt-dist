# unvelt desktop — installers

Installers for the unvelt desktop app, and the manifest its updater reads.
Nothing else lives here: the source is in a private repository.

This repository exists because a private repository's release assets are a 404
to anything without a GitHub credential — and the two things that need them
have none. The updater runs on your machine and cannot sign in as anybody, and
Homebrew's downloader is a plain HTTP fetch. Until these builds were published
here, no unvelt desktop had ever updated itself on any platform.

## Installing

**macOS**

```
brew install --cask unvelt/tap/unvelt
```

The cask clears the quarantine flag macOS attaches to downloads. unvelt is not
signed by an Apple Developer certificate, and without that flag cleared
Gatekeeper refuses to open it — Sequoia removed the Control-click bypass that
used to get past this.

**Windows**

Download `unvelt_<version>_x64-setup.exe` from the latest release and run it.

**Linux**

`.AppImage` and `.deb` are published. Linux is not a supported target yet.

## What is in a release

| file | what it is |
|---|---|
| `unvelt_<version>_x64-setup.exe` | Windows installer |
| `unvelt_<version>_aarch64.dmg` | macOS disk image (Apple Silicon) |
| `unvelt.app.tar.gz` | macOS update payload, for the updater |
| `unvelt_<version>_amd64.AppImage` / `.deb` | Linux |
| `unvelt-agent-<target>` | the collector as a command-line binary |
| `*.sig` | updater signatures |
| `latest.json` | the manifest the updater reads |
| `SHA256SUMS` | checksums for everything above |

Builds are unsigned on every platform. That is a cost of the project having no
code-signing certificate, and it is stated here rather than discovered at the
first security prompt.
