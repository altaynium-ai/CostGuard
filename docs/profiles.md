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

Common preview controls:

```text
ROUTER_ENABLED=false
POLICY_ENGINE_ENABLED=true
PROTECTED_FIRST_TOUCH_ENABLED=true
LATER_TURN_COMPACT_ENABLED=true
SOFT_COMPRESS_ENABLED=true
HARD_COMPRESS_ENABLED=true
TOOL_PERSIST_ENABLED=true
CAPSULES_ENABLED=true
REPEATED_ERROR_AGGREGATION_ENABLED=true
```

## Profile Values

| Setting | `safe-fidelity` | `balanced` | `aggressive-savings` |
|---|---:|---:|---:|
| `TOOL_PERSIST_THRESH_CHARS` | 12000 | 8000 | 4000 |
| `TOOL_PERSIST_THRESH_LINES` | 300 | 200 | 120 |
| `TOOL_PERSIST_THRESH_TOKENS_EST` | 3000 | 2000 | 1000 |
| `EXCERPT_TOTAL_MAX_CHARS` | 1200 | 900 | 700 |
| `EXCERPT_HEAD_CHARS` | 240 | 180 | 120 |
| `EXCERPT_TAIL_CHARS` | 240 | 180 | 120 |
| `CAPSULE_RECENT_TURNS_N` | 6 | 4 | 2 |
| `ASSISTANT_FOLDING_MIN_CHARS` | 2500 | 1800 | 1200 |

## Switching Profiles

Install first, then replace the active `preview.env` with the desired bundled
template before running `start`.

After switching, inspect `config/effective-config.json` to confirm the active
profile and effective runtime values.
