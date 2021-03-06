## `cassandra:latest`

```console
$ docker pull cassandra@sha256:f5b1391b457ead432dc05d34797212f038bd9bd4f0b0260d90ce74e53cbe7ca9
```

-	Platforms:
	-	linux; amd64

### `cassandra:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **162.0 MB (161956595 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b5782481efe9b62b1eea16ec8748d2ca577603e5600a60c29521910c38233718`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["cassandra","-f"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 20:30:39 GMT
RUN awk '$1 ~ "^deb" { $3 = $3 "-backports"; print; exit }' /etc/apt/sources.list > /etc/apt/sources.list.d/backports.list
# Tue, 08 Nov 2016 18:51:31 GMT
RUN groupadd -r cassandra --gid=999 && useradd -r -g cassandra --uid=999 cassandra
# Tue, 08 Nov 2016 18:51:39 GMT
ENV GOSU_VERSION=1.7
# Tue, 08 Nov 2016 18:51:58 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Mon, 14 Nov 2016 22:43:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends libjemalloc1 && rm -rf /var/lib/apt/lists/*
# Mon, 14 Nov 2016 22:43:34 GMT
ENV GPG_KEYS=514A2AD631A57A16DD0047EC749D6EEC0353B12C 	A26E528B271F19B9E5D8E19EA278B781FE4B2BDA
# Mon, 14 Nov 2016 22:43:37 GMT
RUN set -ex 	&& for key in $GPG_KEYS; do 		apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Mon, 14 Nov 2016 22:45:57 GMT
RUN echo 'deb http://www.apache.org/dist/cassandra/debian 39x main' >> /etc/apt/sources.list.d/cassandra.list
# Mon, 14 Nov 2016 22:45:58 GMT
ENV CASSANDRA_VERSION=3.9
# Mon, 14 Nov 2016 22:46:31 GMT
RUN apt-get update 	&& apt-get install -y cassandra="$CASSANDRA_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Mon, 14 Nov 2016 22:46:32 GMT
RUN sed -ri 's/^(JVM_PATCH_VERSION)=.*/\1=25/' /etc/cassandra/cassandra-env.sh
# Mon, 14 Nov 2016 22:46:33 GMT
ENV CASSANDRA_CONFIG=/etc/cassandra
# Mon, 14 Nov 2016 22:46:33 GMT
COPY file:fe6ed91be8debf19da443f09935b578bf6599e644b7a670bf7048d33fb2efa9e in /docker-entrypoint.sh 
# Mon, 14 Nov 2016 22:46:33 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 14 Nov 2016 22:46:34 GMT
RUN mkdir -p /var/lib/cassandra "$CASSANDRA_CONFIG" 	&& chown -R cassandra:cassandra /var/lib/cassandra "$CASSANDRA_CONFIG" 	&& chmod 777 /var/lib/cassandra "$CASSANDRA_CONFIG"
# Mon, 14 Nov 2016 22:46:35 GMT
VOLUME [/var/lib/cassandra]
# Mon, 14 Nov 2016 22:46:35 GMT
EXPOSE 7000/tcp 7001/tcp 7199/tcp 9042/tcp 9160/tcp
# Mon, 14 Nov 2016 22:46:36 GMT
CMD ["cassandra" "-f"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4bd24d76b787add0667caa04ca4427ac36631f5927588c78adfb51048c6e711`  
		Last Modified: Mon, 07 Nov 2016 20:35:28 GMT  
		Size: 216.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ccb1c31767242926e928c13ce22ffab8274502feb989c9dcfc6426bb87a7b6a`  
		Last Modified: Tue, 08 Nov 2016 18:53:44 GMT  
		Size: 2.0 KB (2047 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7ffd548f7384d0c39921aca017c4e99a0f77980c00ed15bf361c0067d057efe`  
		Last Modified: Tue, 08 Nov 2016 18:53:46 GMT  
		Size: 1.2 MB (1216432 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6f6138be8041fbb587135a5d96089598f72031228fe643d40d370cd10ad3118`  
		Last Modified: Mon, 14 Nov 2016 22:46:51 GMT  
		Size: 173.7 KB (173685 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:756363f453c928fd9da1f152db398ecfc6421827ae250449b04bfe5d27885ab0`  
		Last Modified: Mon, 14 Nov 2016 22:46:50 GMT  
		Size: 18.3 KB (18301 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26258521e648f3947cc9ce189a29ddb4ea00c88df754f8d15a48f2619b9f74da`  
		Last Modified: Mon, 14 Nov 2016 22:50:06 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb207e348163b6e437a4e16ecf47546799be003e51267782e261d006457453fb`  
		Last Modified: Mon, 14 Nov 2016 22:50:25 GMT  
		Size: 109.2 MB (109156317 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f9a7ac16b1d5331314095d7e46e2ee3392789caa93514cb74aef97e708420db`  
		Last Modified: Mon, 14 Nov 2016 22:50:01 GMT  
		Size: 4.4 KB (4397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49e0632fe1f146470a3f7216b41a6902ba74989340ad8c9873c7481804aadcc7`  
		Last Modified: Mon, 14 Nov 2016 22:50:02 GMT  
		Size: 721.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba775b0b41f4ccab25c02332345240d96fb3b7cf577c04e14f5eef0d0acc08c7`  
		Last Modified: Mon, 14 Nov 2016 22:50:01 GMT  
		Size: 27.3 KB (27268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
