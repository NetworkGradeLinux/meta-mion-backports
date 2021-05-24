# meta-mion-backports

This repo contains recipes and metadata backported from upstream repos which are
not available for the current LTS release

*As these recipes have been backported from active branches -- it will be necessary for them to be periodically updated!!*

## k3s

Source: meta-virtualization(hardknott) f058b195580f90ea8fb2751fe76168e06a746934

- classes/cni_networking.bbclass
- recipes-containers/{containerd,k3s,runc}
- recipes-filter/ipset
- recipes-networking/cni
- recipes-security/libseccomp

As k3s is not available in the dunfell branch of meta-virtualisation, it is
backported from hardknott. These recipes can be removed when mion moves to the
next LTS branch. All the packages listed above are required for k3s to work
correctly.

> NOTE: The `PREFERRED_PROVIDER_*` settings in the layer config ensure that the
backported versions are used even when meta-virtualisation is enabled.

> NOTE: The names of each of the recipes has been changed from `<recipe>_git.bb`
to `<recipe>_<version>.bb` in order for the correct version to be installed
