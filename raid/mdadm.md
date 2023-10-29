# Using mdadm

## Creating

1) Create
`sudo mdadm --create /dev/md1 --level=1 --raid-devices=2 /dev/sda1 /dev/sdb1`

2) Format
`sudo mkfs.ext4 /dev/md1`

3) Mount 
`sudo mount /dev/md1 /mnt/raid`

## Adding

1) Add
`sudo mdadm --add /dev/md0 /dev/sdx1`

2) Check that device was added 
`sudo mdadm --detail /dev/md0`

```
/dev/md0:
        Version : 1.2
  Creation Time : Wed Aug 10 18:38:51 2016
     Raid Level : raid5
     Array Size : 209584128 (199.88 GiB 214.61 GB)
  Used Dev Size : 104792064 (99.94 GiB 107.31 GB)
   Raid Devices : 3
  Total Devices : 4
    Persistence : Superblock is persistent

    . . .
```

3) Grow array
`sudo mdadm --grow --raid-devices=4 --backup-file=/root/md0_grow.bak /dev/md0`
The following output indicates that the critical section will be backed up:
`mdadm: Need to backup 3072K of critical section..`
The array will begin to reconfigure with an additional active disk. To view the progress of syncing the data, type:
`cat /proc/mdstat`

4) After the reshape is complete, you will need to expand the filesystem on the array to utilize the additional space:
`sudo resize2fs /dev/md0`

sudo mdadm --detail --brief /dev/md0 | sudo tee -a /etc/mdadm/mdadm.conf

в Fedora 37 для сохранения настроек RAID после перезагрузки системы нужно выполнить дополнительный шаг. После изменения файла `/etc/mdadm/mdadm.conf` нужно обновить образ `initramfs`. Для этого выполните следующую команду:

sudo dracut --force
sudo dracut --force /boot/initramfs-$(uname -r).img $(uname -r)

Команда `dracut` создает новый образ `initramfs`, который будет содержать всю необходимую информацию о RAID массивах, включая изменения, внесенные в файл `/etc/mdadm/mdadm.conf`.

После выполнения этой команды перезагрузите систему и убедитесь, что массив запущен, используя команду `sudo mdadm --detail /dev/md0` (где `/dev/md0` - имя вашего массива).






sudo mdadm --create /dev/md0 --level=6 --raid-devices=10 /dev/sda1 /dev/sdb1 /dev/sdc1 /dev/sdd1 /dev/sde1 /dev/sdf1 /dev/sdg1 /dev/sdh1 /dev/sdi1 /dev/sdj1



92 99 9:0   / /mnt/md0 rw,relatime shared:48  - ext4 /dev/md0 rw,stripe=1024
1078 99 9:1 / /mnt/md1 rw,relatime shared:422 - ext4 /dev/md1 rw


/dev/md1 /mnt/md1 ext4 rw,relatime 0 0