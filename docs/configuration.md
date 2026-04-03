# Configuration

CostGuard is designed to manage most local configuration through the release bundle
scripts rather than through direct manual edits to OpenClaw config.

## Local Home Directory

By default, CostGuard stores its local state in:

- macOS and Linux: `~/.openclaw-cost-guard-preview`
- Windows: `%APPDATA%\OpenClawCostGuardPreview`

If `OPENCLAW_COST_GUARD_HOME` is set, the scripts use that directory instead.

## Important Files

Inside the CostGuard home directory:

- `config/preview.env`: active profile and runtime settings
- `config/current-profile.txt`: selected profile name
- `config/effective-config.json`: generated summary of effective runtime settings
- `logs/sidecar.log`: normal sidecar logs
- `logs/sidecar.err.log`: sidecar stderr log
- `data/costguard.db`: local persisted data
- `run/sidecar.pid`: active sidecar pid file

## Plugin Wiring

The release scripts configure the OpenClaw plugin entry for the CostGuard plugin and
set the connection details needed for the local sidecar.

Avoid editing OpenClaw plugin settings manually unless you are debugging a specific
issue. The install and enable scripts repair stale plugin config automatically.

## Runtime Port

The default sidecar URL is typically:

```text
http://127.0.0.1:8080
```

If that port is already in use, update `config/preview.env` to a different port and
keep the sidecar URL consistent with it.

Example:

```env
SIDE_CAR_PORT=18081
COST_GUARD_SIDECAR_URL=http://127.0.0.1:18081
```

## Profiles

The default profile is `balanced`.

To switch profile, replace the installed `preview.env` with one of the bundled
templates before starting the sidecar:

- `preview.safe-fidelity.env`
- `preview.balanced.env`
- `preview.aggressive.env`

Profile intent and tradeoffs are documented in [profiles.md](profiles.md).

## Privacy Defaults

The preview integration is designed to default to safer handling of prompt content:

- plaintext opt-in is disabled by default;
- hashed or summarized metadata is preferred for internal signals;
- repeated transient errors are compacted to reduce later-turn prompt growth.

If you expose CostGuard to regulated or sensitive workloads, validate the runtime
behavior in your environment before production use.
