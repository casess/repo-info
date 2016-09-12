## `nginx:stable`

```console
$ docker pull nginx@sha256:4c54f4d6e452a8d4f610c13f2b7d72e7870ac9fadfab17e09e729707280f6592
```

-	Platforms:
	-	linux; amd64

### `nginx:stable` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **71.2 MB (71195391 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:70d396eb911f4740dc9deb4025bdaf48230bd3721f8ca9b7dba959417926c587`
-	Default Command: `["nginx","-g","daemon off;"]`

```dockerfile
# Thu, 28 Jul 2016 17:47:54 GMT
ADD file:0e0565652aa852f62033d99f84892216020d30f64521ded5e72d4940bc4c9697 in /
# Thu, 28 Jul 2016 17:47:55 GMT
CMD ["/bin/bash"]
# Tue, 23 Aug 2016 18:49:31 GMT
MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"
# Tue, 23 Aug 2016 18:53:05 GMT
ENV NGINX_VERSION=1.10.1-1~jessie
# Tue, 23 Aug 2016 18:54:42 GMT
RUN apt-key adv --keyserver hkp://pgp.mit.edu:80 --recv-keys 573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62 	&& echo "deb http://nginx.org/packages/debian/ jessie nginx" >> /etc/apt/sources.list 	&& apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y 						ca-certificates 						nginx=${NGINX_VERSION} 						nginx-module-xslt 						nginx-module-geoip 						nginx-module-image-filter 						nginx-module-perl 						nginx-module-njs 						gettext-base 	&& rm -rf /var/lib/apt/lists/*
# Tue, 23 Aug 2016 18:54:47 GMT
RUN ln -sf /dev/stdout /var/log/nginx/access.log 	&& ln -sf /dev/stderr /var/log/nginx/error.log
# Tue, 23 Aug 2016 18:54:48 GMT
EXPOSE 443/tcp 80/tcp
# Tue, 23 Aug 2016 18:54:49 GMT
CMD ["nginx" "-g" "daemon off;"]
```

-	Layers:
	-	`sha256:357ea8c3d80bc25792e010facfc98aee5972ebc47e290eb0d5aea3671a901cab`  
		Last Modified: Thu, 28 Jul 2016 17:49:58 GMT  
		Size: 51.4 MB (51365611 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21af961bc3ea42f82ab64f411a39432937188d9ab7a210b4dfd179174790d44a`  
		Last Modified: Tue, 23 Aug 2016 18:58:59 GMT  
		Size: 19.8 MB (19829585 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0790d050b1cc391f388d36a3311b3814f3f50a6a62a6f0ea7bc2068d3950079a`  
		Last Modified: Tue, 23 Aug 2016 18:58:51 GMT  
		Size: 195.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip