# meta-mion-backports

This repo contains recipes and metadata backported from upstram repos which are not available for the current LTS release

*As these recipes have been backported from active branches - it will be necessary for them to be periodically updated!!*

## 1. k3s 

Source - meta-virtialisation (hardknott) f058b195580f90ea8fb2751fe76168e06a746934
- classes/cni_networking.bbclass
- recipes-containers/{containerd,k3s,runc}
- recipes-filter/ipset
- recipes-networking/cni
- recipes-security/libseccomp

k3s is not available in the dunfell branch of meta-virtualisation so it was backported from hardknott - these recipes can be removed when we move to the next LTS branch. All of the pachages listed above are required for k3s to work correctly.

NOTE: The PREFERRED_PROVIDER_* settings in the layer config ensure that the backported versions are used even if meta-virtualisation is enabled
NOTE: The names of each of the recipes has been changed from <recipe>_git.bb to <recipe>_<version>.bb in order for the correct version to be installed
