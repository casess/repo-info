## `ubuntu:devel`

```console
$ docker pull ubuntu@sha256:cd15f91cdbf7667fbc883965891406fc6cf5d34ddf1ff22a6548d9dcb5e292fb
```

-	Platforms:
	-	linux; amd64

### `ubuntu:devel` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.6 MB (40575438 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b1c420e2fe13ec1b075ce08c3b1581b828dda278d38feb6b4c939d10253d0e3d`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 29 Nov 2016 20:05:10 GMT
ADD file:ba0a65b765b68dc137d4ac427d4a79c1c36581275b7fc20a4183935be0c437e1 in / 
# Tue, 29 Nov 2016 20:05:12 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 29 Nov 2016 20:05:13 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 29 Nov 2016 20:05:14 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 29 Nov 2016 20:05:15 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 29 Nov 2016 20:05:15 GMT
CMD ["/bin/bash"]
```

-	Layers:
	-	`sha256:5b7b2e3f5d7964d8c5e002ed8f455f40787d3a11d61f38994772860360c1c792`  
		Last Modified: Tue, 29 Nov 2016 20:11:08 GMT  
		Size: 40.6 MB (40573201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:016956e825c932a6e0c66956018009a107e686b5b6342b78aed0ff41fda297c0`  
		Last Modified: Tue, 29 Nov 2016 20:10:56 GMT  
		Size: 824.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:414a610539c81b84b14ecfb4d2c4f7cf522f59079c367b5aafaadab449e22c3c`  
		Last Modified: Tue, 29 Nov 2016 20:10:57 GMT  
		Size: 389.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85ff7313aa238b9c1b00253f16caab7652654609a191520bc22c13273719cae6`  
		Last Modified: Tue, 29 Nov 2016 20:10:57 GMT  
		Size: 862.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:280884b8dbc96cd34cfb375dde5f08f04b1d74ad319f71f9404fe402bb4c04c9`  
		Last Modified: Tue, 29 Nov 2016 20:10:58 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
