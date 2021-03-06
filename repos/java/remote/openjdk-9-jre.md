## `java:openjdk-9-jre`

```console
$ docker pull java@sha256:213941d09e9504237c50cc555a155febd3d3a68c3c9d28dbba0414ac2d94199d
```

-	Platforms:
	-	linux; amd64

### `java:openjdk-9-jre` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **208.8 MB (208783395 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c6b96784255b8462731896b8047eae2c094eca2fc4cbaf3be8865c5e676a2214`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 07 Nov 2016 20:31:17 GMT
ADD file:4946b2fd6ad8f6dad8ce2007df355ffa80fbc0d560ac45600bc0305c812bc331 in / 
# Mon, 07 Nov 2016 20:31:17 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:28:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:55:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:55:12 GMT
RUN echo 'deb http://deb.debian.org/debian experimental main' > /etc/apt/sources.list.d/experimental.list
# Tue, 08 Nov 2016 18:55:12 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:55:13 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:55:14 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-9-openjdk-amd64
# Tue, 06 Dec 2016 20:48:50 GMT
ENV JAVA_VERSION=9~b147
# Tue, 06 Dec 2016 20:48:51 GMT
ENV JAVA_DEBIAN_VERSION=9~b147-1
# Tue, 06 Dec 2016 20:49:14 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
```

-	Layers:
	-	`sha256:2c2697cc54a4087031e91659113de235e6bd969754303465add193727dc03fa6`  
		Last Modified: Mon, 07 Nov 2016 20:37:10 GMT  
		Size: 43.3 MB (43262401 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b24aac71f904b1bd9a7a8823a0c8281406c9289c475d7231493950a1ba49f40`  
		Last Modified: Mon, 07 Nov 2016 23:00:27 GMT  
		Size: 20.7 MB (20701379 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efb0752ca2d7bc90ead000036e9713b31fd299ba27e4195368b92d7508fa952d`  
		Last Modified: Tue, 08 Nov 2016 19:17:12 GMT  
		Size: 604.1 KB (604059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f6d2d7ddace0522c98e3e7a7d11acbea41599d65611bb1f55470e531e6537e4`  
		Last Modified: Tue, 08 Nov 2016 19:17:12 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6cfb52cbb05dbc85e834b7ee83fa87a77923b207bfe144121296b483566a971`  
		Last Modified: Tue, 08 Nov 2016 19:17:12 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f35dd66d555fc8408f6e9c8f30919da410fa08d9bf030ba42913522a49b995b4`  
		Last Modified: Tue, 06 Dec 2016 21:08:08 GMT  
		Size: 144.2 MB (144215102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
