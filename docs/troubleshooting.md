# Troubleshooting

## `openclaw` Not Found

Install OpenClaw first, reopen your shell, and verify:

```sh
openclaw --help
openclaw onboard --install-daemon
```

## Plugin Is Not Enabled

Use the included wrapper scripts instead of editing OpenClaw config by hand.

macOS and Linux:

```sh
./scripts/unix/enable-plugin.sh
./scripts/unix/status.sh
```

Windows:

```powershell
.\scripts\windows\enable-plugin.ps1
.\scripts\windows\status.ps1
```

## Sidecar Starts and Then Exits

Run:

- `status`
- `doctor`

Then inspect:

- the active log path;
- the error log path;
- `config/effective-config.json`.

Common causes:

- port conflict on the configured sidecar port;
- malformed manual edits to `preview.env`;
- stale OpenClaw plugin config after manual changes.

## Port Conflict

Change the sidecar port and URL together in `config/preview.env`.

Example:

```env
SIDE_CAR_PORT=18081
COST_GUARD_SIDECAR_URL=http://127.0.0.1:18081
```

Then restart CostGuard.

## Runtime Problem

If startup reports a runtime issue:

- confirm the extracted bundle is intact;
- re-run `install`;
- run `doctor`;
- check whether the bundle expected a packaged runtime or a system runtime.

## Quick Rollback

Rollback restores plain OpenClaw behavior without deleting local CostGuard data by
default.

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
