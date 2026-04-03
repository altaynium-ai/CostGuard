# CostGuard

CostGuard is a closed-source OpenClaw middleware package that reduces token cost and improves runtime efficiency by compressing, compacting, and caching intermediate context during OpenClaw API flows.

This repository is the public release repository for CostGuard. It contains product documentation, release notes, checksums, and licensing terms. It does not contain the private source code for CostGuard.

## What CostGuard Does

- Compresses large intermediate artifacts before they bloat later turns
- Caches useful intermediate state so repeated work is avoided
- Preserves a fail-open integration model so OpenClaw keeps working if CostGuard is unavailable
- Ships as installable release bundles for macOS, Linux, and Windows

## Distribution Model

- OpenClaw is required and is not bundled in this repository
- CostGuard is distributed as binary release assets
- Source code is not published
- Use of the software is governed by [EULA.md](EULA.md)

## Quick Start

1. Install OpenClaw and verify the `openclaw` CLI is available.
2. Open the repository `Releases` page and download the archive for your platform.
3. Extract the archive.
4. Run the platform install script from the extracted bundle root.
5. Start the bundled sidecar.
6. Restart the OpenClaw gateway or daemon so the plugin is reloaded.
7. Verify status with the included `status` and `doctor` scripts.

High level example for macOS and Linux:

```sh
cd <bundle-root>
./scripts/unix/install.sh
./scripts/unix/start.sh
./scripts/unix/status.sh
./scripts/unix/doctor.sh
openclaw gateway restart
```

## Repository Layout

- [`docs/install.md`](docs/install.md): installation and first run
- [`docs/configuration.md`](docs/configuration.md): config paths, runtime behavior, and local state
- [`docs/profiles.md`](docs/profiles.md): profile behavior and tuning intent
- [`docs/compatibility.md`](docs/compatibility.md): supported platforms and prerequisites
- [`docs/troubleshooting.md`](docs/troubleshooting.md): common failures and recovery steps
- [`docs/faq.md`](docs/faq.md): commercial and operational FAQ
- [`docs/release-process.md`](docs/release-process.md): suggested GitHub release workflow
- [`CHANGELOG.md`](CHANGELOG.md): public release history
- [`releases/`](releases/): tracked checksums and release metadata

## Current Release Line

The current published preview line is `0.1.0-preview`.

Tracked checksums for the current preview artifacts are in [`releases/0.1.0-preview/SHA256SUMS.txt`](releases/0.1.0-preview/SHA256SUMS.txt).

## Support Boundaries

CostGuard is designed to be installed on top of an existing OpenClaw setup. The release bundle manages the CostGuard plugin and sidecar, but it does not install or manage OpenClaw itself.

If you are evaluating commercial use, deployment at team scale, or a support arrangement, document those terms outside this repository in your release notes, website, or sales materials.

## License

This repository and the distributed software are proprietary.

- Repository rights notice: [LICENSE](LICENSE)
- Binary usage terms: [EULA.md](EULA.md)
- Third-party notices: [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)
