# Redis-Benchmark
## Before Deploying Redis On Flash Container
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
# Deploying Redis On Flash Enterprise inside Docker Container

## Steps

```
$ docker run -d --cap-add sys_resource --name rp -p 8443:8443 -p 9443:9443 -p 12000:12000 redislabs/redis
```
Visit http://IP:8443 to open Redis Labs Enterprise Software.

Note: The Docker container with RS runs on your localhost with port 8443 open for HTTPS connections, 9443 for REST API connections, and port 12000 open for redis client connections. You can publish other ports with -p <host_port>:<container_port>. 

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image.png)

Click on “Setup”.

In the Node Configuration settings, enter a cluster FQDN such as cluster.local. Then click Next button.


![Screenshot](https://docs.redislabs.com/latest/images/rs/enable_redis_flash.png)

Supply Cluster Name as “xxx-cluster”.

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-3.png)

Click “Next”. If you purchased a cluster key please insert it in the field below and click Next. If you would like to use the free version just click Next. We will use trial version. 

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-4.png)

Click “Next”

Add you entry and click “Next”.

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-6.png)

Once you click “Next” it will create a cluster for you

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-7.png)

Wait for few seconds and you will see the below page which will refresh your page and you will be sooner welcome with Redis Enterprise UI.

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-9.png)

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-10.png)

Accessing Redis Enterprise UI

It’s time to create a new database. 

![Screenshot](https://docs.redislabs.com/latest/images/rs/redis-on-flash.png)

Select “redis database” , "Flash" and the “single region” deployment, and click Next.

On the new redis on flash db page, click the show advanced option link and enter myredisflashdb for a database name and 12000 for the endpoint port number. Then click Activate to create your database.

![Screenshot](https://docs.redislabs.com/latest/images/rs/newredisflashdb.png)

Once you click “Activate”, do verify the entries as shown below:

![Screenshot](https://collabnix.com/wp-content/uploads/2020/02/image-14.png)
