# buildpacks-oras-extension
Cloud Native Buildpacks Extension for [ORAS](https://oras.land/) on Run Image

## Configuration

Include this into your **builder.toml**

```toml
[[buildpacks]]
  id = "ricket-son/oras"
  version = "0.2.0"
  uri = "ghcr.io/ricket-son/oras:0.2.0"

[[order]]
  [[order.group]]
    id = "ricket-son/oras"
    version = "0.2.0"
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