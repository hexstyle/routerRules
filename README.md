# routerRules

Shared routing targets for multiple routers.

This repository contains the human-maintained source list that routers consume and translate into device-specific filter artifacts.

## Canonical File

- [lists/shared-targets.txt](/Users/redff00xx/proj/routerRules/lists/shared-targets.txt)

## Allowed Line Types

One rule per line:

- domain name
- IPv4 address
- IPv4 CIDR
- comment starting with `#`

Blank lines are allowed.

Examples:

```text
chatgpt.com
149.154.160.0/20
8.8.8.8
# telegram
telegram.org
```

## What This File Is

This file is:

- the shared operator-facing list
- the sync target for routers
- the input for local domain-to-IP resolution on routers that cannot match domains directly

## What This File Is Not

This file is not:

- a generated mapping database
- a resolved IP cache
- a device-specific config file

Routers should generate those locally.

## Sync Policy

Routers using this repo should follow this merge rule:

1. Prefer the GitHub version as the base.
2. If the local router has unique non-comment rules that do not exist in GitHub, append them to the end.
3. Commit the merged result on top of the GitHub version.

This keeps the shared file authoritative while still preserving local additions.

## Notes

- Domain resolution is intentionally left to the routers.
- Different consumers may produce different generated outputs from the same source list.
- Comments may be reformatted or moved by future tooling, but rule lines must stay semantically stable.
