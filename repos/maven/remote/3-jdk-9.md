## `maven:3-jdk-9`

```console
$ docker pull maven@sha256:abc7b0b6a0710b4c57b8cbdad7d76b76bc4f6df19bb2e4906d5698d581154722
```

-	Platforms:
	-	linux; amd64

### `maven:3-jdk-9` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **267.8 MB (267771319 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4bb9ae1952a9a8beb36c29c5dc85d92315edaaad4249005896dc452914ad64bc`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Mon, 07 Nov 2016 20:31:17 GMT
ADD file:4946b2fd6ad8f6dad8ce2007df355ffa80fbc0d560ac45600bc0305c812bc331 in / 
# Mon, 07 Nov 2016 20:31:17 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:28:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 07 Nov 2016 22:29:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:54:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:54:38 GMT
RUN echo 'deb http://deb.debian.org/debian experimental main' > /etc/apt/sources.list.d/experimental.list
# Tue, 08 Nov 2016 18:54:38 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:54:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:54:40 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-9-openjdk-amd64
# Tue, 06 Dec 2016 20:48:12 GMT
ENV JAVA_VERSION=9~b147
# Tue, 06 Dec 2016 20:48:13 GMT
ENV JAVA_DEBIAN_VERSION=9~b147-1
# Tue, 06 Dec 2016 20:48:49 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-9-jdk-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 07 Dec 2016 22:07:36 GMT
ARG MAVEN_VERSION=3.3.9
# Wed, 07 Dec 2016 22:07:36 GMT
ARG USER_HOME_DIR=/root
# Wed, 07 Dec 2016 22:07:40 GMT
# ARGS: MAVEN_VERSION=3.3.9 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL http://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz     | tar -xzC /usr/share/maven --strip-components=1   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Wed, 07 Dec 2016 22:07:40 GMT
ENV MAVEN_HOME=/usr/share/maven
# Wed, 07 Dec 2016 22:07:40 GMT
ENV MAVEN_CONFIG=/root/.m2
# Wed, 07 Dec 2016 22:07:41 GMT
COPY file:e3aa30a24fcf60a59710465ac66fc1d53c35590a74fcdd51e12a5cbce393904b in /usr/local/bin/mvn-entrypoint.sh 
# Wed, 07 Dec 2016 22:07:42 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Wed, 07 Dec 2016 22:07:42 GMT
VOLUME [/root/.m2]
# Wed, 07 Dec 2016 22:07:43 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Wed, 07 Dec 2016 22:07:43 GMT
CMD ["mvn"]
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
	-	`sha256:3514ff4b0f0d308024087f10c855ab7412915526a9bba7e3777b0c857e908493`  
		Last Modified: Mon, 07 Nov 2016 23:01:09 GMT  
		Size: 50.8 MB (50774782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e24ab6c2095e0bb84448123a4fa0e15b8240a5bbc1229d146022725a63dd9896`  
		Last Modified: Tue, 08 Nov 2016 19:14:49 GMT  
		Size: 635.5 KB (635542 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f06e8f012ab67aee2075e0e4dc0b50d25067c6982112822d498e4239ea7342c`  
		Last Modified: Tue, 08 Nov 2016 19:14:49 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11ecc3023cb702682496563a3683d719fb6a3cd56d955cea13b376ba92ed0a7a`  
		Last Modified: Tue, 08 Nov 2016 19:14:48 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25a5b2ea4f4645ea13592cc17482ad689df5890718de8335f70321e9a4bae0b3`  
		Last Modified: Tue, 06 Dec 2016 21:05:43 GMT  
		Size: 143.8 MB (143796866 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1904f56713cc306ee938e70f656e0c0c81b62dc78cbc96635b35c41ccdc266d`  
		Last Modified: Wed, 07 Dec 2016 22:17:51 GMT  
		Size: 8.6 MB (8598857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:231be8db27f7817445616536014adff4149766b075d9a6113e27513276e484df`  
		Last Modified: Wed, 07 Dec 2016 22:17:49 GMT  
		Size: 691.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15c49b7d9c614a789454f1876e9faf6b6484e74a8701477a2dbfe5346484ea8b`  
		Last Modified: Wed, 07 Dec 2016 22:17:50 GMT  
		Size: 347.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
