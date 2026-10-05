# Contributing to rumahl assets

This repository holds artwork for rumahl OS under multiple licenses. This
document explains how contributions are licensed and how new assets and
licenses are added.

## License model

[SPDX](https://spdx.dev/) / [REUSE](https://reuse.software/) is used so that
**every file's license is declared by its path**. There is exactly one answer to
"what license is this file under?", and it is machine-checkable.

- The mapping lives in [`REUSE.toml`](REUSE.toml); license texts live in
  [`LICENSES/`](LICENSES/).
- The default for first-party assets is **CC BY-NC-SA 4.0**.
- Third-party assets override the default per path and keep their own license.

### Adding an asset

1. Confirm you have the right to distribute the asset.
2. Place it in a suitable subdirectory (for example `wallpapers/`).
3. Add or extend an annotation in [`REUSE.toml`](REUSE.toml):
   - `SPDX-FileCopyrightText` — the actual rights holder(s).
   - `SPDX-License-Identifier` — the real license.
4. Make sure the license text exists in `LICENSES/`:
   - `<SPDX-id>.txt` for licenses on the SPDX list;
   - `LicenseRef-<name>.txt` for anything else.
5. For a single file, a `<file>.license` sidecar (same name plus `.license`) is
   often cleaner than a glob. Images cannot carry a header, so use a sidecar or
   a `REUSE.toml` annotation.

### Adding a new license

Adding a license is a **data change**, not a policy change:

1. Drop the text into `LICENSES/<SPDX-id>.txt` (or `LicenseRef-<name>.txt`).
2. Point the relevant `REUSE.toml` annotation at the identifier.
3. If a file genuinely needs more than one license, express it with SPDX
   (`A AND B`, `A OR B`) instead of inventing a rule.

### Third-party assets

**Never relicense a third-party asset.** Record the real license and the
attribution the license requires. The wallpapers here, for example, are under
the Unsplash License and are not project-owned.

## Inbound = outbound

All commits must be signed off under the [Developer Certificate of Origin
1.1](https://developercertificate.org/):

```sh
git commit -s
```

By signing off you license your contribution under **the license already
declared for the paths you changed**. You cannot use a contribution to relicense
a path or a tree; that is a maintainer decision and affects all previous
contributors.

## Checks

CI runs `reuse lint` and fails if any tracked file lacks copyright or licensing
information. Run it locally if you have the [REUSE tool](https://github.com/fsfe/reuse-tool)
installed:

```sh
reuse lint
```
