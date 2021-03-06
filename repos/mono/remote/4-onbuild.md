## `mono:4-onbuild`

```console
$ docker pull mono@sha256:0e634272d039cdd2c29c595a88d574455c969a9cfe8854b12ec5d58c32f7c2d2
```

-	Platforms:
	-	linux; amd64

### `mono:4-onbuild` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **143.1 MB (143065975 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9039f0c52d7bbf8aff465726096b90106481261cf90edad5ef95082b9876f608`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 07 Nov 2016 20:33:23 GMT
ADD file:6fdd763c7bbd245e1c98a3c937b10dcc9b5383d5d0bcda22e8cbfeb6746932da in / 
# Mon, 07 Nov 2016 20:33:24 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 20:41:54 GMT
MAINTAINER Jo Shields <jo.shields@xamarin.com>
# Tue, 08 Nov 2016 20:50:44 GMT
RUN apt-get update   && apt-get install -y curl   && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 20:50:46 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Fri, 18 Nov 2016 20:47:58 GMT
RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/4.6.2.7 main" > /etc/apt/sources.list.d/mono-xamarin.list   && apt-get update   && apt-get install -y binutils mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
# Fri, 18 Nov 2016 20:47:59 GMT
MAINTAINER Jo Shields <jo.shields@xamarin.com>
# Fri, 18 Nov 2016 20:48:00 GMT
RUN mkdir -p /usr/src/app/source /usr/src/app/build
# Fri, 18 Nov 2016 20:48:00 GMT
WORKDIR /usr/src/app/source
# Fri, 18 Nov 2016 20:48:01 GMT
ONBUILD COPY . /usr/src/app/source
# Fri, 18 Nov 2016 20:48:01 GMT
ONBUILD RUN nuget restore -NonInteractive
# Fri, 18 Nov 2016 20:48:01 GMT
ONBUILD RUN xbuild /property:Configuration=Release /property:OutDir=/usr/src/app/build/
# Fri, 18 Nov 2016 20:48:02 GMT
ONBUILD WORKDIR /usr/src/app/build
```

-	Layers:
	-	`sha256:c952bb7239f0af4620e24e9dd88d56be7d4469563f840a911c7721321431d9cb`  
		Last Modified: Mon, 07 Nov 2016 20:42:41 GMT  
		Size: 37.2 MB (37208582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d541abfbbc01335a620179134d1a01d86aebbb38f2a90ae0895fa12bcbf1888e`  
		Last Modified: Tue, 08 Nov 2016 20:52:01 GMT  
		Size: 7.6 MB (7570637 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dda78b4f741477e207964122ffda987099c38940ff1532a2c5c52bee288f1d76`  
		Last Modified: Tue, 08 Nov 2016 20:52:00 GMT  
		Size: 29.3 KB (29330 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ec4849e1f2e4a678cfc8e250e7533800a7349dfbade3237971722e4612fa8cc`  
		Last Modified: Fri, 18 Nov 2016 21:04:25 GMT  
		Size: 98.3 MB (98257262 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0a4d32f27adae812d73f88159847c2e49bcb3791622ebc14fcc3ab7fecc7ee2`  
		Last Modified: Fri, 18 Nov 2016 21:05:42 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
