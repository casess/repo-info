<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `consul`

-	[`consul:latest`](#consullatest)
-	[`consul:0.7.1`](#consul071)

## `consul:latest`

```console
$ docker pull consul@sha256:4a6a91f7981d2c78b8746075859a2ff5ae938bae5da3b9b5637714fc7810fbb2
```

-	Platforms:
	-	linux; amd64

### `consul:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **11.5 MB (11497713 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:40d2b6c205a626671dcadf5dd342884a95fde30731c6011bfd4c586637d62c0b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["agent","-dev","-client","0.0.0.0"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 18 Oct 2016 22:59:33 GMT
MAINTAINER James Phillips <james@hashicorp.com> (@slackpad)
# Fri, 11 Nov 2016 20:43:30 GMT
ENV CONSUL_VERSION=0.7.1
# Fri, 11 Nov 2016 20:43:30 GMT
ENV DOCKER_BASE_VERSION=0.0.4
# Fri, 11 Nov 2016 20:43:32 GMT
RUN addgroup consul &&     adduser -S -G consul consul
# Fri, 11 Nov 2016 20:43:41 GMT
RUN apk add --no-cache ca-certificates curl gnupg libcap openssl &&     gpg --recv-keys 91A6E7F85D05C65630BEF18951852D87348FFC4C &&     mkdir -p /tmp/build &&     cd /tmp/build &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     grep ${DOCKER_BASE_VERSION}_linux_amd64.zip docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS | sha256sum -c &&     unzip docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     cp bin/gosu bin/dumb-init /bin &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify consul_${CONSUL_VERSION}_SHA256SUMS.sig consul_${CONSUL_VERSION}_SHA256SUMS &&     grep consul_${CONSUL_VERSION}_linux_amd64.zip consul_${CONSUL_VERSION}_SHA256SUMS | sha256sum -c &&     unzip -d /bin consul_${CONSUL_VERSION}_linux_amd64.zip &&     cd /tmp &&     rm -rf /tmp/build &&     apk del gnupg openssl &&     rm -rf /root/.gnupg
# Fri, 11 Nov 2016 20:43:42 GMT
RUN mkdir -p /consul/data &&     mkdir -p /consul/config &&     chown -R consul:consul /consul
# Fri, 11 Nov 2016 20:43:43 GMT
VOLUME [/consul/data]
# Fri, 11 Nov 2016 20:43:43 GMT
EXPOSE 8300/tcp
# Fri, 11 Nov 2016 20:43:43 GMT
EXPOSE 8301/tcp 8301/udp 8302/tcp 8302/udp
# Fri, 11 Nov 2016 20:43:44 GMT
EXPOSE 8400/tcp 8500/tcp 8600/tcp 8600/udp
# Fri, 11 Nov 2016 20:43:44 GMT
COPY file:de6c9a0e693ae46a375c565826f2071715281bba7f165975eb8537acd0d96ff4 in /usr/local/bin/docker-entrypoint.sh 
# Fri, 11 Nov 2016 20:43:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 11 Nov 2016 20:43:45 GMT
CMD ["agent" "-dev" "-client" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba641cbc2e36933f14d63e3d82fd857ee6bf7e7348150bf20671a90e9f3fa563`  
		Last Modified: Fri, 11 Nov 2016 20:44:01 GMT  
		Size: 1.3 KB (1273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a0885c9cb15f564abedc944841d72bcf7f6c80d482d1bb5ea2fd698620043d9`  
		Last Modified: Fri, 11 Nov 2016 20:44:08 GMT  
		Size: 9.2 MB (9181710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8baed0bc57fe7a7365d287d6019b0f64574dbe53044388fd7f64a03f5a4df7c4`  
		Last Modified: Fri, 11 Nov 2016 20:44:01 GMT  
		Size: 143.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:048b29acd8e7714efafe8b9c91acbf9119ff8cf5eb67143b85ec501d6cc3875d`  
		Last Modified: Fri, 11 Nov 2016 20:44:02 GMT  
		Size: 1.6 KB (1629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `consul:0.7.1`

```console
$ docker pull consul@sha256:4a6a91f7981d2c78b8746075859a2ff5ae938bae5da3b9b5637714fc7810fbb2
```

-	Platforms:
	-	linux; amd64

### `consul:0.7.1` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **11.5 MB (11497713 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:40d2b6c205a626671dcadf5dd342884a95fde30731c6011bfd4c586637d62c0b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["agent","-dev","-client","0.0.0.0"]`

```dockerfile
# Tue, 18 Oct 2016 20:31:22 GMT
ADD file:7afbc23fda8b0b3872623c16af8e3490b2cee951aed14b3794389c2f946cc8c7 in / 
# Tue, 18 Oct 2016 22:59:33 GMT
MAINTAINER James Phillips <james@hashicorp.com> (@slackpad)
# Fri, 11 Nov 2016 20:43:30 GMT
ENV CONSUL_VERSION=0.7.1
# Fri, 11 Nov 2016 20:43:30 GMT
ENV DOCKER_BASE_VERSION=0.0.4
# Fri, 11 Nov 2016 20:43:32 GMT
RUN addgroup consul &&     adduser -S -G consul consul
# Fri, 11 Nov 2016 20:43:41 GMT
RUN apk add --no-cache ca-certificates curl gnupg libcap openssl &&     gpg --recv-keys 91A6E7F85D05C65630BEF18951852D87348FFC4C &&     mkdir -p /tmp/build &&     cd /tmp/build &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/docker-base/${DOCKER_BASE_VERSION}/docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS.sig docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS &&     grep ${DOCKER_BASE_VERSION}_linux_amd64.zip docker-base_${DOCKER_BASE_VERSION}_SHA256SUMS | sha256sum -c &&     unzip docker-base_${DOCKER_BASE_VERSION}_linux_amd64.zip &&     cp bin/gosu bin/dumb-init /bin &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS &&     wget https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_SHA256SUMS.sig &&     gpg --batch --verify consul_${CONSUL_VERSION}_SHA256SUMS.sig consul_${CONSUL_VERSION}_SHA256SUMS &&     grep consul_${CONSUL_VERSION}_linux_amd64.zip consul_${CONSUL_VERSION}_SHA256SUMS | sha256sum -c &&     unzip -d /bin consul_${CONSUL_VERSION}_linux_amd64.zip &&     cd /tmp &&     rm -rf /tmp/build &&     apk del gnupg openssl &&     rm -rf /root/.gnupg
# Fri, 11 Nov 2016 20:43:42 GMT
RUN mkdir -p /consul/data &&     mkdir -p /consul/config &&     chown -R consul:consul /consul
# Fri, 11 Nov 2016 20:43:43 GMT
VOLUME [/consul/data]
# Fri, 11 Nov 2016 20:43:43 GMT
EXPOSE 8300/tcp
# Fri, 11 Nov 2016 20:43:43 GMT
EXPOSE 8301/tcp 8301/udp 8302/tcp 8302/udp
# Fri, 11 Nov 2016 20:43:44 GMT
EXPOSE 8400/tcp 8500/tcp 8600/tcp 8600/udp
# Fri, 11 Nov 2016 20:43:44 GMT
COPY file:de6c9a0e693ae46a375c565826f2071715281bba7f165975eb8537acd0d96ff4 in /usr/local/bin/docker-entrypoint.sh 
# Fri, 11 Nov 2016 20:43:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 11 Nov 2016 20:43:45 GMT
CMD ["agent" "-dev" "-client" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3690ec4760f95690944da86dc4496148a63d85c9e3100669a318110092f6862f`  
		Last Modified: Tue, 18 Oct 2016 20:32:39 GMT  
		Size: 2.3 MB (2312958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ba641cbc2e36933f14d63e3d82fd857ee6bf7e7348150bf20671a90e9f3fa563`  
		Last Modified: Fri, 11 Nov 2016 20:44:01 GMT  
		Size: 1.3 KB (1273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a0885c9cb15f564abedc944841d72bcf7f6c80d482d1bb5ea2fd698620043d9`  
		Last Modified: Fri, 11 Nov 2016 20:44:08 GMT  
		Size: 9.2 MB (9181710 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8baed0bc57fe7a7365d287d6019b0f64574dbe53044388fd7f64a03f5a4df7c4`  
		Last Modified: Fri, 11 Nov 2016 20:44:01 GMT  
		Size: 143.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:048b29acd8e7714efafe8b9c91acbf9119ff8cf5eb67143b85ec501d6cc3875d`  
		Last Modified: Fri, 11 Nov 2016 20:44:02 GMT  
		Size: 1.6 KB (1629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
