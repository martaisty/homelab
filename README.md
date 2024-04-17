# homelab
My HomeLab config

## Generate password hash

```shell
podman run -ti --rm quay.io/coreos/mkpasswd --method=yescrypt
```

## Generate ignition

Place public keys at `fcos-config/pub_keys`

```shell
butane --files-dir fcos-config --pretty --strict --output fcos.ign fedora-core-os-ignition.yml
```