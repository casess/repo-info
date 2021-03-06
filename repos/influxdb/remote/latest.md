## `influxdb:latest`

```console
$ docker pull influxdb@sha256:f47a250b117384e8944a5e8b5bb359a3bc051b60d521de962b44e22b41045418
```

-	Platforms:
	-	linux; amd64

### `influxdb:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **85.4 MB (85423937 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:11072db974c852ed2390c729c39cb6da872e9b28b6bdb6a2cffe47a0cbd71e51`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["influxd"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 19:00:47 GMT
RUN gpg     --keyserver hkp://ha.pool.sks-keyservers.net     --recv-keys 05CE15085FC09D18E99EFB22684A14CF2582E0C5
# Wed, 07 Dec 2016 21:14:49 GMT
ENV INFLUXDB_VERSION=1.1.1
# Wed, 07 Dec 2016 21:14:52 GMT
RUN wget -q https://dl.influxdata.com/influxdb/releases/influxdb_${INFLUXDB_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb_${INFLUXDB_VERSION}_amd64.deb &&     gpg --batch --verify influxdb_${INFLUXDB_VERSION}_amd64.deb.asc influxdb_${INFLUXDB_VERSION}_amd64.deb &&     dpkg -i influxdb_${INFLUXDB_VERSION}_amd64.deb &&     rm -f influxdb_${INFLUXDB_VERSION}_amd64.deb*
# Wed, 07 Dec 2016 21:15:00 GMT
COPY file:3ee2bc0321c2aa2451df7a508649c3a54f0eebc1ef9b8a24967c58105b4d3160 in /etc/influxdb/influxdb.conf 
# Wed, 07 Dec 2016 21:15:01 GMT
EXPOSE 8086/tcp
# Wed, 07 Dec 2016 21:15:01 GMT
VOLUME [/var/lib/influxdb]
# Wed, 07 Dec 2016 21:15:02 GMT
COPY file:812647bc923fb58bd6fba201df6d23a9311547ea81f3a598e86e2b93b2399169 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:15:02 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:15:02 GMT
CMD ["influxd"]
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
	-	`sha256:3a5c2f2069c8ad4411d8d0de5b23f1cc58b73ee10feba4907738119d4305fbb3`  
		Last Modified: Tue, 08 Nov 2016 19:01:13 GMT  
		Size: 6.7 KB (6745 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95878ca6cdfd8005dfe0c5d29f03567fbae6ae4f346107e430854da2b1ffbf30`  
		Last Modified: Wed, 07 Dec 2016 21:16:52 GMT  
		Size: 15.5 MB (15531321 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb8b6d02e00df9277466b18d07763bf080bf6ea11116bd8da8176f1c7247c483`  
		Last Modified: Wed, 07 Dec 2016 21:16:45 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f0eef09d9f394a3ff5f4f1e8dc061ecc1052e27409976101d235ab1f4c3911a`  
		Last Modified: Wed, 07 Dec 2016 21:16:45 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
