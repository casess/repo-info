## `redis:3-alpine`

```console
$ docker pull redis@sha256:b4c47064c182d77aed359ceab16ebfec9b749a6b18af3988731181252f0f1b44
```

-	Platforms:
	-	linux; amd64

### `redis:3-alpine` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **8.0 MB (7988013 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9947c5a33865d3f74c0485ce5f615499db1855584f1455976d1b41a0a9f56729`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Wed, 19 Oct 2016 00:07:57 GMT
RUN addgroup -S redis && adduser -S -G redis redis
# Wed, 19 Oct 2016 00:07:59 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Tue, 06 Dec 2016 22:55:45 GMT
ENV REDIS_VERSION=3.2.6
# Tue, 06 Dec 2016 22:55:46 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-3.2.6.tar.gz
# Tue, 06 Dec 2016 22:55:46 GMT
ENV REDIS_DOWNLOAD_SHA1=0c7bc5c751bdbc6fabed178db9cdbdd948915d1b
# Tue, 06 Dec 2016 22:56:29 GMT
RUN set -ex 		&& apk add --no-cache --virtual .build-deps 		gcc 		linux-headers 		make 		musl-dev 		tar 		&& wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL" 	&& echo "$REDIS_DOWNLOAD_SHA1 *redis.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/redis 	&& tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1 	&& rm redis.tar.gz 		&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h 	&& sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h 	&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h 		&& make -C /usr/src/redis 	&& make -C /usr/src/redis install 		&& rm -r /usr/src/redis 		&& apk del .build-deps
# Tue, 06 Dec 2016 22:56:30 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Dec 2016 22:56:30 GMT
VOLUME [/data]
# Tue, 06 Dec 2016 22:56:30 GMT
WORKDIR /data
# Tue, 06 Dec 2016 22:56:31 GMT
COPY file:9b596974f478088dc2d2bf2906046f6c8872ecff3c716abd89850fd50ec90c47 in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:56:31 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Dec 2016 22:56:32 GMT
EXPOSE 6379/tcp
# Tue, 06 Dec 2016 22:56:32 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e231f7bdf9dfacf1bf9ecf8f9c82a422efd59e4d918599dd184a380a55c4659`  
		Last Modified: Wed, 19 Oct 2016 00:08:54 GMT  
		Size: 1.3 KB (1268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a74fb2950f817fd68a70f4ea9d395ab1266040f47aacfcbc5ae48d55d60cd9f`  
		Last Modified: Wed, 19 Oct 2016 00:08:54 GMT  
		Size: 7.9 KB (7927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b8e4215fba224a7fad90770875b90db63fa5ed6345a0d2d8d6577a99472c2e9`  
		Last Modified: Tue, 06 Dec 2016 23:00:26 GMT  
		Size: 5.7 MB (5665372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6186b0ef323fee3923c47d8afc34cd42dcea475de895f91bff869dd8721e425`  
		Last Modified: Tue, 06 Dec 2016 23:00:23 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25b8fb88c84f20fa8cf59713d2a9e9535a0a052512724e386f36691e41b9dc4b`  
		Last Modified: Tue, 06 Dec 2016 23:00:23 GMT  
		Size: 390.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
