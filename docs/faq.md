# FAQ

## Is CostGuard open source?

No. CostGuard is distributed as closed-source binary releases.

## Can I use GitHub for distribution if the source is private?

Yes. This repository is intended to act as a public release and documentation repo.
The private source code can remain in a separate private repository.

## Which license applies?

The repository is proprietary. Use is governed by:

- [LICENSE](../LICENSE) for repository rights;
- [EULA.md](../EULA.md) for binary usage terms.

## Does CostGuard include OpenClaw?

No. OpenClaw must already be installed.

## Where should release archives live?

Prefer GitHub `Releases` assets instead of committing large binary archives into the
git history. Keep checksums and release notes in the repository.

## Can I commercialize CostGuard later?

Yes. This repository structure keeps that option open because it does not grant an
open-source source-code license.

## Should I publish the extracted bundle in the repository?

No. Treat extracted bundles as local staging material. Publish only the release
archives as GitHub release assets.
