# rumahl assets

Multi-license asset repository for [rumahl OS](https://github.com/rumahl/rumahl).
It holds the artwork that ships with rumahl OS, kept separate from the source
code so it can be licensed on its own terms.

## Layout

| Path | Contents | License |
| --- | --- | --- |
| `wallpapers/` | Photographic wallpapers | Unsplash License (`LicenseRef-Unsplash`) |
| `LICENSES/` | License texts | — |
| `REUSE.toml` | Path-to-license declarations | — |

Assets that are not third-party default to **CC BY-NC-SA 4.0**.

## Licensing

This repository uses [SPDX](https://spdx.dev/) / [REUSE](https://reuse.software/):
the **path decides the license**. Every covered file has a copyright notice and
a valid SPDX license expression, declared in [`REUSE.toml`](REUSE.toml) with the
license texts under [`LICENSES/`](LICENSES/).

Third-party assets keep their own license and are never relicensed. The
photographic wallpapers are covered by the Unsplash License; attribution is in
[`LICENSES/LicenseRef-Unsplash.txt`](LICENSES/LicenseRef-Unsplash.txt).

CI runs `reuse lint` and fails if any tracked file lacks licensing information.

## Used by rumahl OS

rumahl OS consumes this repository through a pinned checkout and copies the
assets into its frontend at build time. Consumers should not edit files here;
contribute changes upstream instead.

## Adding an asset

1. Confirm you have the right to distribute the asset.
2. Put it in a suitable subdirectory.
3. Declare its license in [`REUSE.toml`](REUSE.toml) and add the license text
   to `LICENSES/` (`LicenseRef-<name>.txt` if it is not an SPDX identifier).
4. Never change the license of a third-party asset; record the real one.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full rules.
