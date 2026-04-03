# Install

This repository distributes CostGuard through GitHub release assets. Do not install
from files committed into the repository tree. Download the correct archive for your
platform from the repository `Releases` page.

## Prerequisites

- OpenClaw must already be installed
- the `openclaw` CLI must be available on your `PATH`
- you should have completed OpenClaw onboarding, including daemon or gateway setup

Recommended OpenClaw verification:

```sh
openclaw --help
openclaw onboard --install-daemon
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
./scripts/unix/install.sh
./scripts/unix/start.sh
./scripts/unix/status.sh
./scripts/unix/doctor.sh
openclaw gateway restart
```

## Windows

From the extracted bundle root:

```powershell
.\scripts\windows\install.ps1
.\scripts\windows\start.ps1
.\scripts\windows\status.ps1
.\scripts\windows\doctor.ps1
openclaw gateway restart
```

## What Install Does

- verifies that `openclaw` is available;
- installs or refreshes the CostGuard plugin;
- enables the plugin in OpenClaw config;
- creates local config, data, logs, and runtime directories;
- installs the selected profile, defaulting to `balanced`;
- generates a local sidecar token if one is not already set.

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
