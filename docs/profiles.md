# Profiles

CostGuard currently ships with three named profiles:

- `safe-fidelity`
- `balanced`
- `aggressive-savings`

Default profile:

- `balanced`

## Profile Intent

`safe-fidelity`

- favors retaining more context before compression thresholds are reached
- best fit when output quality is more important than maximum savings

`balanced`

- targets a practical middle ground between cost reduction and context fidelity
- recommended starting point for most evaluations

`aggressive-savings`

- compresses and compacts sooner
- best fit when budget pressure is stronger than fidelity pressure

## Common Behaviors Across Profiles

All shipped profiles are intended to keep these behaviors enabled:

- policy-driven context handling
- protected first-touch behavior
- later-turn compaction
- soft and hard compression paths
- tool-result persistence
- compact handling of repeated transient errors

## Switching Profiles

Install first, then replace the active `preview.env` with the desired bundled
template before running `start`.

After switching, inspect `config/effective-config.json` to confirm the active
profile and effective runtime values.
