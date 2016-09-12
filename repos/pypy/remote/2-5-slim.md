## `pypy:2-5-slim`

```console
$ docker pull pypy@sha256:ba9576262f52186c872622a9119b7c08b28e6c2adb04cf5dfe97734999f2498d
```

-	Platforms:
	-	linux; amd64

### `pypy:2-5-slim` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **82.7 MB (82663067 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cd6c164a8c1f14facc57cb270a5ee328551b28ded7d3df7227e8f413a0b1a291`
-	Default Command: `["pypy"]`

```dockerfile
# Tue, 30 Aug 2016 21:00:51 GMT
ADD file:f2453b914e7e026efd39c6321c7b14509b6d09dd3cf5567a8f6bd38466e06954 in / 
# Tue, 30 Aug 2016 21:00:52 GMT
CMD ["/bin/bash"]
# Wed, 31 Aug 2016 02:39:27 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 31 Aug 2016 02:39:27 GMT
ENV LANG=C.UTF-8
# Thu, 08 Sep 2016 20:53:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Thu, 08 Sep 2016 20:53:34 GMT
ENV PYPY_VERSION=5.4.1
# Thu, 08 Sep 2016 20:53:34 GMT
ENV PYPY_SHA256SUM=9c85319778224d7fb0c348f55fe3fada15bb579c5f3870a13ad63b42a737dd72
# Thu, 08 Sep 2016 20:53:35 GMT
ENV PYTHON_PIP_VERSION=8.1.2
# Thu, 08 Sep 2016 20:53:59 GMT
RUN set -ex 	&& fetchDeps=' 		bzip2 		wget 	' 	&& apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy2-v${PYPY_VERSION}-linux64.tar.bz2" 	&& echo "$PYPY_SHA256SUM  pypy.tar.bz2" | sha256sum -c 	&& tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2 	&& rm pypy.tar.bz2 			&& wget -O /tmp/get-pip.py 'https://bootstrap.pypa.io/get-pip.py' 		&& pypy /tmp/get-pip.py "pip==$PYTHON_PIP_VERSION" 		&& rm /tmp/get-pip.py 	&& pip install --no-cache-dir --upgrade --force-reinstall "pip==$PYTHON_PIP_VERSION" 	&& [ "$(pip list |tac|tac| awk -F '[ ()]+' '$1 == "pip" { print $2; exit }')" = "$PYTHON_PIP_VERSION" ] 		&& apt-get purge -y --auto-remove $fetchDeps 	&& rm -rf ~/.cache
# Thu, 08 Sep 2016 20:54:00 GMT
CMD ["pypy"]
```

-	Layers:
	-	`sha256:8ad8b3f87b378cfae583fef34e47a3c9203847d779961b7351cbf786af0bc09f`  
		Last Modified: Tue, 30 Aug 2016 21:02:02 GMT  
		Size: 51.4 MB (51367268 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3201fa3d047251e1cd4d144a7c8182853606fd2d2cd67e45c29632c208c16e7b`  
		Last Modified: Thu, 08 Sep 2016 20:55:48 GMT  
		Size: 3.5 MB (3464735 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7bc72e615503c96103b8c6e885e536d3947764eb5e2b4a4f0e839bceaf8f3c5`  
		Last Modified: Thu, 08 Sep 2016 20:56:00 GMT  
		Size: 27.8 MB (27831064 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip