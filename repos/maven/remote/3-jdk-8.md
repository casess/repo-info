## `maven:3-jdk-8`

```console
$ docker pull maven@sha256:a7fd540bc273b7c4f1193fbcd46127ad3912fd095a251382f4e4312b9ac85e9d
```

-	Platforms:
	-	linux; amd64

### `maven:3-jdk-8` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **252.0 MB (251970441 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b2ef69e414f5e8b727377e3fc347f4daa5706ac5af2370a137aeba2368aaa7ed`
-	Entrypoint: `["\/usr\/local\/bin\/mvn-entrypoint.sh"]`
-	Default Command: `["mvn"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 07 Nov 2016 22:27:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:50:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:52:55 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Tue, 08 Nov 2016 18:52:56 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:52:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:52:57 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
# Tue, 08 Nov 2016 18:52:58 GMT
ENV JAVA_VERSION=8u111
# Tue, 08 Nov 2016 18:52:58 GMT
ENV JAVA_DEBIAN_VERSION=8u111-b14-2~bpo8+1
# Tue, 08 Nov 2016 18:52:59 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20140324
# Tue, 08 Nov 2016 18:53:49 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 08 Nov 2016 18:53:51 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 08 Nov 2016 22:27:28 GMT
ARG MAVEN_VERSION=3.3.9
# Tue, 08 Nov 2016 22:27:29 GMT
ARG USER_HOME_DIR=/root
# Thu, 10 Nov 2016 07:06:00 GMT
# ARGS: MAVEN_VERSION=3.3.9 USER_HOME_DIR=/root
RUN mkdir -p /usr/share/maven /usr/share/maven/ref   && curl -fsSL http://apache.osuosl.org/maven/maven-3/$MAVEN_VERSION/binaries/apache-maven-$MAVEN_VERSION-bin.tar.gz     | tar -xzC /usr/share/maven --strip-components=1   && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn
# Thu, 10 Nov 2016 07:06:00 GMT
ENV MAVEN_HOME=/usr/share/maven
# Thu, 10 Nov 2016 07:06:01 GMT
ENV MAVEN_CONFIG=/root/.m2
# Thu, 10 Nov 2016 07:06:01 GMT
COPY file:e3aa30a24fcf60a59710465ac66fc1d53c35590a74fcdd51e12a5cbce393904b in /usr/local/bin/mvn-entrypoint.sh 
# Thu, 10 Nov 2016 07:06:02 GMT
COPY file:b3fc14e8337e0079a4e97eace880b4b7cddc0dc0ea733de80749f78fe1eb089a in /usr/share/maven/ref/ 
# Thu, 10 Nov 2016 07:06:02 GMT
VOLUME [/root/.m2]
# Thu, 10 Nov 2016 07:06:03 GMT
ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
# Thu, 10 Nov 2016 07:06:03 GMT
CMD ["mvn"]
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
	-	`sha256:88b459c9f665cc39ff5fc09071b5dada4dad766573d962276f999d0c466d5405`  
		Last Modified: Mon, 07 Nov 2016 22:57:53 GMT  
		Size: 42.5 MB (42498243 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:690dbea0e4ca2996b70b102af3c4639bbd2f1b8fcbb2bf602a0a82f74d54bf51`  
		Last Modified: Tue, 08 Nov 2016 18:59:32 GMT  
		Size: 593.3 KB (593322 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e401cdd6f18ec55ddebd090e4a39f0db17e1eb68f9db7e2233b1438f6f7dcf5`  
		Last Modified: Tue, 08 Nov 2016 19:06:16 GMT  
		Size: 216.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a58186ddf9a07069e7d41ba4c1d56d5c20ad55222483c80dd3425942952c3224`  
		Last Modified: Tue, 08 Nov 2016 19:06:16 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49999ed55bc4d3fce78396b5fc5d7b50e35bd4355625be799b7da8cf71b91723`  
		Last Modified: Tue, 08 Nov 2016 19:06:55 GMT  
		Size: 130.1 MB (130108814 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb40561aad8f0aaca0d47fd663fce6d8799737cecd64c0a12da5c670fa154b9e`  
		Last Modified: Tue, 08 Nov 2016 19:06:19 GMT  
		Size: 284.2 KB (284242 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ce0e24588f2b2ef1bdef51115b00555e63b73224cec47d2a8d080026448881a`  
		Last Modified: Thu, 10 Nov 2016 07:06:19 GMT  
		Size: 8.6 MB (8598852 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35430242cb99852ddd9db8e015434836e902940cdf6e28061e0804a0bcf8e702`  
		Last Modified: Thu, 10 Nov 2016 07:06:17 GMT  
		Size: 695.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4af041dcf95990868d012d8971672f0f8fbcea19ccb5df3da0bb88544c2c621`  
		Last Modified: Thu, 10 Nov 2016 07:06:16 GMT  
		Size: 349.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
