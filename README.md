# how-to-install-kvm-on-ubuntu
how to install kvm on ubuntu


## Bước 1: Check xem máy có ảo hóa bằng kvm được không
+ Check bước 1
```
grep -Eoc '(vmx|svm)' /proc/cpuinfo
```
Nếu số core lớn hơn 0 là được

+ Check bước 2
```
sudo apt update
sudo apt install cpu-checker
kvm-ok
```

```
output này thì okie.
INFO: /dev/kvm exists
KVM acceleration can be used
```
## Bước 2: Check xem máy có ảo hóa bằng kvm được không
```
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virtinst virt-manager
```
```
qemu-kvm - software that provides hardware emulation for the KVM hypervisor.
libvirt-daemon-system - configuration files to run the libvirt daemon as a system service.
libvirt-clients - software for managing virtualization platforms.
bridge-utils - a set of command-line tools for configuring ethernet bridges.
virtinst - a set of command-line tools for creating virtual machines.
virt-manager - an easy-to-use GUI interface and supporting command-line utilities for managing virtual machines through libvirt.
```

```
sudo systemctl is-active libvirtd
```
 
you’ll need to add your user to the “libvirt” and “kvm” groups. To do that, enter:
```
sudo usermod -aG libvirt $USER
sudo usermod -aG kvm $USER
```

## Bước 3: Tạo máy ảo
Mở gui để tạo máy ảo, tải iso file về và tạo
```
sudo virt-manager
```

*link tham khảo : https://linuxize.com/post/how-to-install-kvm-on-ubuntu-20-04/
