## `logstash:latest`

```console
$ docker pull logstash@sha256:6abdea7d0685cc1f1ada76265f243036f1e90c91112b819ceefc095e5e6b7445
```

-	Platforms:
	-	linux; amd64

### `logstash:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **221.3 MB (221301572 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0ec18fcb5f14c91954bbd7b9e3b4c97370ca3fd770e1fa74f379f877989468da`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["-e",""]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:52:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:53:53 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Tue, 08 Nov 2016 18:53:53 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:53:54 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_VERSION=8u111
# Tue, 08 Nov 2016 18:53:55 GMT
ENV JAVA_DEBIAN_VERSION=8u111-b14-2~bpo8+1
# Tue, 08 Nov 2016 18:53:56 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20140324
# Tue, 08 Nov 2016 18:54:18 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 08 Nov 2016 18:54:26 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 08 Nov 2016 22:14:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https 		libzmq3 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 22:15:00 GMT
RUN mkdir -p /usr/local/lib 	&& ln -s /usr/lib/*/libzmq.so.3 /usr/local/lib/libzmq.so
# Tue, 08 Nov 2016 22:15:00 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 22:15:05 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Tue, 08 Nov 2016 22:15:06 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 46095ACC8548582C1A2699A9D27D666CD88E42B4
# Tue, 08 Nov 2016 22:25:06 GMT
RUN echo 'deb https://artifacts.elastic.co/packages/5.x/apt stable main' > /etc/apt/sources.list.d/logstash.list
# Fri, 09 Dec 2016 17:49:08 GMT
ENV LOGSTASH_VERSION=5.1.1
# Fri, 09 Dec 2016 17:49:08 GMT
ENV LOGSTASH_DEB_VERSION=1:5.1.1-1
# Fri, 09 Dec 2016 17:49:34 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y --no-install-recommends "logstash=$LOGSTASH_DEB_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Fri, 09 Dec 2016 17:49:35 GMT
ENV PATH=/usr/share/logstash/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 09 Dec 2016 17:49:35 GMT
ENV LS_SETTINGS_DIR=/etc/logstash
# Fri, 09 Dec 2016 17:49:36 GMT
RUN set -ex; 	if [ -f "$LS_SETTINGS_DIR/logstash.yml" ]; then 		sed -ri 's!^path\.config:!#&!g' "$LS_SETTINGS_DIR/logstash.yml"; 	fi; 	if [ -f "$LS_SETTINGS_DIR/log4j2.properties" ]; then 		cp "$LS_SETTINGS_DIR/log4j2.properties" "$LS_SETTINGS_DIR/log4j2.properties.dist"; 		truncate --size=0 "$LS_SETTINGS_DIR/log4j2.properties"; 	fi
# Fri, 09 Dec 2016 17:49:37 GMT
COPY file:b540f903cdce9f3c92d22e6ec1673d5185797f0f604d4ddc9fdeb6fab1050a8f in / 
# Fri, 09 Dec 2016 17:49:37 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Fri, 09 Dec 2016 17:49:38 GMT
CMD ["-e" ""]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75ea8418708338e40dce9179cfe97fd116831f1601be50fef48ea6011653c986`  
		Last Modified: Mon, 07 Nov 2016 22:57:05 GMT  
		Size: 18.5 MB (18528477 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e2e387eb26a1afa07fb24ab119e8680fc80f43a194890da1d1bb21f76e23c5e`  
		Last Modified: Tue, 08 Nov 2016 19:04:01 GMT  
		Size: 566.9 KB (566896 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eef540699244c02b2a8e14c3b4f335314506cb4b12e15c867535cb20ac429a37`  
		Last Modified: Tue, 08 Nov 2016 19:11:43 GMT  
		Size: 217.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1624a2f8d1142bb2aed22223df10c5416ff37b599ff48c724d23347d37b2b20e`  
		Last Modified: Tue, 08 Nov 2016 19:11:45 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7018f4ec6e0ab2d452cd6ac9600b8cfa25bcd10c603db8ad9107677e9f8fe15e`  
		Last Modified: Tue, 08 Nov 2016 19:12:03 GMT  
		Size: 53.5 MB (53450336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ca3bc2ad3b37551550f7c86d23f4e25066740db6d2f99c3ba99c0f9e0a4d3ec`  
		Last Modified: Tue, 08 Nov 2016 19:11:44 GMT  
		Size: 284.2 KB (284177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3829939e70526b1cb9ed1308aba8b1e3cfe0a28f594a8e1fed143bad35d10c4c`  
		Last Modified: Tue, 08 Nov 2016 22:15:46 GMT  
		Size: 1.4 MB (1357160 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cf20bb3ce62d736e74a65883ccd4dbb035d8329767b3fcf0ec255a2fa6ac4ef`  
		Last Modified: Tue, 08 Nov 2016 22:15:45 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f737f281552e31d566f3dbe3dc54b8392cbcf7ba4b932561b141883629ed7b01`  
		Last Modified: Tue, 08 Nov 2016 22:15:46 GMT  
		Size: 807.9 KB (807933 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1b7aca72edd236c5ccf364c8026eed4ccd4e700047ad5977072174bb921cb63`  
		Last Modified: Tue, 08 Nov 2016 22:15:42 GMT  
		Size: 1.4 KB (1446 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb821ca73c542874d7e6baa4551bc881c9c8b51f5099aad9c16914ccd6453794`  
		Last Modified: Tue, 08 Nov 2016 22:25:54 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7be90372974a3210917ed84c339cecaf7176d287c800cc5f260731e804427ea5`  
		Last Modified: Fri, 09 Dec 2016 17:52:17 GMT  
		Size: 94.9 MB (94944733 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce7e77c6cffff4e66136098a7df6cf5beb1a41754b25795768ed3cce5cca773`  
		Last Modified: Fri, 09 Dec 2016 17:52:01 GMT  
		Size: 2.2 KB (2244 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f42d62f31b9867ef1a7e4a6cf931801e3e06e714644bb70c8a993ab3a83b88f3`  
		Last Modified: Fri, 09 Dec 2016 17:52:00 GMT  
		Size: 305.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
