# Lightweight WordPress PHP-FPM & Nginx Docker Image

Lightwight Docker image for the (latest) PHP-FPM and Nginx to run WordPress based on [AlpineLinux](http://alpinelinux.org)

* Image size only ~50MB !
* Very new packages (alpine:edge) 2015-04-03:
  * [PHP](http://pkgs.alpinelinux.org/package/main/x86/php) 5.6.7
  * [Nginx](http://pkgs.alpinelinux.org/package/main/x86/nginx) 1.6.2
  * Memory usage is around 50mb on a simple install.
  
  
### A simple example
## Say you want to run a single site on a box with Docker

```bash
docker pull etopian/nginx-proxy

mkdir -p /data/sites/etopian.com/htdocs

sudo docker run -e VIRTUAL_HOST=etopian.com -e VIRTUAL_PORT=8081 -v /data/sites/etopian.com:/DATA -p 8081:80 etopian/alpine-nginx-wordpress

```

### Volume structure

* `htdocs`: Webroot
* `logs`: Nginx/PHP error logs
