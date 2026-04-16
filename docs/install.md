# Install

This repository distributes CostGuard through GitHub release assets. Do not install
from files committed into the repository tree. Download the correct archive for your
platform from the repository `Releases` page.

## Prerequisites

- OpenClaw must already be installed
- the `openclaw` CLI must be available on your `PATH`
- you should have completed OpenClaw onboarding, including daemon or gateway setup
- macOS and Linux require Python 3 on `PATH` because the Unix lifecycle scripts use it for OpenClaw output filtering and config repair

Recommended OpenClaw verification:

```sh
openclaw --help
openclaw onboard --install-daemon
```

If your macOS or Linux system has `python3` but no `python`, create a user-local
shim or install your distribution's Python 3 alias package.

User-local shim:

```sh
mkdir -p ~/bin
ln -s "$(which python3)" ~/bin/python
export PATH="$HOME/bin:$PATH"
```

Ubuntu/Debian alternative:

```sh
sudo apt install python-is-python3
```

## Download

Select the release archive for your platform:

- `costguard-preview-macos-aarch64.tar.gz`
- `costguard-preview-linux-x64.tar.gz`
- `costguard-preview-windows-x64.zip`

Verify the download checksum against the matching release notes or the tracked file
in [`releases/0.1.0-preview/SHA256SUMS.txt`](../releases/0.1.0-preview/SHA256SUMS.txt).

## macOS and Linux

From the extracted bundle root:

```sh
openclaw gateway stop
./scripts/unix/install.sh
./scripts/unix/start.sh
openclaw gateway restart
./scripts/unix/status.sh
./scripts/unix/doctor.sh
```

## Windows

From the extracted bundle root:

```powershell
openclaw gateway stop
.\scripts\windows\install.ps1
.\scripts\windows\start.ps1
openclaw gateway restart
.\scripts\windows\status.ps1
.\scripts\windows\doctor.ps1
```

## What Install Does

- verifies that `openclaw` is available;
- installs or refreshes the CostGuard plugin;
- enables the plugin in OpenClaw config;
- creates local config, data, logs, and runtime directories;
- installs the selected profile, defaulting to `balanced`;
- generates a local sidecar token if one is not already set.

## Script Entrypoints

Windows bundle scripts:

- `install.ps1`
- `start.ps1`
- `stop.ps1`
- `status.ps1`
- `doctor.ps1`
- `disable-plugin.ps1`
- `enable-plugin.ps1`
- `uninstall.ps1`

macOS and Linux bundle scripts:

- `install.sh`
- `start.sh`
- `stop.sh`
- `status.sh`
- `doctor.sh`
- `disable-plugin.sh`
- `enable-plugin.sh`
- `uninstall.sh`

## Rollback

Rollback preserves local state by default.

macOS and Linux:

```sh
./scripts/unix/stop.sh
./scripts/unix/disable-plugin.sh
```

Windows:

```powershell
.\scripts\windows\stop.ps1
.\scripts\windows\disable-plugin.ps1
```
