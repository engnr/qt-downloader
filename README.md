# qt-downloader
CLI to download Qt on headless systems

# Preparation

## Ubuntu

```bash
sudo apt update
sudo apt install python3-pip p7zip-full
sudo pip3 install requests semantic_version lxml
```

## macOS

```
brew install python3 p7zip
pip3 install requests semantic_version lxml
```

# Usage

Start by reading the help: `./qt-downloader --help`

A basic usage pattern is `./qt-downloader [os] [target] [version] [toolchain]`

Arguments are designed to be provided from left to right, so that one can discover
reasonable values step by step. Feeling doubtful about what to type? Don't bother typing.
Fire a command as is, and allowed values for the first yet to be specified argument are to be
handed to you after a while.

Here's an example:
```
$ ./qt-downloader
Discovering available OS types... Done
  Choose from: linux, linux_x86, macos, windows

$ ./qt-downloader macos
OS type: macos
Discovering available targets... Done
  Choose from: android, desktop, ios
```

At any step, one might add option `--all` and all yet to be specified arguments are to be
discovered in one go. This way, discovering of all the arguments at the very beginning is
possible too: `./qt-downloader --all`. *Bear in mind, though, that this operation lasts for
about half a minute and provides lengthy output.*

Qt kit lands into a folder with a name equal to the requested version.

