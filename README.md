# Slim Upjet-based Crossplane provider for AWS for Agronod

## Add/ Remove resources

1. Enable/ Disable the resource in [zz_monolith_setup.go](/internal/controller/zz_monolith_setup.go)
2. Add/ Remove the resource in [Makefile](/Makefile) section **kustomize-crds**

## Build and push

```bash
# Init or update submodules
git submodule update --init --recursive

# Login to github Agronod
gh auth login

# Ensure everything is check in and tag
git tag v1.19.0-slim

# Build and push
BUILD_ARGS="--load" XPKG_REG_ORGS_NO_PROMOTE="" XPKG_REG_ORGS="ghcr.io/agronod" make build.all publish BRANCH_NAME=main
```
