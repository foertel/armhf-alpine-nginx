### Alpine Linux Nginx for Raspberry Pi

A lightweight [Nginx][nginx] [Docker image][dockerhub_project] built from source atop [Alpine Linux][alpine_linux] for armhf. Available on [GitHub][github_project].

#### Mainline 1.11.x Branch Tags

> Nginx 1.11.8+ are built on Alpine Linux 3.4.5 (OpenSSL 1.0.2j, gcc 5.3.0).

- `1.11.8`, `1.11`, `mainline`, `latest` (2017-01-22, [Dockerfile](https://github.com/foertel/armhf-alpine-nginx/tree/master/versions/1.11.8/Dockerfile), [Changes][nginx_changes])

### Default Usage

```bash
$ docker run --rm foertel/armhf-alpine-nginx
2017/01/22 19:51:47 [notice] 1#1: using the "epoll" event method
2017/01/22 19:51:47 [notice] 1#1: nginx/1.11.8
2017/01/22 19:51:47 [notice] 1#1: built by gcc 5.3.0 (Alpine 5.3.0) 
2017/01/22 19:51:47 [notice] 1#1: OS: Linux 4.4.38-v7+
2017/01/22 19:51:47 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2017/01/22 19:51:47 [notice] 1#1: start worker processes
2017/01/22 19:51:47 [notice] 1#1: start worker process 7
```

### Configuration

[Nginx][nginx] is compiled from source using the same [configure arguments][nginx_configure] as the official, pre-built packages.

```bash
$ docker run --rm foertel/armhf-alpine-nginx nginx -V
nginx version: nginx/1.11.8
built by gcc 5.3.0 (Alpine 5.3.0) 
built with OpenSSL 1.0.2j  26 Sep 2016
TLS SNI support enabled
configure arguments: --prefix=/etc/nginx --sbin-path=/usr/sbin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --pid-path=/var/run/nginx.pid --lock-path=/var/run/nginx.lock --http-client-body-temp-path=/var/cache/nginx/client_temp --http-proxy-temp-path=/var/cache/nginx/proxy_temp --http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp --http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp --http-scgi-temp-path=/var/cache/nginx/scgi_temp --user=nginx --group=nginx --with-http_ssl_module --with-http_realip_module --with-http_addition_module --with-http_sub_module --with-http_dav_module --with-http_flv_module --with-http_mp4_module --with-http_gunzip_module --with-http_gzip_static_module --with-http_random_index_module --with-http_secure_link_module --with-http_stub_status_module --with-http_auth_request_module --with-threads --with-stream --with-stream_ssl_module --with-http_slice_module --with-mail --with-mail_ssl_module --with-file-aio --with-http_v2_module --with-stream_realip_module

$ docker run --rm foertel/armhf-alpine-nginx openssl version
OpenSSL 1.0.2j  26 Sep 2016

$ docker run --rm foertel/armhf-alpine-nginx cat /etc/alpine-release
3.4.5
```

### History

- 2017-01-22 - Initial version with Nginx 1.11.8 and Alpine Linux 3.4.5 (OpenSSL 1.0.2j, gcc 5.3.0).

### Thanks

- [sickp](https://github.com/sickp/docker-alpine-nginx) for alpine-nginx

[alpine_linux]:        https://hub.docker.com/r/armhf/alpine/
[dockerhub_project]:   https://hub.docker.com/r/foertel/armhf-alpine-nginx/
[github_project]:      https://github.com/foertel/armhf-alpine-nginx/
[nginx]:               http://nginx.org/
[nginx_changes]:       http://nginx.org/en/CHANGES
[nginx_configure]:     http://nginx.org/en/linux_packages.html#mainline

