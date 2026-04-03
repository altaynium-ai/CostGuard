# Changelog

All notable public releases of CostGuard should be documented in this file.

## [0.1.0-preview] - 2025-04-02

Initial public preview release.

Included in the preview release line:

- macOS, Linux, and Windows binary bundles
- OpenClaw plugin packaging for CostGuard integration
- managed install, start, stop, status, doctor, enable, disable, and uninstall scripts
- bundled profile presets: `safe-fidelity`, `balanced`, and `aggressive-savings`
- local sidecar runtime packaging
- rollback and troubleshooting guidance

Operational focus of the preview:

- reduce prompt bloat from large intermediate artifacts
- compact repeated transient errors in later turns
- preserve fail-open behavior so OpenClaw remains usable if CostGuard is unavailable
