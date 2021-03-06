## `golang:wheezy`

```console
$ docker pull golang@sha256:51ac44aa7c5f70494622cfb5c937c2489dfdcea8eec2575f8e37e65a6a184198
```

-	Platforms:
	-	linux; amd64

### `golang:wheezy` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **200.9 MB (200858633 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:96cc22964add7c6c04b514c47fddfff812a005f759de03bca6189f0e3ce20b76`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 07 Nov 2016 20:33:23 GMT
ADD file:6fdd763c7bbd245e1c98a3c937b10dcc9b5383d5d0bcda22e8cbfeb6746932da in / 
# Mon, 07 Nov 2016 20:33:24 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:32:01 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 07 Nov 2016 22:32:19 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 19:35:28 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Thu, 01 Dec 2016 23:40:25 GMT
ENV GOLANG_VERSION=1.7.4
# Thu, 01 Dec 2016 23:40:26 GMT
ENV GOLANG_DOWNLOAD_URL=https://golang.org/dl/go1.7.4.linux-amd64.tar.gz
# Thu, 01 Dec 2016 23:40:26 GMT
ENV GOLANG_DOWNLOAD_SHA256=47fda42e46b4c3ec93fa5d4d4cc6a748aa3f9411a2a2b7e08e3a6d80d753ec8b
# Thu, 01 Dec 2016 23:40:35 GMT
RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz 	&& echo "$GOLANG_DOWNLOAD_SHA256  golang.tar.gz" | sha256sum -c - 	&& tar -C /usr/local -xzf golang.tar.gz 	&& rm golang.tar.gz
# Thu, 01 Dec 2016 23:40:35 GMT
ENV GOPATH=/go
# Thu, 01 Dec 2016 23:40:35 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 01 Dec 2016 23:40:36 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Thu, 01 Dec 2016 23:40:36 GMT
WORKDIR /go
# Thu, 01 Dec 2016 23:40:37 GMT
COPY file:f6191f2c86edc9343569339f101facba47e886e33e29d70da6916ca6b1101a53 in /usr/local/bin/ 
```

-	Layers:
	-	`sha256:c952bb7239f0af4620e24e9dd88d56be7d4469563f840a911c7721321431d9cb`  
		Last Modified: Mon, 07 Nov 2016 20:42:41 GMT  
		Size: 37.2 MB (37208582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df674db1f5c55ee81a339f27b2104d63dee9bb1c6c6ab199c8b8a365b11dad1c`  
		Last Modified: Mon, 07 Nov 2016 23:05:45 GMT  
		Size: 6.7 MB (6749846 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a97590af2ddaf78e699b922536a6f7c27288dfcb51170ab3ad3e31dc9f6959f0`  
		Last Modified: Mon, 07 Nov 2016 23:06:14 GMT  
		Size: 37.4 MB (37366492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2727f2714cc443069ac3f57b891cddd93f170223c961bf68ffbd2e1700e8be2f`  
		Last Modified: Tue, 08 Nov 2016 19:36:13 GMT  
		Size: 36.4 MB (36446322 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56e4f3b398ede471172ecd98d96bd3db454d75637a89a301213f4bf52e60769f`  
		Last Modified: Thu, 01 Dec 2016 23:48:45 GMT  
		Size: 83.1 MB (83085917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d3c63919bcc098bf59810a1ce34931d54dcfe44330dfeac388a064b68a536c7`  
		Last Modified: Thu, 01 Dec 2016 23:48:21 GMT  
		Size: 123.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7290b31bf5a44d0650547b776d4a15a65cd738d53e68baabd3c4e2d16943ee5c`  
		Last Modified: Thu, 01 Dec 2016 23:48:21 GMT  
		Size: 1.4 KB (1351 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
