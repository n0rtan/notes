# Prepare disks for RAID

1) Make sure that disks arer not using and not mounted;
2) Clead sectors with partition table:
`dd if=/dev/zero of=/dev/sda bs=1M count=100`
3) Mark disk as GPT:
`parted /dev/sda mklabel gpt`
4) Make partition on disk:
`parted /dev/sda mkpart primary 0% 100%`
5) Make sure that partition labeled as raid autodetect:
`parted /dev/sda set 1 raid on`

```
df -h -x devtmpfs -x tmpfs
lsblk -e7


sudo dd if=/dev/zero of=/dev/sda bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdb bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdc bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdd bs=1M count=100
sudo dd if=/dev/zero of=/dev/sde bs=1M count=100

sudo dd if=/dev/zero of=/dev/sdf bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdg bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdh bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdi bs=1M count=100
sudo dd if=/dev/zero of=/dev/sdj bs=1M count=100

sudo parted /dev/sda mklabel gpt
sudo parted /dev/sdb mklabel gpt
sudo parted /dev/sdc mklabel gpt
sudo parted /dev/sdd mklabel gpt
sudo parted /dev/sde mklabel gpt

sudo parted /dev/sda mkpart primary 0% 100%
sudo parted /dev/sdb mkpart primary 0% 100%
sudo parted /dev/sdc mkpart primary 0% 100%
sudo parted /dev/sdd mkpart primary 0% 100%
sudo parted /dev/sde mkpart primary 0% 100%

sudo parted /dev/sda set 1 raid on
sudo parted /dev/sdb set 1 raid on
sudo parted /dev/sdc set 1 raid on
sudo parted /dev/sdd set 1 raid on
sudo parted /dev/sde set 1 raid on
```