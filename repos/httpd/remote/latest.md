## `httpd:latest`

```console
$ docker pull httpd@sha256:10fd24b8d20ffd15cb21d49529be5952d828ba3f269564cc8ebe60053293ceba
```

-	Platforms:
	-	linux; amd64

### `httpd:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **66.7 MB (66735320 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ff3a8919cd8868bc4e90cc4aa60f3ae537e921ef9fa345d60249b3b4b0451596`
-	Default Command: `["httpd-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 19:53:04 GMT
ENV HTTPD_PREFIX=/usr/local/apache2
# Tue, 08 Nov 2016 19:53:04 GMT
ENV PATH=/usr/local/apache2/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 08 Nov 2016 19:53:05 GMT
RUN mkdir -p "$HTTPD_PREFIX" 	&& chown www-data:www-data "$HTTPD_PREFIX"
# Tue, 08 Nov 2016 19:53:06 GMT
WORKDIR /usr/local/apache2
# Tue, 06 Dec 2016 20:43:40 GMT
ENV NGHTTP2_VERSION=1.17.0-1
# Tue, 06 Dec 2016 20:43:41 GMT
RUN { 		echo 'deb http://deb.debian.org/debian stretch main'; 	} > /etc/apt/sources.list.d/stretch.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release n=stretch'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: libnghttp2*'; 		echo "Pin: version $NGHTTP2_VERSION"; 		echo 'Pin-Priority: 990'; 		echo; 	} > /etc/apt/preferences.d/unstable-nghttp2
# Tue, 06 Dec 2016 20:43:58 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		libapr1 		libaprutil1 		libaprutil1-ldap 		libapr1-dev 		libaprutil1-dev 		liblua5.2-0 		libnghttp2-14=$NGHTTP2_VERSION 		libpcre++0 		libssl1.0.0 		libxml2 	&& rm -r /var/lib/apt/lists/*
# Tue, 06 Dec 2016 20:43:58 GMT
ENV HTTPD_VERSION=2.4.23
# Tue, 06 Dec 2016 20:43:59 GMT
ENV HTTPD_SHA1=5101be34ac4a509b245adb70a56690a84fcc4e7f
# Tue, 06 Dec 2016 20:43:59 GMT
ENV HTTPD_BZ2_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=httpd/httpd-2.4.23.tar.bz2
# Tue, 06 Dec 2016 20:43:59 GMT
ENV HTTPD_ASC_URL=https://www.apache.org/dist/httpd/httpd-2.4.23.tar.bz2.asc
# Tue, 06 Dec 2016 20:45:08 GMT
RUN set -x 	&& buildDeps=" 		bzip2 		ca-certificates 		gcc 		libnghttp2-dev=$NGHTTP2_VERSION 		liblua5.2-dev 		libpcre++-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		make 		wget 	" 	&& apt-get update 	&& apt-get install -y --no-install-recommends -V $buildDeps 	&& rm -r /var/lib/apt/lists/* 		&& wget -O httpd.tar.bz2 "$HTTPD_BZ2_URL" 	&& echo "$HTTPD_SHA1 *httpd.tar.bz2" | sha1sum -c - 	&& wget -O httpd.tar.bz2.asc "$HTTPD_ASC_URL" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys A93D62ECC3C8EA12DB220EC934EA76E6791485A8 	&& gpg --batch --verify httpd.tar.bz2.asc httpd.tar.bz2 	&& rm -r "$GNUPGHOME" httpd.tar.bz2.asc 		&& mkdir -p src 	&& tar -xf httpd.tar.bz2 -C src --strip-components=1 	&& rm httpd.tar.bz2 	&& cd src 		&& ./configure 		--prefix="$HTTPD_PREFIX" 		--enable-mods-shared=reallyall 	&& make -j "$(nproc)" 	&& make install 		&& cd .. 	&& rm -r src man manual 		&& sed -ri 		-e 's!^(\s*CustomLog)\s+\S+!\1 /proc/self/fd/1!g' 		-e 's!^(\s*ErrorLog)\s+\S+!\1 /proc/self/fd/2!g' 		"$HTTPD_PREFIX/conf/httpd.conf" 		&& apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Dec 2016 20:45:08 GMT
COPY file:761e313354b918b6cd7ea99975a4f6b53ff5381ba689bab2984aec4dab597215 in /usr/local/bin/ 
# Tue, 06 Dec 2016 20:45:09 GMT
EXPOSE 80/tcp
# Tue, 06 Dec 2016 20:45:09 GMT
CMD ["httpd-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a11d6b8e2face8ea979cca66f15bb9455ff660b07bf5507652f2e108e7e023e4`  
		Last Modified: Tue, 08 Nov 2016 19:54:44 GMT  
		Size: 151.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c22afc84eb8c67069e4ef6747611efcd517fc66d8fb821adf740f1774c3efe16`  
		Last Modified: Tue, 06 Dec 2016 20:46:20 GMT  
		Size: 333.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8cee93cc2580dc256330102b057510684cbfedf3d21eaef86507e75a59f36c13`  
		Last Modified: Tue, 06 Dec 2016 20:46:24 GMT  
		Size: 12.9 MB (12856262 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad6ee84c236c2bb3efd7824acc5fbda45d867cd9a4fb7074dc7b5b3ef7ae224a`  
		Last Modified: Tue, 06 Dec 2016 20:46:22 GMT  
		Size: 2.5 MB (2521294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f02435546328ba6f66c25c1f94963c3e2d90c6ca3100ce61d47ca1fb74895d71`  
		Last Modified: Tue, 06 Dec 2016 20:46:20 GMT  
		Size: 291.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
