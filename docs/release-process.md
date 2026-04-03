# Release Process

This repository should be operated as a binary-release repository, not as a source
repository.

## Recommended Structure

- private repository: source code, CI, build scripts, tests, signing, packaging
- public repository: docs, changelog, license terms, checksums, GitHub releases

## Suggested Release Checklist

1. Build platform archives from the private source repository.
2. Verify install, start, status, doctor, rollback, and uninstall flows.
3. Generate SHA256 checksums for every artifact.
4. Update [`CHANGELOG.md`](../CHANGELOG.md).
5. Add or update `releases/<version>/SHA256SUMS.txt`.
6. Create a Git tag that matches the release version.
7. Publish a GitHub release and upload the platform archives as release assets.
8. Paste install prerequisites, checksums, and known limitations into the release notes.

## What To Keep Out Of Git

- extracted test bundles;
- local staging directories;
- platform-specific IDE files;
- large release archives after they have been uploaded to GitHub Releases.

The local `.gitignore` already excludes the current staging directory pattern used in
this workspace.
