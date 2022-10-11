# multipass-workspace
Multipass Workspace with Ubuntu 22.04 LTS and Docker

## Launch Ubuntu VM

* Create a VM with 4 GB RAM, 20 GB Storage
* Network type: Wi-Fi interface

```sh
multipass launch --network Wi-Fi --name workspace --disk 20G --mem 4G --cpus 16 --cloud-init cloud-config.yml
```

## SSH (Recommended)

* User: `dev`
* No Password
* Groups: `sudo`

```sh
ssh dev@<local_domain>
```

### Example in Windows

```sh
ssh dev@workspace.mshome.net
```

## Shell

* Default user: `ubuntu`

```sh
multipass shell workspace
```

## Stop

```sh
multipass stop workspace
```

## Delete and Purge (already stop before delete)

```sh
multipass delete workspace --purge
```

## Update RAM, CPU, Storage

* Template: `local.<instance_name>.(cpus|disk|memory)`

### Update RAM

```sh
multipass stop workspace
multipass set local.workspace.memory=4G
```