## `ghost:latest`

```console
$ docker pull ghost@sha256:2258f67d3cc513dbf205d5e793e6a9d7359ba28cf16fc5dce08b4e5d2b982245
```

-	Platforms:
	-	linux; amd64

### `ghost:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.3 MB (114337111 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b73bd21ec0477e02c853b6b086a67d96af56fd62e0fa3d81b17893fa923d9873`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 30 Aug 2016 21:00:51 GMT
ADD file:f2453b914e7e026efd39c6321c7b14509b6d09dd3cf5567a8f6bd38466e06954 in / 
# Tue, 30 Aug 2016 21:00:52 GMT
CMD ["/bin/bash"]
# Tue, 30 Aug 2016 21:52:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 30 Aug 2016 22:01:06 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     0034A06D9D9B0064CE8ADF6BF1747F4AD2306D93     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 30 Aug 2016 22:02:00 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 30 Aug 2016 22:02:00 GMT
ENV NODE_VERSION=4.5.0
# Tue, 30 Aug 2016 22:02:09 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Tue, 30 Aug 2016 22:02:10 GMT
CMD ["node"]
# Tue, 30 Aug 2016 23:19:36 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Wed, 07 Sep 2016 18:05:43 GMT
ENV GOSU_VERSION=1.7
# Wed, 07 Sep 2016 18:05:49 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Wed, 07 Sep 2016 18:05:50 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Wed, 07 Sep 2016 18:05:50 GMT
WORKDIR /usr/src/ghost
# Thu, 08 Sep 2016 17:57:40 GMT
ENV GHOST_VERSION=0.10.1
# Thu, 08 Sep 2016 17:58:39 GMT
RUN buildDeps=' 		gcc 		make 		python 		unzip 	' 	&& set -x 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 	&& wget -O ghost.zip "https://ghost.org/archives/ghost-${GHOST_VERSION}.zip" 	&& unzip ghost.zip 	&& npm install --production 	&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false $buildDeps 	&& rm ghost.zip 	&& npm cache clean 	&& rm -rf /tmp/npm*
# Thu, 08 Sep 2016 17:58:39 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Thu, 08 Sep 2016 17:58:40 GMT
RUN mkdir -p "$GHOST_CONTENT" && chown -R user:user "$GHOST_CONTENT"
# Thu, 08 Sep 2016 17:58:40 GMT
VOLUME [/var/lib/ghost]
# Thu, 08 Sep 2016 17:58:41 GMT
COPY file:c0bc882b990efd55f75953224ed07d533c09aeac8158a4698a92e623b1c79ce9 in /entrypoint.sh 
# Thu, 08 Sep 2016 17:58:41 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 08 Sep 2016 17:58:41 GMT
EXPOSE 2368/tcp
# Thu, 08 Sep 2016 17:58:42 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:8ad8b3f87b378cfae583fef34e47a3c9203847d779961b7351cbf786af0bc09f`  
		Last Modified: Tue, 30 Aug 2016 21:02:02 GMT  
		Size: 51.4 MB (51367268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:751fe39c4d348c7fc411d46929c1dac390e3d7107efc9f8f69641b50e14459f7`  
		Last Modified: Tue, 30 Aug 2016 21:59:08 GMT  
		Size: 18.5 MB (18527264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c8031bea3fa7a9ab51e491ccfebaa75d172cda490602b2101b5cb2c0c8cdea5`  
		Last Modified: Tue, 30 Aug 2016 23:09:38 GMT  
		Size: 71.8 KB (71848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:854b52827bb4e83d9198f145e14c5ba239aaa6e75987ec0a019332e0e2b7fae1`  
		Last Modified: Tue, 30 Aug 2016 23:13:28 GMT  
		Size: 12.3 MB (12273177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2c2db6ff75a3db50798375c44d712855cbb89b9cf0b82ecd7e23e30c92b9e7c`  
		Last Modified: Tue, 30 Aug 2016 23:21:07 GMT  
		Size: 4.3 KB (4335 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e874614dce5742d9998b2ba5aa03f3111d92266dddcc9bc66fcaf28c9eaa465`  
		Last Modified: Wed, 07 Sep 2016 18:07:14 GMT  
		Size: 807.9 KB (807934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3aa1c5caad5511eec529ce57728e818b09f845443b4809ad84a923b1132ed03c`  
		Last Modified: Wed, 07 Sep 2016 18:07:12 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0cb1edc0454a245349d6dd1659e1eca20de1a080744abfb5cacc18e3fa225495`  
		Last Modified: Thu, 08 Sep 2016 17:58:59 GMT  
		Size: 31.3 MB (31284547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d8ba59589a6a56e3a03daeaed68e9372f611f3c5b82e0e648f4d7c07c37d58f`  
		Last Modified: Thu, 08 Sep 2016 17:58:47 GMT  
		Size: 137.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bff20c59045801215fb4593a5bec2b61532545c3b9846a1ad6d3bf4900f5c194`  
		Last Modified: Thu, 08 Sep 2016 17:58:47 GMT  
		Size: 471.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip