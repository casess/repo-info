## `arangodb:latest`

```console
$ docker pull arangodb@sha256:791be361b10c2f73125f524ddeaca99d4fd5986e63ac153cad06546d3a5ff5ff
```

-	Platforms:
	-	linux; amd64

### `arangodb:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **126.6 MB (126607866 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6ddd29e756c2df5696043fd2f04f75e0c03ac4fc34072b3e5f8207cc462ffc5c`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["arangod"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 18:42:33 GMT
MAINTAINER Frank Celler <info@arangodb.com>
# Tue, 08 Nov 2016 18:49:29 GMT
ENV ARCHITECTURE=amd64
# Mon, 14 Nov 2016 18:41:59 GMT
ENV DEB_PACKAGE_VERSION=1
# Fri, 09 Dec 2016 17:52:53 GMT
ENV ARANGO_VERSION=3.1.4
# Fri, 09 Dec 2016 17:52:53 GMT
ENV ARANGO_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0
# Fri, 09 Dec 2016 17:52:53 GMT
ENV ARANGO_PACKAGE=arangodb3-3.1.4-1_amd64.deb
# Fri, 09 Dec 2016 17:52:54 GMT
ENV ARANGO_PACKAGE_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0/amd64/arangodb3-3.1.4-1_amd64.deb
# Fri, 09 Dec 2016 17:52:54 GMT
ENV ARANGO_SIGNATURE_URL=https://www.arangodb.com/repositories/arangodb31/Debian_8.0/amd64/arangodb3-3.1.4-1_amd64.deb.asc
# Fri, 09 Dec 2016 17:52:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys CD8CB0F1E0AD5B52E93F41E7EA93F5E56E751E9B
# Fri, 09 Dec 2016 17:53:11 GMT
RUN apt-get update &&     apt-get install -y --no-install-recommends         libjemalloc1 	libsnappy1         ca-certificates         pwgen         curl     &&     rm -rf /var/lib/apt/lists/*
# Fri, 09 Dec 2016 17:53:12 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Fri, 09 Dec 2016 17:53:40 GMT
RUN curl -O ${ARANGO_SIGNATURE_URL} &&           curl -O ${ARANGO_PACKAGE_URL} &&             gpg --verify ${ARANGO_PACKAGE}.asc &&     (echo arangodb3 arangodb3/password password test | debconf-set-selections) &&     (echo arangodb3 arangodb3/password_again password test | debconf-set-selections) &&     DEBIAN_FRONTEND="noninteractive" dpkg -i ${ARANGO_PACKAGE} &&     rm -rf /var/lib/arangodb3/* &&     sed -ri         -e 's!127\.0\.0\.1!0.0.0.0!g'         -e 's!^(file\s*=).*!\1 -!'         -e 's!^#\s*uid\s*=.*!uid = arangodb!'         -e 's!^#\s*gid\s*=.*!gid = arangodb!'         /etc/arangodb3/arangod.conf     &&     DEBIAN_FRONTEND="noninteractive" apt-get purge -y --auto-remove ca-certificates &&     rm -f ${ARANGO_PACKAGE}*
# Fri, 09 Dec 2016 17:53:41 GMT
VOLUME [/var/lib/arangodb3 /var/lib/arangodb3-apps]
# Fri, 09 Dec 2016 17:53:42 GMT
COPY file:9f20ed9a2181af8ddc12371a0082e7645aa20b1008b5f484851bcc399e64801e in /entrypoint.sh 
# Fri, 09 Dec 2016 17:53:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 09 Dec 2016 17:53:43 GMT
EXPOSE 8529/tcp
# Fri, 09 Dec 2016 17:53:43 GMT
CMD ["arangod"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02282760997377c35441a21f13173c65450520534878f683d16811a51193df8f`  
		Last Modified: Fri, 09 Dec 2016 17:55:48 GMT  
		Size: 7.4 KB (7366 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6805b86b3ebc3d4b78f2b762c56ebc10f62ea9a0d0b1b96342df80f8c93495f3`  
		Last Modified: Fri, 09 Dec 2016 17:55:47 GMT  
		Size: 6.7 MB (6683797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dab0ee0455854da11b47097c42a0e92b59153551a483b3848f09e212d0fbec92`  
		Last Modified: Fri, 09 Dec 2016 17:55:45 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbffef8d189a8f12c730c37ecc7dfb99a4cdfb7499d4958e3f1056b4272a0357`  
		Last Modified: Fri, 09 Dec 2016 17:56:05 GMT  
		Size: 68.6 MB (68558164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19af744236534f648cfddae22014bebbbe8ad5d67d08cf80c9a3d26abfba142d`  
		Last Modified: Fri, 09 Dec 2016 17:55:45 GMT  
		Size: 1.4 KB (1436 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
