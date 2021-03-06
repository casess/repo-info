## `tomcat:6-jre7`

```console
$ docker pull tomcat@sha256:ac6df4ca8b0376a038852df71c97085b7d781fba905af4cfa7add7c287ab07af
```

-	Platforms:
	-	linux; amd64

### `tomcat:6-jre7` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **159.7 MB (159746398 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:625e3c9ca315dfc7e925c6f080cd5393f0dc2698aaecaf9f7682ea65197c6183`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:52:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 18:52:12 GMT
ENV LANG=C.UTF-8
# Tue, 08 Nov 2016 18:52:13 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 08 Nov 2016 18:52:13 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
# Tue, 08 Nov 2016 18:52:14 GMT
ENV JAVA_VERSION=7u111
# Tue, 08 Nov 2016 18:52:14 GMT
ENV JAVA_DEBIAN_VERSION=7u111-2.6.7-2~deb8u1
# Tue, 08 Nov 2016 18:52:54 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 08 Nov 2016 23:13:03 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Tue, 08 Nov 2016 23:13:04 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 08 Nov 2016 23:13:05 GMT
RUN mkdir -p "$CATALINA_HOME"
# Tue, 08 Nov 2016 23:13:05 GMT
WORKDIR /usr/local/tomcat
# Tue, 08 Nov 2016 23:13:06 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Tue, 08 Nov 2016 23:13:06 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Tue, 08 Nov 2016 23:13:06 GMT
ENV OPENSSL_VERSION=1.0.2j-1
# Thu, 17 Nov 2016 23:36:48 GMT
RUN { 		echo 'deb http://deb.debian.org/debian stretch main'; 	} > /etc/apt/sources.list.d/stretch.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release n=stretch'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: openssl libssl*'; 		echo "Pin: version $OPENSSL_VERSION"; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/stretch-openssl
# Thu, 17 Nov 2016 23:37:01 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 		openssl="$OPENSSL_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Thu, 17 Nov 2016 23:37:01 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 80FF76D88A969FE46108558A80B953A041E49465 8B39757B1D8A994DF2433ED58B3A601F08C975E5 A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 B3F49CD3B9BD2996DA90F817ED3873F5D3262722 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 17 Nov 2016 23:37:12 GMT
RUN set -ex; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Thu, 17 Nov 2016 23:37:12 GMT
ENV TOMCAT_MAJOR=6
# Thu, 17 Nov 2016 23:37:13 GMT
ENV TOMCAT_VERSION=6.0.48
# Thu, 17 Nov 2016 23:37:13 GMT
ENV TOMCAT_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-6/v6.0.48/bin/apache-tomcat-6.0.48.tar.gz
# Thu, 17 Nov 2016 23:37:14 GMT
ENV TOMCAT_ASC_URL=https://www.apache.org/dist/tomcat/tomcat-6/v6.0.48/bin/apache-tomcat-6.0.48.tar.gz.asc
# Thu, 17 Nov 2016 23:37:49 GMT
RUN set -x 		&& wget -O tomcat.tar.gz "$TOMCAT_TGZ_URL" 	&& wget -O tomcat.tar.gz.asc "$TOMCAT_ASC_URL" 	&& gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz 	&& tar -xvf tomcat.tar.gz --strip-components=1 	&& rm bin/*.bat 	&& rm tomcat.tar.gz* 		&& nativeBuildDir="$(mktemp -d)" 	&& tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1 	&& nativeBuildDeps=" 		gcc 		libapr1-dev 		libssl-dev 		make 		openjdk-${JAVA_VERSION%%[-~bu]*}-jdk=$JAVA_DEBIAN_VERSION 	" 	&& apt-get update && apt-get install -y --no-install-recommends $nativeBuildDeps && rm -rf /var/lib/apt/lists/* 	&& ( 		export CATALINA_HOME="$PWD" 		&& cd "$nativeBuildDir/native" 		&& ./configure 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes 		&& make -j$(nproc) 		&& make install 	) 	&& apt-get purge -y --auto-remove $nativeBuildDeps 	&& rm -rf "$nativeBuildDir" 	&& rm bin/tomcat-native.tar.gz
# Thu, 17 Nov 2016 23:37:50 GMT
EXPOSE 8080/tcp
# Thu, 17 Nov 2016 23:37:50 GMT
CMD ["catalina.sh" "run"]
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
	-	`sha256:7c6c48f4275c3aaf22ac521477e2cb076c7bac5f5083ffad6ea09262591239bc`  
		Last Modified: Tue, 08 Nov 2016 19:04:01 GMT  
		Size: 243.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:887691f35f8fa16d96ad671f685d40ceb95046bad8f49d98020e02b53560587f`  
		Last Modified: Tue, 08 Nov 2016 19:04:20 GMT  
		Size: 78.2 MB (78154492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdd1cefebf67ecd133fb45541b8326b8ae7c72192b8d552b245c113dccab4677`  
		Last Modified: Thu, 17 Nov 2016 23:47:39 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:598674c5963feec5c64b38d49bab2790776aa842999f6b6685c917b7f05f9da3`  
		Last Modified: Thu, 17 Nov 2016 23:47:40 GMT  
		Size: 332.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfa880bbc1a2a4f0b1e53cda538481881f113ea0170647f437f71f94c0641d35`  
		Last Modified: Thu, 17 Nov 2016 23:47:40 GMT  
		Size: 3.0 MB (3002384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7977017a9b6a1297b5eed8bab3b050125a70eeb4aa46ecbcf53fc9de985ef32f`  
		Last Modified: Thu, 17 Nov 2016 23:47:40 GMT  
		Size: 274.4 KB (274390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2755cfe454e123c6a5accf0a1fac6667b2f3f654aa7845842f7c72a93208b903`  
		Last Modified: Thu, 17 Nov 2016 23:47:40 GMT  
		Size: 7.9 MB (7862051 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
