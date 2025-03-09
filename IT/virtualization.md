# Virtualization

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
fdisk /dev/vda
partprobe
resize2fs /dev/vdaNUMBER
```
