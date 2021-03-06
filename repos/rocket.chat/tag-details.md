<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `rocket.chat`

-	[`rocket.chat:0.47.0`](#rocketchat0470)
-	[`rocket.chat:0.47`](#rocketchat047)
-	[`rocket.chat:0`](#rocketchat0)
-	[`rocket.chat:latest`](#rocketchatlatest)

## `rocket.chat:0.47.0`

```console
$ docker pull rocket.chat@sha256:e9cfee2b72f1bf4258bb1d0911447019a662af38713a88f761709eec3dda8da8
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0.47.0` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **164.1 MB (164052243 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7235d05706d8ad04fb46b2b62b8886002f294761da84e9f222f66c76761d1feb`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 23 Nov 2016 19:19:21 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 23 Nov 2016 19:19:27 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Wed, 23 Nov 2016 19:19:27 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Wed, 07 Dec 2016 23:20:54 GMT
ENV NODE_VERSION=4.7.0
# Wed, 07 Dec 2016 23:21:04 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Wed, 07 Dec 2016 23:21:05 GMT
CMD ["node"]
# Wed, 07 Dec 2016 23:58:04 GMT
MAINTAINER buildmaster@rocket.chat
# Wed, 07 Dec 2016 23:58:05 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat
# Wed, 07 Dec 2016 23:58:06 GMT
VOLUME [/app/uploads]
# Wed, 07 Dec 2016 23:58:07 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Wed, 07 Dec 2016 23:58:08 GMT
ENV RC_VERSION=0.47.0
# Wed, 07 Dec 2016 23:58:08 GMT
WORKDIR /app
# Wed, 07 Dec 2016 23:58:39 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Wed, 07 Dec 2016 23:58:41 GMT
USER [rocketchat]
# Wed, 07 Dec 2016 23:58:42 GMT
WORKDIR /app/bundle
# Wed, 07 Dec 2016 23:58:42 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Wed, 07 Dec 2016 23:58:43 GMT
EXPOSE 3000/tcp
# Wed, 07 Dec 2016 23:58:43 GMT
CMD ["node" "main.js"]
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
	-	`sha256:cd9504bce48c013a648681c7f1255af8ee7ded2363fa98b54b6a4a495d1a6b71`  
		Last Modified: Wed, 23 Nov 2016 19:45:54 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcdc0ec954a4f4efa5ac9a642053a9821981049da792378ee5cacb854d6968fc`  
		Last Modified: Wed, 23 Nov 2016 19:45:53 GMT  
		Size: 97.2 KB (97213 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7501c61ea84b3838e9a4b3e7a5308c4bc46ece2d539dfc59e85d303b2b1fc1`  
		Last Modified: Wed, 07 Dec 2016 23:36:50 GMT  
		Size: 12.3 MB (12261548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96a5fdebe0ab10d6356d9d64ad68f858117a2a0e9540af4db088589d112c5777`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e233e5794ddb3c8cf31c0287d9c2b052c587ff17bbafd8853c8ead3e47bdd9f3`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 94.7 KB (94663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:292551a43c94514a309ce0c332c1ae6df05c7de54571d03f000e05cd4ffdc512`  
		Last Modified: Wed, 07 Dec 2016 23:59:21 GMT  
		Size: 81.7 MB (81706919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:0.47`

```console
$ docker pull rocket.chat@sha256:e9cfee2b72f1bf4258bb1d0911447019a662af38713a88f761709eec3dda8da8
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0.47` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **164.1 MB (164052243 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7235d05706d8ad04fb46b2b62b8886002f294761da84e9f222f66c76761d1feb`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 23 Nov 2016 19:19:21 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 23 Nov 2016 19:19:27 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Wed, 23 Nov 2016 19:19:27 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Wed, 07 Dec 2016 23:20:54 GMT
ENV NODE_VERSION=4.7.0
# Wed, 07 Dec 2016 23:21:04 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Wed, 07 Dec 2016 23:21:05 GMT
CMD ["node"]
# Wed, 07 Dec 2016 23:58:04 GMT
MAINTAINER buildmaster@rocket.chat
# Wed, 07 Dec 2016 23:58:05 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat
# Wed, 07 Dec 2016 23:58:06 GMT
VOLUME [/app/uploads]
# Wed, 07 Dec 2016 23:58:07 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Wed, 07 Dec 2016 23:58:08 GMT
ENV RC_VERSION=0.47.0
# Wed, 07 Dec 2016 23:58:08 GMT
WORKDIR /app
# Wed, 07 Dec 2016 23:58:39 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Wed, 07 Dec 2016 23:58:41 GMT
USER [rocketchat]
# Wed, 07 Dec 2016 23:58:42 GMT
WORKDIR /app/bundle
# Wed, 07 Dec 2016 23:58:42 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Wed, 07 Dec 2016 23:58:43 GMT
EXPOSE 3000/tcp
# Wed, 07 Dec 2016 23:58:43 GMT
CMD ["node" "main.js"]
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
	-	`sha256:cd9504bce48c013a648681c7f1255af8ee7ded2363fa98b54b6a4a495d1a6b71`  
		Last Modified: Wed, 23 Nov 2016 19:45:54 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcdc0ec954a4f4efa5ac9a642053a9821981049da792378ee5cacb854d6968fc`  
		Last Modified: Wed, 23 Nov 2016 19:45:53 GMT  
		Size: 97.2 KB (97213 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7501c61ea84b3838e9a4b3e7a5308c4bc46ece2d539dfc59e85d303b2b1fc1`  
		Last Modified: Wed, 07 Dec 2016 23:36:50 GMT  
		Size: 12.3 MB (12261548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96a5fdebe0ab10d6356d9d64ad68f858117a2a0e9540af4db088589d112c5777`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e233e5794ddb3c8cf31c0287d9c2b052c587ff17bbafd8853c8ead3e47bdd9f3`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 94.7 KB (94663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:292551a43c94514a309ce0c332c1ae6df05c7de54571d03f000e05cd4ffdc512`  
		Last Modified: Wed, 07 Dec 2016 23:59:21 GMT  
		Size: 81.7 MB (81706919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:0`

```console
$ docker pull rocket.chat@sha256:e9cfee2b72f1bf4258bb1d0911447019a662af38713a88f761709eec3dda8da8
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:0` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **164.1 MB (164052243 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7235d05706d8ad04fb46b2b62b8886002f294761da84e9f222f66c76761d1feb`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 23 Nov 2016 19:19:21 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 23 Nov 2016 19:19:27 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Wed, 23 Nov 2016 19:19:27 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Wed, 07 Dec 2016 23:20:54 GMT
ENV NODE_VERSION=4.7.0
# Wed, 07 Dec 2016 23:21:04 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Wed, 07 Dec 2016 23:21:05 GMT
CMD ["node"]
# Wed, 07 Dec 2016 23:58:04 GMT
MAINTAINER buildmaster@rocket.chat
# Wed, 07 Dec 2016 23:58:05 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat
# Wed, 07 Dec 2016 23:58:06 GMT
VOLUME [/app/uploads]
# Wed, 07 Dec 2016 23:58:07 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Wed, 07 Dec 2016 23:58:08 GMT
ENV RC_VERSION=0.47.0
# Wed, 07 Dec 2016 23:58:08 GMT
WORKDIR /app
# Wed, 07 Dec 2016 23:58:39 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Wed, 07 Dec 2016 23:58:41 GMT
USER [rocketchat]
# Wed, 07 Dec 2016 23:58:42 GMT
WORKDIR /app/bundle
# Wed, 07 Dec 2016 23:58:42 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Wed, 07 Dec 2016 23:58:43 GMT
EXPOSE 3000/tcp
# Wed, 07 Dec 2016 23:58:43 GMT
CMD ["node" "main.js"]
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
	-	`sha256:cd9504bce48c013a648681c7f1255af8ee7ded2363fa98b54b6a4a495d1a6b71`  
		Last Modified: Wed, 23 Nov 2016 19:45:54 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcdc0ec954a4f4efa5ac9a642053a9821981049da792378ee5cacb854d6968fc`  
		Last Modified: Wed, 23 Nov 2016 19:45:53 GMT  
		Size: 97.2 KB (97213 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7501c61ea84b3838e9a4b3e7a5308c4bc46ece2d539dfc59e85d303b2b1fc1`  
		Last Modified: Wed, 07 Dec 2016 23:36:50 GMT  
		Size: 12.3 MB (12261548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96a5fdebe0ab10d6356d9d64ad68f858117a2a0e9540af4db088589d112c5777`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e233e5794ddb3c8cf31c0287d9c2b052c587ff17bbafd8853c8ead3e47bdd9f3`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 94.7 KB (94663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:292551a43c94514a309ce0c332c1ae6df05c7de54571d03f000e05cd4ffdc512`  
		Last Modified: Wed, 07 Dec 2016 23:59:21 GMT  
		Size: 81.7 MB (81706919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `rocket.chat:latest`

```console
$ docker pull rocket.chat@sha256:e9cfee2b72f1bf4258bb1d0911447019a662af38713a88f761709eec3dda8da8
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **164.1 MB (164052243 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7235d05706d8ad04fb46b2b62b8886002f294761da84e9f222f66c76761d1feb`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Mon, 07 Nov 2016 22:27:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 23 Nov 2016 19:19:21 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 23 Nov 2016 19:19:27 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Wed, 23 Nov 2016 19:19:27 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Wed, 07 Dec 2016 23:20:54 GMT
ENV NODE_VERSION=4.7.0
# Wed, 07 Dec 2016 23:21:04 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Wed, 07 Dec 2016 23:21:05 GMT
CMD ["node"]
# Wed, 07 Dec 2016 23:58:04 GMT
MAINTAINER buildmaster@rocket.chat
# Wed, 07 Dec 2016 23:58:05 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat
# Wed, 07 Dec 2016 23:58:06 GMT
VOLUME [/app/uploads]
# Wed, 07 Dec 2016 23:58:07 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Wed, 07 Dec 2016 23:58:08 GMT
ENV RC_VERSION=0.47.0
# Wed, 07 Dec 2016 23:58:08 GMT
WORKDIR /app
# Wed, 07 Dec 2016 23:58:39 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Wed, 07 Dec 2016 23:58:41 GMT
USER [rocketchat]
# Wed, 07 Dec 2016 23:58:42 GMT
WORKDIR /app/bundle
# Wed, 07 Dec 2016 23:58:42 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Wed, 07 Dec 2016 23:58:43 GMT
EXPOSE 3000/tcp
# Wed, 07 Dec 2016 23:58:43 GMT
CMD ["node" "main.js"]
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
	-	`sha256:cd9504bce48c013a648681c7f1255af8ee7ded2363fa98b54b6a4a495d1a6b71`  
		Last Modified: Wed, 23 Nov 2016 19:45:54 GMT  
		Size: 4.3 KB (4345 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcdc0ec954a4f4efa5ac9a642053a9821981049da792378ee5cacb854d6968fc`  
		Last Modified: Wed, 23 Nov 2016 19:45:53 GMT  
		Size: 97.2 KB (97213 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7501c61ea84b3838e9a4b3e7a5308c4bc46ece2d539dfc59e85d303b2b1fc1`  
		Last Modified: Wed, 07 Dec 2016 23:36:50 GMT  
		Size: 12.3 MB (12261548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96a5fdebe0ab10d6356d9d64ad68f858117a2a0e9540af4db088589d112c5777`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e233e5794ddb3c8cf31c0287d9c2b052c587ff17bbafd8853c8ead3e47bdd9f3`  
		Last Modified: Wed, 07 Dec 2016 23:58:57 GMT  
		Size: 94.7 KB (94663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:292551a43c94514a309ce0c332c1ae6df05c7de54571d03f000e05cd4ffdc512`  
		Last Modified: Wed, 07 Dec 2016 23:59:21 GMT  
		Size: 81.7 MB (81706919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
