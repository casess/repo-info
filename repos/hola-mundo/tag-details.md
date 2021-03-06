<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `hola-mundo`

-	[`hola-mundo:latest`](#hola-mundolatest)
-	[`hola-mundo:nanoserver`](#hola-mundonanoserver)

## `hola-mundo:latest`

```console
$ docker pull hola-mundo@sha256:5e796e7d978ea682dca1d3a3e817fef58df1a9e2830157c7c49d465dd014bc71
```

-	Platforms:
	-	linux; amd64

### `hola-mundo:latest` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **995.0 B**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f8d7b5c20e9a0bf389bc42ebd4f12bc510fde8f00e8e06abbfdbba5ddbb14b00`
-	Default Command: `["\/hello"]`

```dockerfile
# Fri, 01 Jul 2016 19:39:44 GMT
COPY file:a5683840ef8d031155d28627397288d42671eab91b639b960af545b1360af727 in /
# Fri, 01 Jul 2016 19:39:44 GMT
CMD ["/hello"]
```

-	Layers:
	-	`sha256:d8fd245f4d9eb7b64f9c962a61072d8cf7f1a2cc61c234989a9a66302326583c`  
		Last Modified: Fri, 01 Jul 2016 19:39:52 GMT  
		Size: 995.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `hola-mundo:nanoserver`

```console
$ docker pull hola-mundo@sha256:42d2fa51897e2779a14ea3ffc69c55bc5b406157b544d1ac8b932b9ccb7eac84
```

-	Platforms:
	-	windows; amd64

### `hola-mundo:nanoserver` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **343.2 MB (343178841 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c836e8281a89fdc2d1b9bb088c3ec945f54f97c8a78eb3cc23ca1690a0947da`
-	Default Command: `["cmd","\/C","type C:\\hello.txt"]`

```dockerfile
# Mon, 21 Nov 2016 20:24:34 GMT
RUN cmd /S /C #(nop) COPY file:8782f5dbf383aa126556f4d5860e14f79fbb620fadebd9f62a6146a178c74d6d in C: 
# Mon, 21 Nov 2016 20:24:36 GMT
RUN cmd /S /C #(nop)  CMD ["cmd" "/C" "type C:\\hello.txt"]
```

-	Layers:
	-	`sha256:5496abde368a3dd39999745bf998c877ddc6a390a943bc3fd99ffaabf728ed88`  
		Size: 242.6 MB (242646586 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:482ab31872a23b32cbdeca13edb7a0b97290714c0b5edcce96fbb3e34221ea91`  
		Size: 100.5 MB (100529622 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:968dd89ec0c9f5ad63cf2741964c57129f45e5523383b802ff41b59507b5c302`  
		Last Modified: Mon, 21 Nov 2016 20:24:42 GMT  
		Size: 1.7 KB (1680 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b9330a2d4919e5c8371b28d52fbad9e4c063c8cdb81e564b24927d8ddf1e68e`  
		Last Modified: Mon, 21 Nov 2016 20:24:40 GMT  
		Size: 953.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
