## `haproxy:latest`

```console
$ docker pull haproxy@sha256:f66887f7e4adfda87b6c61ef4b18b478019fe60d7d6dce313f085604cf83d34b
```

-	Platforms:
	-	linux; amd64

### `haproxy:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **57.8 MB (57831994 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7cc35805808d2aa456415f36b15ab890537e29ffdf59716cb5f37ca4294b03ea`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["haproxy","-f","\/usr\/local\/etc\/haproxy\/haproxy.cfg"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:41:17 GMT
RUN apt-get update && apt-get install -y libssl1.0.0 libpcre3 --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Mon, 28 Nov 2016 23:06:04 GMT
ENV HAPROXY_MAJOR=1.7
# Mon, 28 Nov 2016 23:06:05 GMT
ENV HAPROXY_VERSION=1.7.0
# Mon, 28 Nov 2016 23:06:05 GMT
ENV HAPROXY_MD5=ab6e169aeb1b53364aacda80c904398a
# Mon, 28 Nov 2016 23:06:58 GMT
RUN buildDeps='curl gcc libc6-dev libpcre3-dev libssl-dev make' 	&& set -x 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 	&& curl -SL "http://www.haproxy.org/download/${HAPROXY_MAJOR}/src/haproxy-${HAPROXY_VERSION}.tar.gz" -o haproxy.tar.gz 	&& echo "${HAPROXY_MD5}  haproxy.tar.gz" | md5sum -c 	&& mkdir -p /usr/src/haproxy 	&& tar -xzf haproxy.tar.gz -C /usr/src/haproxy --strip-components=1 	&& rm haproxy.tar.gz 	&& make -C /usr/src/haproxy 		TARGET=linux2628 		USE_PCRE=1 PCREDIR= 		USE_OPENSSL=1 		USE_ZLIB=1 		all 		install-bin 	&& mkdir -p /usr/local/etc/haproxy 	&& cp -R /usr/src/haproxy/examples/errorfiles /usr/local/etc/haproxy/errors 	&& rm -rf /usr/src/haproxy 	&& apt-get purge -y --auto-remove $buildDeps
# Mon, 28 Nov 2016 23:07:03 GMT
COPY file:b1cb7b827dc9fcd27909f9c233ac2faa2d7534c25992fa5f3402d22503666d6d in / 
# Mon, 28 Nov 2016 23:07:03 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 28 Nov 2016 23:07:04 GMT
CMD ["haproxy" "-f" "/usr/local/etc/haproxy/haproxy.cfg"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3bf50e4075efc324ebc179dc3846c2487f280b0c4cd194a99df6d78d431836a8`  
		Last Modified: Tue, 08 Nov 2016 19:42:26 GMT  
		Size: 1.7 MB (1690386 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff73258bb286efaff733f01af06938a3f16f93977e68c9eb569b83d7dedaf4a4`  
		Last Modified: Mon, 28 Nov 2016 23:10:58 GMT  
		Size: 4.8 MB (4784275 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47b87bb0319848421d10d972b20deb89410da129fa25efd2e389550032b8e96d`  
		Last Modified: Mon, 28 Nov 2016 23:10:57 GMT  
		Size: 344.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
