---
title: Virtualization
---

## qemu

- [https://wiki.debian.org/KVM](https://wiki.debian.org/KVM)

```sh
apt install qemu-system libvirt-daemon-system
adduser $USER libvirt
apt install virt-manager # nice GUI
```

## Resize VM

```sh
# edit the config
EDITOR=nano sudo virsh edit --domain vm_name

# resize the disk
sudo qemu-img resize /path/to/vm.qcow2 +20G

# then inside the VM

# little check on fstab - also to get the swap uuid
cat /etc/fstab
# turn off the swap
swapoff -a
# resize the partition
fdisk /dev/vda
    # delete partitions
    # create a new partitions with the same start sector
partprobe
resize2fs /dev/vdaNUMBER
# optionally, if you have a swap partition
mkswap /dev/vdaNUMBER --uuid <UUID>
# restart the swap
swapon -a
```
