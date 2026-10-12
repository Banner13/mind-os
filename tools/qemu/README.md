
# example

``` bash
qemu-system-x86_64 -enable-kvm \
-cpu host \
-machine pc \
-smp "4" \
-m "2048" \
-nographic \
-kernel ./bzImage \
-append "console=ttyS0 root=/dev/vda rw rootwait" \
-drive "file=./rootfs.ext2,format=raw,if=virtio" \
-netdev "user,id=net0,hostfwd=tcp::2222-:22" \
-device "virtio-net-pci,netdev=net0" 
```