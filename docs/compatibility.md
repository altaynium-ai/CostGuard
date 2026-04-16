# Compatibility

## Supported Distribution Targets

Current public preview artifacts are packaged for:

- macOS `aarch64`
- Linux `x64`
- Windows `x64`

## Required External Dependency

CostGuard does not replace OpenClaw. You must install OpenClaw separately and make
the `openclaw` CLI available before installing CostGuard.

## Runtime Packaging

The release bundle includes:

- CostGuard sidecar artifact
- OpenClaw plugin files
- profile templates
- install and lifecycle scripts

Some bundles may also include a runtime needed to start the sidecar locally. If a
runtime is included, keep its bundled legal notices intact.

Expected platform runtime paths inside current preview bundles:

- Windows x64: `runtime/sidecar/jre/bin/java.exe`
- macOS aarch64: `runtime/sidecar/jre/Contents/Home/bin/java`
- Linux x64: `runtime/sidecar/jre/bin/java`

If a bundle reports a Java runtime issue, treat the bundle-level `manifest.json`,
`README.txt`, and `doctor` output as the source of truth for that specific artifact.

## Operational Model

CostGuard is best suited to:

- multi-turn workflows with repeated context accumulation;
- tool-heavy runs where intermediate outputs would otherwise bloat later prompts;
- local or developer-managed environments where a sidecar process is acceptable.

CostGuard is not positioned as:

- a full retrieval platform;
- a replacement for broader RAG infrastructure;
- a guarantee of lower output-token usage in every workload.

## Preview Bundle Contents

Each preview bundle is expected to include:

- `README.txt`
- `manifest.json`
- `config/config-template.yaml`
- `config/preview.balanced.env`
- `config/preview.safe-fidelity.env`
- `config/preview.aggressive.env`
- `plugin/openclaw-cost-guard-plugin/`
- `runtime/sidecar/app.jar`
- `docs/quickstart.md`
- `docs/troubleshooting.md`
- `docs/rollback.md`
- `docs/limitations.md`
- `docs/profiles.md`
- `docs/preview_smoke_checklist.md`
- `release_validation/release_validation.md`
