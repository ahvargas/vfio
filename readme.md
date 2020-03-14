# PCI passthrough via OVMF


## Grub

Edit `/boot/grub/grub.cfg` 

Update configuration:

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

## mkinitcpio


Edit `/etc/mkinitcpio.conf`

Update configuration:

```bash
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

## quemu 

Edit `/etc/libvirt/qemu.conf`

Restart the service.
```bash
sudo systemctl restart libvirtd
```

## virsh 

Backup image:

```bash
virsh dumpxml base-win10  > base-win-10.xml 
```

Restore image:

```bash
virsh define --file base-win-10.xml 
```

## Links

1. [Arch guide](https://wiki.archlinux.org/index.php/PCI_passthrough_via_OVMF)

2. [Boot GPU](https://passthroughpo.st/explaining-csm-efifboff-setting-boot-gpu-manually/)

3. [Ideas](https://passthroughpo.st/things-vfio-working/)

4. [IOMMU](https://www.ece.rice.edu/~willmann/pubs/cdna_usenix.pdf)