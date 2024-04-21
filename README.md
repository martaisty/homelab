# homelab

My HomeLab config

## Fedora CoreOS

### Passwords setup

Generate password hash and update [fedora-core-os-ignition.yml](fedora-core-os-ignition.yml):

```shell
podman run -ti --rm quay.io/coreos/mkpasswd --method=yescrypt
```

Place public keys at [fcos-config/pub_keys](fcos-config/pub_keys).

### Generate ignition

```shell
butane --files-dir fcos-config --pretty --strict --output fcos.ign fedora-core-os-ignition.yml
```

## Mosquito

### Permissions

Update sensitive files permissions:

- `mosquitto/config/certs/*` - `640`
- `mosquitto/config/pwfile` - `640`