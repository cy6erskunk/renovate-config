# renovate-config
config presets for renovate bot

## Available Presets

### `default`
Base configuration with security-focused settings:
- Extends `config:base`
- Pins dependency versions with `rangeStrategy: "pin"`
- Adds 24-hour delay before creating PRs (`minimumReleaseAge: "24 hours"`) to reduce supply chain attack risk
- Labels PRs with `renovate-deps`
- Supports `rebase` label for manual rebasing

### `supply-chain-security`
Standalone preset that adds a 24-hour delay to PR creation to mitigate supply chain attack risks.
Can be combined with other presets:
```json
{
  "extends": [
    "github>cy6erskunk/renovate-config:supply-chain-security"
  ]
}
```

### `automerge-minor-patch-devdeps`
Auto-merges minor and patch updates for devDependencies.

### `automerge-patch-deps`
Auto-merges patch updates for production dependencies.
