# unvelt desktop — installers

Installers for the unvelt desktop app, and the manifest its updater reads.

## Installing

**macOS**

```
brew install --cask unvelt/tap/unvelt
```

The cask clears the quarantine flag macOS attaches to downloads. unvelt is
signed with its own certificate but not notarized by Apple, so without that
flag cleared Gatekeeper refuses to open it — Sequoia removed the
Control-click bypass that used to get past this.

**Windows**

Download `unvelt_<version>_x64-setup.exe` from the latest release and run it.
Windows builds are not signed, so the first run shows a SmartScreen warning.

**Linux**

Download `unvelt_<version>_amd64.AppImage`, make it executable and run it.
The `.deb` is for Debian and Ubuntu; on any other distribution use the
AppImage. Linux is not a supported target yet — most of what unvelt records
on Windows and macOS, it cannot see on Linux.

## What is in a release

| file | what it is |
|---|---|
| `unvelt_<version>_x64-setup.exe` | Windows installer |
| `unvelt_<version>_universal.dmg` | macOS disk image, Intel and Apple Silicon |
| `unvelt.app.tar.gz` | macOS update payload, for the updater |
| `unvelt_<version>_amd64.AppImage` | Linux, any distribution |
| `unvelt_<version>_amd64.deb` | Linux, Debian and Ubuntu |
| `unvelt-agent-<target>` | the collector as a command-line binary |
| `*.sig` | updater signatures, for the files the updater fetches |
| `latest.json` | the manifest the updater reads |
| `SHA256SUMS` | checksums for everything above |

On Windows and macOS unvelt updates itself, so this page is only needed for a
first install. A Linux AppImage does not update itself; download the new one.
