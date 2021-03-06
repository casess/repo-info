## `telegraf:alpine`

```console
$ docker pull telegraf@sha256:9bdda5c932dc5e69d9b07881e820f4f53e8a30a9221a1738686ef974424ef58f
```

-	Platforms:
	-	linux; amd64

### `telegraf:alpine` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **9.5 MB (9521381 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bd7fb3ed21eaa48ce8a754b28c2d9e485b9d13c9877d110daabe46bc0e92cf5b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["telegraf"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Mon, 14 Nov 2016 18:48:49 GMT
ENV TELEGRAF_VERSION=1.1.1
# Mon, 14 Nov 2016 18:48:51 GMT
RUN apk add --no-cache ca-certificates &&     update-ca-certificates
# Mon, 14 Nov 2016 18:48:57 GMT
RUN apk add --no-cache --virtual .build-deps wget gnupg tar &&     gpg --keyserver hkp://ha.pool.sks-keyservers.net         --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5 &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/telegraf/releases/telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz.asc telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src /etc/telegraf &&     tar -C /usr/src -xzf telegraf-${TELEGRAF_VERSION}-static_linux_amd64.tar.gz &&     mv /usr/src/telegraf*/telegraf.conf /etc/telegraf/ &&     chmod +x /usr/src/telegraf*/* &&     cp -a /usr/src/telegraf*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Mon, 14 Nov 2016 18:48:57 GMT
EXPOSE 8092/udp 8094/tcp 8125/udp
# Mon, 14 Nov 2016 18:48:58 GMT
COPY file:43e6828e001b57ab465cff8dfd3d30830289afe7ca5944b61641956bfe38cd1c in /entrypoint.sh 
# Mon, 14 Nov 2016 18:48:58 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 14 Nov 2016 18:48:59 GMT
CMD ["telegraf"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3dd00e1b73a48ce9b10c90d7db98da9f3d13bb6b7d873ae181a987f9ec33157`  
		Last Modified: Mon, 14 Nov 2016 18:50:59 GMT  
		Size: 344.0 KB (343992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a68ef55adba27a33fe729f0170ad337603e88e36e759c7ff889618bd74557b53`  
		Last Modified: Mon, 14 Nov 2016 18:50:59 GMT  
		Size: 6.9 MB (6864248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5844262ab7bed9f988a6114638ee28252f408926893032de78a768717fcc38fb`  
		Last Modified: Mon, 14 Nov 2016 18:50:57 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
