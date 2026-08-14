# eic-spack-mirror

HTTP source mirror for packages in [eic/eic-spack](https://github.com/eic/eic-spack).

## Mirror update workflow

This repository provides a manual GitHub Actions workflow (`Update Spack Mirror`) that:

1. Uses `spack/setup-spack` with `spack_ref: develop` and `packages_ref: develop`
2. Checks out `eic/eic-spack` at `develop`
3. Adds the `eic-spack` repository to Spack
4. Runs `spack mirror create --versions-per-spec 5` for each package found in `eic-spack`
5. Commits updated mirror artifacts into the `mirror/` directory
6. Publishes the mirror contents to GitHub Pages

## Using this mirror in Spack

```bash
spack mirror add eic-spack-mirror https://eic.github.io/eic-spack-mirror/
```
