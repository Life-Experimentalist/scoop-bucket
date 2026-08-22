# Life-Experimentalist/scoop-bucket

A Scoop bucket carrying one manifest: [**dev-prune**](https://github.com/Life-Experimentalist/dev-prune),
a universal, lockfile-safe workspace pruner.

```powershell
scoop bucket add life-experimentalist https://github.com/Life-Experimentalist/scoop-bucket
scoop install dev-prune
```

That registers both names — `dev-prune` and `devp` — on 64-bit, ARM and 32-bit Windows.

To upgrade:

```powershell
scoop update dev-prune
```

## What is in here

`bucket/dev-prune.json`, and nothing else. It is not written by hand: the manifest is
rendered by `scripts/render-packaging.sh` in the
[dev-prune repository](https://github.com/Life-Experimentalist/dev-prune/tree/main/packaging/scoop)
against the assets each release actually publishes, and
[`.github/workflows/sync.yml`](.github/workflows/sync.yml) copies it here. Every download
URL is matched by a `hash` that Scoop verifies before extracting, so a tampered archive
fails the install rather than reaching your machine.

**Open issues and pull requests against
[Life-Experimentalist/dev-prune](https://github.com/Life-Experimentalist/dev-prune/issues),
not here.** A change made in this repository is overwritten by the next sync.

## You do not have to add the bucket

The manifest can be installed straight from its URL, and Scoop still checks the hash:

```powershell
scoop install https://raw.githubusercontent.com/Life-Experimentalist/dev-prune/main/packaging/scoop/dev-prune.json
```

The bucket exists so that `scoop update` keeps working afterwards, which the URL form does
not do.

## Licence

Apache-2.0, the same as dev-prune itself.
