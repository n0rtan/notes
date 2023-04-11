## Windows VM on Fedora 37

# Shared Folders

# _On Host machine_

1) install virtiofsd
`sudo dnf install virtiofsd`

2) install virtio-win
`sudo dnf install virtio-win`

3) inject cdrom image
`/usr/share/virtio-win/virtio-win.iso`


# _On VM_

1) Intall virtio drivers and agent

