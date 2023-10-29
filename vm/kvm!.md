# Windows VM on Fedora 37 !

## Shared Folders

### _On Host machine_

1) install virtiofsd
`sudo dnf install virtiofsd`

2) install virtio-win
`sudo dnf install virtio-win`

3) inject cdrom image
`/usr/share/virtio-win/virtio-win.iso`


### _On VM_

1) Intall virtio drivers and agent

### _Links_

[9.2. Sharing files between the host and its virtual machines using virtiofs](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9/html/configuring_and_managing_virtualization/sharing-files-between-the-host-and-its-virtual-machines_configuring-and-managing-virtualization#sharing-files-between-the-host-and-its-virtual-machines-using-virtiofs_sharing-files-between-the-host-and-its-virtual-machines)

[Chapter 20. Installing and managing Windows virtual machines](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9/html/configuring_and_managing_virtualization/installing-and-managing-windows-virtual-machines-on-rhel_configuring-and-managing-virtualization)
