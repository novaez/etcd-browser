
# etcd browser

## Demo
[http://henszey.github.io/etcd-browser/](http://henszey.github.io/etcd-browser/)

## Screen Shot
![etcd-browser Screen Shot](http://henszey.github.io/etcd-browser/images/etcdbrowser.png)

## TODO
* Implement missing features (TTL)

## To build/run as a Docker container:

(adjust options as necessary - to run it as a daemon, remove "--rm", "-t", "-i" and add "-D")

    cd <repository>
    sudo docker build -t etcd-browser .
    sudo docker run --rm --name etcd-browser -p 0.0.0.0:8000:8000 --env ETCD_HOST=10.10.0.1 --env AUTH_PASS=doe -t -i etcd-browser

### Configuration
You can configure the builtin server using environment variables:

 * AUTH_USER: Username for http basic auth (skip to disable auth)
 * AUTH_PASS: Password for http basic auth
 * ETCD_HOST: IP of the etcd host the internal proxy should use
 * ETCD_PORT: Port of the etcd daemon [2379]
 * ETCD_USER: Username for etcd http basic auth [etcd-browser]
 * ETCD_PASS: Password for etcd http basic auth
 * SERVER_PORT: Port of builtin server
 
If you use a secured etcd:
 * ETCDCTL_CA_FILE
 * ETCDCTL_KEY_FILE
 * ETCDCTL_CERT_FILE
