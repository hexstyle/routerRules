# routerRules

Shared routing targets for routers.

This repository contains only the human-maintained source list of domains, IPv4 addresses and CIDRs that should be routed through special paths on supported routers.

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

## Purpose

The file is meant to stay simple:

- one shared operator-facing list
- no generated data
- no device-specific config
- no cached DNS resolution results

## Notes

- Routers may consume this list differently.
- Some routers can route by domain, others may resolve domains to IP locally.
- This repository should remain just the shared rule list and a short description of its format.
