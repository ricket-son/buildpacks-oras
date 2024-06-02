# buildpacks-oras-extension
Cloud Native Buildpacks Extension for [ORAS](https://oras.land/) on Run Image

## Configuration

Include this into your **builder.toml**

```toml
[[buildpacks]]
  id = "ricket-son/oras"
  version = "0.1.0"
  uri = "ghcr.io/ricket-son/oras:0.1.0"

[[order]]
  [[order.group]]
    id = "ricket-son/oras"
    version = "0.1.0"


[[extensions]]
  id = "ricket-son/oras-extension"
  version = "0.1.0"
  uri = "ghcr.io/ricket-son/oras-extension:0.1.0"

[[order-extensions]]
  [[order-extensions.group]]
    id = "ricket-son/oras-extension"
    version = "0.1.0"
```

Include this into your build environment to include the Buildpack

```bash
BP_REQUIRES="oras"
```

## Usage

After Image is built with corresponding Buildpack, use the process

```bash
docker run --rm --entrypoint oras YOUR_IMAGE $PARAMS
```