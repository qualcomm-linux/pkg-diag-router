# pkg-diag-router

Debian packaging repository for `qcom-diag-router`, a daemon that routes Qualcomm diagnostic messages between the host and modem. The package is built from prebuilt binaries sourced from Artifactory and integrates with the [qcom-build-utils](https://github.com/qualcomm-linux/qcom-build-utils) reusable workflow infrastructure.

## Branches

- **main**: Primary branch containing workflow logic in `.github/` and boilerplate documentation (license, contribution guidelines, this README).
- **qcom/debian/trixie**: Packaging branch for Debian Trixie. Contains the `debian/` folder targeting the Trixie distribution.
- **qcom/ubuntu/resolute**: Packaging branch for Ubuntu Resolute. Contains the `debian/` folder targeting the Resolute distribution.

## Package

| Field | Value |
|---|---|
| Source / Binary | `qcom-diag-router` |
| Version | 1.0.2 |
| Architecture | arm64 |
| Depends | `qcom-libdiag` |
| Upstream source | Prebuilt binary from Artifactory |

## Workflows

The `main` branch includes the following workflows in `.github/workflows/`:

- **build-debian-package.yml**: Builds the Debian package by invoking reusable workflows from `qcom-build-utils`.
- **promote-prebuilt.yml**: Promotes the package to a new prebuilt upstream release.
- **promote-upstream.yml**: Promotes the package's tracking version to a new upstream release.
- **pkg-pr-hook.yml**: Executes during a PR and after it is merged.
- **release.yml**: Triggers a release of the package.
- **qcom-preflight-checks.yml**: Sanity checks inherited from the base Qualcomm template.
- **stale-issues.yaml**: Manages stale issues.

