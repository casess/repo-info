## `ubuntu:latest`

```console
$ docker pull ubuntu@sha256:3b64c309deae7ab0f7dbdd42b6b326261ccd6261da5d88396439353162703fb5
```

-	Platforms:
	-	linux; amd64

### `ubuntu:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **50.1 MB (50098887 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4ca3a192ff2a5b7e225e81dc006b6379c10776ed3619757a65608cb72de0a7f6`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 29 Nov 2016 20:04:32 GMT
ADD file:2ca910a8c0cef4144f7c4ef779f9d85d5f451a776c3c67fc83a7a461de73e7d7 in / 
# Tue, 29 Nov 2016 20:04:33 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 29 Nov 2016 20:04:34 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 29 Nov 2016 20:04:35 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 29 Nov 2016 20:04:36 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 29 Nov 2016 20:04:37 GMT
CMD ["/bin/bash"]
```

-	Layers:
	-	`sha256:af49a5ceb2a56a8232402f5868cdb13dfdae5d66a62955a73e647e16e9f30a63`  
		Last Modified: Tue, 29 Nov 2016 20:08:29 GMT  
		Size: 50.1 MB (50096701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f9757b472e7962a4304d4af61630e2cde66129218135b4093a43b9db8942c34`  
		Last Modified: Tue, 29 Nov 2016 20:08:15 GMT  
		Size: 824.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e931b117db38a05b9d0bbd28ca99a0abe5236a0026d88b3db804f520e59977ec`  
		Last Modified: Tue, 29 Nov 2016 20:08:19 GMT  
		Size: 518.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:47b5e16c0811b08c1cf3198fa5ac0b920946ac538a0a0030627d19763e2fa212`  
		Last Modified: Tue, 29 Nov 2016 20:08:15 GMT  
		Size: 682.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9332eaf1a55b72fb779d2f249b65855c623c8ce7be83c822b7d80115ef5a3af3`  
		Last Modified: Tue, 29 Nov 2016 20:08:15 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
