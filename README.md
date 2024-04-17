# homelab
My HomeLab config

## Fedora CoreOS

### Generate password hash

```shell
podman run -ti --rm quay.io/coreos/mkpasswd --method=yescrypt
```

### Generate ignition

Place public keys at `fcos-config/pub_keys`

```shell
butane --files-dir fcos-config --pretty --strict --output fcos.ign fedora-core-os-ignition.yml
```

## Mosquito 

### Permissions 

Owner and group - app user (inside container)

- `config/certs/` - `555`
- `config/certs/*` - `400`
- `config/mosquitto.conf` - `644`
- `config/pwfile` - `600`