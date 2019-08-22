# qt-downloader
CLI to download Qt on headless systems

# Preparation

## Ubuntu

```bash
sudo apt update
sudo apt install python3-pip
sudo pip3 install requests semantic_version lxml
```

## macOS

```
brew install python3 p7zip
pip3 install requests semantic_version lxml
```

# Usage

Start by reading help: `./qt-downloader --help`

Basic usage pattern is `./qt-downloader [os] [version] [target] [toolchain]`

Arguments are designed to be provided from left to right, so that one can discover reasonable values for specific OS and Qt version on the go.

Complete set of available Qt kits is obtainable by: `./qt-downloader --all`. *This operation lasts for about half a minute and provides lengthy output.*
