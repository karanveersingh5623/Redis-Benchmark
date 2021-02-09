# Redis-Benchmark

```
$ sudo /opt/redislabs/sbin/prepare_flash.sh
```
```
$ mkfs.ext4 /dev/nvme1n1 
```
```
$ mount -t ext4 /dev/nvme1n1 /var/opt/redislabs/flash
```
```
$ chmod -R 777 /var/opt/redislabs/flash/
```
