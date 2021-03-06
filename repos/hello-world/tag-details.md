<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `hello-world`

-	[`hello-world:latest`](#hello-worldlatest)
-	[`hello-world:nanoserver`](#hello-worldnanoserver)

## `hello-world:latest`

```console
$ docker pull hello-world@sha256:0256e8a36e2070f7bf2d0b0763dbabdd67798512411de4cdcf9431a1feb60fd9
```

-	Platforms:
	-	linux; amd64

### `hello-world:latest` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **974.0 B**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c54a2cc56cbb2f04003c1cd4507e118af7c0d340fe7e2720f70976c4b75237dc`
-	Default Command: `["\/hello"]`

```dockerfile
# Fri, 01 Jul 2016 19:39:26 GMT
COPY file:21fb0ede514e588c72071bfbd3c577e2f6a669db9351d1a435e21baf895efcd6 in /
# Fri, 01 Jul 2016 19:39:27 GMT
CMD ["/hello"]
```

-	Layers:
	-	`sha256:c04b14da8d1441880ed3fe6106fb2cc6fa1c9661846ac0266b8a5ec8edf37b7c`  
		Last Modified: Fri, 01 Jul 2016 19:39:34 GMT  
		Size: 974.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `hello-world:nanoserver`

```console
$ docker pull hello-world@sha256:3f5a4d0983b0cf36db8b767a25b0db6e4ae3e5abec8831dc03fe773c58ee404a
```

-	Platforms:
	-	windows; amd64

### `hello-world:nanoserver` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **343.2 MB (343178826 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:64385142d4dc5ad057d07fdc20859cbeabce75d2a9df8b03c11679cce43b6ab2`
-	Default Command: `["cmd","\/C","type C:\\hello.txt"]`

```dockerfile
# Mon, 21 Nov 2016 20:24:22 GMT
RUN cmd /S /C #(nop) COPY file:9341009dbfcf24e5ece855cc7a1f9ae5c60019d9d57ac3254d48defda0555271 in C: 
# Mon, 21 Nov 2016 20:24:24 GMT
RUN cmd /S /C #(nop)  CMD ["cmd" "/C" "type C:\\hello.txt"]
```

-	Layers:
	-	`sha256:5496abde368a3dd39999745bf998c877ddc6a390a943bc3fd99ffaabf728ed88`  
		Size: 242.6 MB (242646586 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:482ab31872a23b32cbdeca13edb7a0b97290714c0b5edcce96fbb3e34221ea91`  
		Size: 100.5 MB (100529622 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:4256836bcaf82f57c8f86ff5544a2561e2a2a6801dd11685ed07bcce5e28bd0d`  
		Last Modified: Mon, 21 Nov 2016 20:24:28 GMT  
		Size: 1.7 KB (1663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5bc5abeff4046896b79b05966f62694bcd8393cbe34a59752da498814e3b2299`  
		Last Modified: Mon, 21 Nov 2016 20:24:29 GMT  
		Size: 955.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
