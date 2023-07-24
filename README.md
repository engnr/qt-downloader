# qt-downloader
CLI to download Qt on headless systems

# Preparation

## Ubuntu

```bash
sudo apt update
sudo apt install python3-pip
sudo pip3 install pipenv
```

## macOS

```
brew install python3
pip3 install pipenv
```

## Common

```
pipenv install
```

# Usage

**Note**. Either enter `pipenv shell` and run commands as is or prepend them with `pipenv run` every time.

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

Qt kit lands into a folder with a name equal to the requested version. The kit is made
relocatable by generating the `qt.conf` file with the appropriate contents. If the `qt.conf`
file exists, then it is not touched.

Need an Open Source version of Qt? Pass option `--opensource` and the Open Source license will
be accepted.

All essential modules of Qt are downloaded by default. Installation of a required subset of
essential modules is supported as well. See option `--module`.

Add-on modules are not downloaded by default. One has to list desired add-ons explicitly by
means of the option `--addon`. On Windows, adding `debug_info` to the list of addons installs
the debug files for the essential modules as well as the selected addons.

Mirrors of official servers are supported by the option `--server`.

**Warning**. All inter-modules dependencies have to be resolved manually.

## Additional tools shipped with Qt

Qt ships a few tools as complementary packages. The current list of supported tools is as follows:
- OpenSSL, see option `--openssl`
- MinGW, see option `--mingw`
- QtCreator, see option `--creator`

The appropriate version of a tool is inferred automatically when possible.

Additional tools land into the `Tools` folder by the side of the Qt itself. The only exception
to this rule is the QtCreator for macOS: it is installed to the root of the output directory.

