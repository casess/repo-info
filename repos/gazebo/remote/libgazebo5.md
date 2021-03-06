## `gazebo:libgazebo5`

```console
$ docker pull gazebo@sha256:e41bdf012545d9949496070a1313f834bda1767347c6168cad5ea517a761d17f
```

-	Platforms:
	-	linux; amd64

### `gazebo:libgazebo5` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **490.5 MB (490453286 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b02d4959a7910c3934faa028e86b0ea6beb1b222015192f0721b1c8c51d4882b`
-	Entrypoint: `["\/gzserver_entrypoint.sh"]`
-	Default Command: `["gzserver"]`

```dockerfile
# Tue, 29 Nov 2016 20:04:12 GMT
ADD file:ded1872c7b5d88e55fedfb512f1c0d02f06b8235c702c984bedd589861c0cd46 in / 
# Tue, 29 Nov 2016 20:04:13 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 29 Nov 2016 20:04:14 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 29 Nov 2016 20:04:15 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 29 Nov 2016 20:04:16 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 29 Nov 2016 20:04:16 GMT
CMD ["/bin/bash"]
# Tue, 29 Nov 2016 22:50:17 GMT
MAINTAINER Steven Peters scpeters+buildfarm@osrfoundation.org
# Tue, 29 Nov 2016 22:50:19 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys D2486D2DD83DB69272AFE98867170598AF249743
# Tue, 29 Nov 2016 22:50:21 GMT
RUN echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-latest.list
# Tue, 29 Nov 2016 22:56:09 GMT
RUN apt-get update && apt-get install -q -y     gazebo5=5.3.0*     && rm -rf /var/lib/apt/lists/*
# Tue, 29 Nov 2016 22:56:10 GMT
EXPOSE 11345/tcp
# Tue, 29 Nov 2016 22:56:10 GMT
COPY file:5869092530419fa234b6d43a32bf8687d0d509fced55597b2e241dd58b3d1335 in / 
# Tue, 29 Nov 2016 22:56:11 GMT
ENTRYPOINT ["/gzserver_entrypoint.sh"]
# Tue, 29 Nov 2016 22:56:11 GMT
CMD ["gzserver"]
# Tue, 29 Nov 2016 23:05:44 GMT
MAINTAINER Steven Peters scpeters+buildfarm@osrfoundation.org
# Tue, 29 Nov 2016 23:10:00 GMT
RUN apt-get update && apt-get install -q -y     libgazebo5-dev=5.3.0*     && rm -rf /var/lib/apt/lists/*
```

-	Layers:
	-	`sha256:04cf3f0e25b66692b614f4c294f2855c0f1ae522e80eb07ca54acb46e8487c27`  
		Last Modified: Tue, 29 Nov 2016 20:07:09 GMT  
		Size: 65.7 MB (65699456 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5b45e963ba03647f19009036377b492415543fa3a79fdfa6c9ea8bef77bc3ba`  
		Last Modified: Tue, 29 Nov 2016 20:06:50 GMT  
		Size: 71.6 KB (71562 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5c78fda4e14ffefdd419326d60773ea712471f864f81e6c50fde1c193285989`  
		Last Modified: Tue, 29 Nov 2016 20:06:50 GMT  
		Size: 365.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:193d4969ca79a1eae056433a65e49d650e697d55f280d568f213d0eccc23ac50`  
		Last Modified: Tue, 29 Nov 2016 20:06:51 GMT  
		Size: 681.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d709551f96308ca25c1a8435f6fb8d3a37e8c53a172dd0a32c9028082c171c6f`  
		Last Modified: Tue, 29 Nov 2016 20:06:50 GMT  
		Size: 161.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5946e2fe1ba9307f6bc92a30ada5a29a90b266d66ffcbb4e2e54dede07ec76cc`  
		Last Modified: Tue, 29 Nov 2016 23:29:44 GMT  
		Size: 13.1 KB (13107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee0bbbd82b5433f322b8a5290c7d640e866d9f4fd8cee5204eb6b8fca9181832`  
		Last Modified: Tue, 29 Nov 2016 23:29:46 GMT  
		Size: 258.1 KB (258140 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8251cf0e565eee55c50f90937e48f4312d7afed97c98c34a93077cafbdd01a6d`  
		Last Modified: Tue, 29 Nov 2016 23:31:24 GMT  
		Size: 164.5 MB (164504280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16bcb3cbb6baee19aaa2aea692fbbfc0b3122fcd35c777e666d1181a6dd3be3f`  
		Last Modified: Tue, 29 Nov 2016 23:30:42 GMT  
		Size: 190.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81ee92cb42b18c72db7ea3822a26e021e49e9f5a71b10dda4df048cab6451f97`  
		Last Modified: Tue, 29 Nov 2016 23:37:30 GMT  
		Size: 259.9 MB (259905344 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
