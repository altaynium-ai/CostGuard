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

## Operational Model

CostGuard is best suited to:

- multi-turn workflows with repeated context accumulation;
- tool-heavy runs where intermediate outputs would otherwise bloat later prompts;
- local or developer-managed environments where a sidecar process is acceptable.

CostGuard is not positioned as:

- a full retrieval platform;
- a replacement for broader RAG infrastructure;
- a guarantee of lower output-token usage in every workload.
