<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `backdrop`

-	[`backdrop:1.5.2`](#backdrop152)
-	[`backdrop:1.5`](#backdrop15)
-	[`backdrop:1`](#backdrop1)
-	[`backdrop:1.5.0-apache`](#backdrop150-apache)
-	[`backdrop:1.5-apache`](#backdrop15-apache)
-	[`backdrop:1-apache`](#backdrop1-apache)
-	[`backdrop:apache`](#backdropapache)
-	[`backdrop:latest`](#backdroplatest)
-	[`backdrop:1.5.2-fpm`](#backdrop152-fpm)
-	[`backdrop:1.5-fpm`](#backdrop15-fpm)
-	[`backdrop:1-fpm`](#backdrop1-fpm)
-	[`backdrop:fpm`](#backdropfpm)

## `backdrop:1.5.2`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5.2` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1.5`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1.5.0-apache`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5.0-apache` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1.5-apache`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5-apache` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1-apache`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:1-apache` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:apache`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:apache` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:latest`

```console
$ docker pull backdrop@sha256:c7467d27fa9b6b93f1d2483c6b1ece2b63e84812f3ae4d94a50b1f559c0639af
```

-	Platforms:
	-	linux; amd64

### `backdrop:latest` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.5 MB (168456508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7bf1bc9740300acd400121a73354614432a3d70594a96d6a6d2e888f8fc5014b`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:22:45 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 08 Nov 2016 23:22:45 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 08 Nov 2016 23:22:46 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 08 Nov 2016 23:22:47 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 08 Nov 2016 23:22:48 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 08 Nov 2016 23:22:49 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 08 Nov 2016 23:22:50 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:49 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:26:50 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:16:28 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:16:29 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:16:38 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:16:39 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:18:46 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:21 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:22 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:23 GMT
EXPOSE 80/tcp
# Wed, 07 Dec 2016 19:12:23 GMT
CMD ["apache2-foreground"]
# Wed, 07 Dec 2016 21:08:31 GMT
RUN a2enmod rewrite
# Wed, 07 Dec 2016 21:09:54 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:10:01 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:10:01 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:10:07 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz   && echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c -   && tar -xz --strip-components=1 -f backdrop.tar.gz   && rm backdrop.tar.gz   && chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:10:16 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:10:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:10:17 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:872f6d38a33bac61f5c37fce97cc80fc61ee6ffe8d8a7da5d30cc2733aaebb7e`  
		Last Modified: Tue, 08 Nov 2016 23:25:38 GMT  
		Size: 2.8 MB (2849357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5ea5361568cb6486c878f80ba5844797b34da7b824fdb4eb5ecbaa05416e503`  
		Last Modified: Tue, 08 Nov 2016 23:25:37 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81f18e7771919bad862147cb2c038a59fab10d523862f0ae5ff9417137dfd58`  
		Last Modified: Tue, 08 Nov 2016 23:25:36 GMT  
		Size: 425.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dbc878ca0c93ba275fdb0cbc79169d4b1b86735d24b8577ea529daa953b333`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 222.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:195935e4100b1050f83184b119a90f6ca23b3b03954773ea7de354a629652673`  
		Last Modified: Tue, 08 Nov 2016 23:25:35 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0191f86c93d0537f4f1141651d5e4ebb4f6fe87820121e1abdf7a5a696451ba9`  
		Last Modified: Tue, 06 Dec 2016 22:49:35 GMT  
		Size: 12.6 MB (12571206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2668a15f7db3ce6c9238cdef988c4fcea831cfa684729f7c61835bed41277caf`  
		Last Modified: Tue, 06 Dec 2016 22:49:32 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cec47ea54d8e25d808aa15b3cf81508f6202c8942a296cb706532881680a58b3`  
		Last Modified: Tue, 06 Dec 2016 22:49:36 GMT  
		Size: 9.1 MB (9102934 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e5d932ca96d093228d1ba050bff9b215e2a2185e3fec547d220f3dd705accbf`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 1.8 KB (1831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d29c2876dc397682827a22222ed4a6ffcde9dc974eee03c57ef21381892b41aa`  
		Last Modified: Wed, 07 Dec 2016 19:28:26 GMT  
		Size: 580.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bcc4e105f6df9eaff49feb7e0b780b7723f489c30b6bbcef1a47e9b02a200ca`  
		Last Modified: Wed, 07 Dec 2016 21:12:06 GMT  
		Size: 293.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0ccafc9de93dc9407baefee16effd83733ac91115559bd4c2fa48f19d2e3477`  
		Last Modified: Wed, 07 Dec 2016 21:12:10 GMT  
		Size: 6.9 MB (6905370 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49b6652aefc6afc5c78105b181989e7144f931326bc8cac809f2147ad069e9bd`  
		Last Modified: Wed, 07 Dec 2016 21:12:08 GMT  
		Size: 8.1 MB (8072679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22be59d032b63024dc8e9cd51f987b58eeff94aeeb8875ae3c1c626d37211390`  
		Last Modified: Wed, 07 Dec 2016 21:12:05 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1.5.2-fpm`

```console
$ docker pull backdrop@sha256:4a86bccc5222e896df6861ece692495ed3e5e48ba08bf67da41507ef3df91011
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5.2-fpm` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.0 MB (164956074 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:54b3a651a1691f7014e7bd4e3cf1f71f9b06543e1696eea8e7ac761748dfe258`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 06 Dec 2016 21:29:28 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:18:49 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:18:49 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:19:01 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:19:02 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:22:13 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:24 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:25 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:26 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Wed, 07 Dec 2016 19:12:26 GMT
EXPOSE 9000/tcp
# Wed, 07 Dec 2016 19:12:26 GMT
CMD ["php-fpm"]
# Wed, 07 Dec 2016 21:11:35 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:11:37 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:11:41 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz 	&& echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f backdrop.tar.gz 	&& rm backdrop.tar.gz 	&& chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:11:42 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:11:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:11:42 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e33b402f8dab84d89e0cbc7312bfea5f9a57c1fca4b90823205f1082f657a023`  
		Last Modified: Tue, 06 Dec 2016 22:50:31 GMT  
		Size: 12.6 MB (12552031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbb919650a069b03abe443d1a0f4e54c854d7f31488888b11d2f2a074ba858d0`  
		Last Modified: Tue, 06 Dec 2016 22:50:26 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3baf42de3541778d607ce56954f095300c2285aacdea139e1a43e51fd9db682`  
		Last Modified: Tue, 06 Dec 2016 22:50:28 GMT  
		Size: 8.5 MB (8488797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d332211c7a61227c4955de19b4e1df753fdacf37afc1a3e9a809201801879661`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 1.8 KB (1828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:530065f3a72215af50a85cdbfc251f7864466f2a8ae839497838fba70ca85816`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c42311d28c692c0aa11cf04b1910f39c2156244441af5c663e403842c370dabb`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 7.6 KB (7630 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19ea7ab39d82e7669c27d2c3303ba57bdd2b980a88003b9af93e5bd5a69820e6`  
		Last Modified: Wed, 07 Dec 2016 21:14:40 GMT  
		Size: 6.9 MB (6883100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21d81b45a7e9fbad8e270f27e5f7124747224e286dcd093b21b2561548a14cd6`  
		Last Modified: Wed, 07 Dec 2016 21:14:42 GMT  
		Size: 8.1 MB (8072675 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b04a222216ba41c43d3251abd1bf1b0f9cfda6004afd4c36e199e9214d3b8bf9`  
		Last Modified: Wed, 07 Dec 2016 21:14:37 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1.5-fpm`

```console
$ docker pull backdrop@sha256:4a86bccc5222e896df6861ece692495ed3e5e48ba08bf67da41507ef3df91011
```

-	Platforms:
	-	linux; amd64

### `backdrop:1.5-fpm` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.0 MB (164956074 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:54b3a651a1691f7014e7bd4e3cf1f71f9b06543e1696eea8e7ac761748dfe258`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 06 Dec 2016 21:29:28 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:18:49 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:18:49 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:19:01 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:19:02 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:22:13 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:24 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:25 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:26 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Wed, 07 Dec 2016 19:12:26 GMT
EXPOSE 9000/tcp
# Wed, 07 Dec 2016 19:12:26 GMT
CMD ["php-fpm"]
# Wed, 07 Dec 2016 21:11:35 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:11:37 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:11:41 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz 	&& echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f backdrop.tar.gz 	&& rm backdrop.tar.gz 	&& chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:11:42 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:11:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:11:42 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e33b402f8dab84d89e0cbc7312bfea5f9a57c1fca4b90823205f1082f657a023`  
		Last Modified: Tue, 06 Dec 2016 22:50:31 GMT  
		Size: 12.6 MB (12552031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbb919650a069b03abe443d1a0f4e54c854d7f31488888b11d2f2a074ba858d0`  
		Last Modified: Tue, 06 Dec 2016 22:50:26 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3baf42de3541778d607ce56954f095300c2285aacdea139e1a43e51fd9db682`  
		Last Modified: Tue, 06 Dec 2016 22:50:28 GMT  
		Size: 8.5 MB (8488797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d332211c7a61227c4955de19b4e1df753fdacf37afc1a3e9a809201801879661`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 1.8 KB (1828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:530065f3a72215af50a85cdbfc251f7864466f2a8ae839497838fba70ca85816`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c42311d28c692c0aa11cf04b1910f39c2156244441af5c663e403842c370dabb`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 7.6 KB (7630 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19ea7ab39d82e7669c27d2c3303ba57bdd2b980a88003b9af93e5bd5a69820e6`  
		Last Modified: Wed, 07 Dec 2016 21:14:40 GMT  
		Size: 6.9 MB (6883100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21d81b45a7e9fbad8e270f27e5f7124747224e286dcd093b21b2561548a14cd6`  
		Last Modified: Wed, 07 Dec 2016 21:14:42 GMT  
		Size: 8.1 MB (8072675 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b04a222216ba41c43d3251abd1bf1b0f9cfda6004afd4c36e199e9214d3b8bf9`  
		Last Modified: Wed, 07 Dec 2016 21:14:37 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:1-fpm`

```console
$ docker pull backdrop@sha256:4a86bccc5222e896df6861ece692495ed3e5e48ba08bf67da41507ef3df91011
```

-	Platforms:
	-	linux; amd64

### `backdrop:1-fpm` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.0 MB (164956074 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:54b3a651a1691f7014e7bd4e3cf1f71f9b06543e1696eea8e7ac761748dfe258`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 06 Dec 2016 21:29:28 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:18:49 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:18:49 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:19:01 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:19:02 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:22:13 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:24 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:25 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:26 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Wed, 07 Dec 2016 19:12:26 GMT
EXPOSE 9000/tcp
# Wed, 07 Dec 2016 19:12:26 GMT
CMD ["php-fpm"]
# Wed, 07 Dec 2016 21:11:35 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:11:37 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:11:41 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz 	&& echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f backdrop.tar.gz 	&& rm backdrop.tar.gz 	&& chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:11:42 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:11:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:11:42 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e33b402f8dab84d89e0cbc7312bfea5f9a57c1fca4b90823205f1082f657a023`  
		Last Modified: Tue, 06 Dec 2016 22:50:31 GMT  
		Size: 12.6 MB (12552031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbb919650a069b03abe443d1a0f4e54c854d7f31488888b11d2f2a074ba858d0`  
		Last Modified: Tue, 06 Dec 2016 22:50:26 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3baf42de3541778d607ce56954f095300c2285aacdea139e1a43e51fd9db682`  
		Last Modified: Tue, 06 Dec 2016 22:50:28 GMT  
		Size: 8.5 MB (8488797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d332211c7a61227c4955de19b4e1df753fdacf37afc1a3e9a809201801879661`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 1.8 KB (1828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:530065f3a72215af50a85cdbfc251f7864466f2a8ae839497838fba70ca85816`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c42311d28c692c0aa11cf04b1910f39c2156244441af5c663e403842c370dabb`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 7.6 KB (7630 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19ea7ab39d82e7669c27d2c3303ba57bdd2b980a88003b9af93e5bd5a69820e6`  
		Last Modified: Wed, 07 Dec 2016 21:14:40 GMT  
		Size: 6.9 MB (6883100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21d81b45a7e9fbad8e270f27e5f7124747224e286dcd093b21b2561548a14cd6`  
		Last Modified: Wed, 07 Dec 2016 21:14:42 GMT  
		Size: 8.1 MB (8072675 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b04a222216ba41c43d3251abd1bf1b0f9cfda6004afd4c36e199e9214d3b8bf9`  
		Last Modified: Wed, 07 Dec 2016 21:14:37 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `backdrop:fpm`

```console
$ docker pull backdrop@sha256:4a86bccc5222e896df6861ece692495ed3e5e48ba08bf67da41507ef3df91011
```

-	Platforms:
	-	linux; amd64

### `backdrop:fpm` - linux; amd64

-	Docker Version: 1.12.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.0 MB (164956074 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:54b3a651a1691f7014e7bd4e3cf1f71f9b06543e1696eea8e7ac761748dfe258`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 07 Nov 2016 20:30:25 GMT
ADD file:41ea5187c50116884c38d9ec51d920d79cfaeb2a61c52e07a97f457419a10a4f in / 
# Mon, 07 Nov 2016 20:30:26 GMT
CMD ["/bin/bash"]
# Tue, 08 Nov 2016 23:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 08 Nov 2016 23:16:53 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 08 Nov 2016 23:16:54 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 08 Nov 2016 23:16:55 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 08 Nov 2016 23:26:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 06 Dec 2016 21:29:28 GMT
ENV CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 06 Dec 2016 21:29:29 GMT
ENV LDFLAGS=-Wl,-O1 -Wl,--hash-style=both
# Tue, 06 Dec 2016 22:18:49 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 06 Dec 2016 22:18:49 GMT
ENV PHP_VERSION=5.6.28
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.28.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.28.tar.xz.asc/from/this/mirror
# Tue, 06 Dec 2016 22:18:50 GMT
ENV PHP_SHA256=07187ba2870f89cef334cd2ad6cb801aeec5eaf283da0293a9a6be75d6786d11 PHP_MD5=1e01c66b2e67ab3b56a6180ee560fe4c
# Tue, 06 Dec 2016 22:19:01 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Dec 2016 22:19:02 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 06 Dec 2016 22:22:13 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Wed, 07 Dec 2016 19:12:24 GMT
COPY multi:02856938f72d54124bed9d5b55ba70223cef4d18c06d2738da5fb9713b27e77b in /usr/local/bin/ 
# Wed, 07 Dec 2016 19:12:25 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 19:12:26 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Wed, 07 Dec 2016 19:12:26 GMT
EXPOSE 9000/tcp
# Wed, 07 Dec 2016 19:12:26 GMT
CMD ["php-fpm"]
# Wed, 07 Dec 2016 21:11:35 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Wed, 07 Dec 2016 21:11:37 GMT
WORKDIR /var/www/html
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_VERSION=1.5.2
# Wed, 07 Dec 2016 21:11:37 GMT
ENV BACKDROP_MD5=dbc73ec1841af1b824277a6c1c445250
# Wed, 07 Dec 2016 21:11:41 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz 	&& echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f backdrop.tar.gz 	&& rm backdrop.tar.gz 	&& chown -R www-data:www-data sites
# Wed, 07 Dec 2016 21:11:42 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Wed, 07 Dec 2016 21:11:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Dec 2016 21:11:42 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:386a066cd84a33a04d560c42bef66d1dd64ebfc76de78550e5fd0f8d57778bca`  
		Last Modified: Mon, 07 Nov 2016 20:34:04 GMT  
		Size: 51.4 MB (51356989 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:269e95c6053af006e565f05aa87acc36a1e1dbdf1a7ac29c0de4739bfc0e40ef`  
		Last Modified: Tue, 08 Nov 2016 23:21:22 GMT  
		Size: 77.6 MB (77591280 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6243d5c57a349bb65b8641277fdb52b01726cbeadf307cf33a0293e6a2a17f6c`  
		Last Modified: Tue, 08 Nov 2016 23:21:00 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e33b402f8dab84d89e0cbc7312bfea5f9a57c1fca4b90823205f1082f657a023`  
		Last Modified: Tue, 06 Dec 2016 22:50:31 GMT  
		Size: 12.6 MB (12552031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbb919650a069b03abe443d1a0f4e54c854d7f31488888b11d2f2a074ba858d0`  
		Last Modified: Tue, 06 Dec 2016 22:50:26 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3baf42de3541778d607ce56954f095300c2285aacdea139e1a43e51fd9db682`  
		Last Modified: Tue, 06 Dec 2016 22:50:28 GMT  
		Size: 8.5 MB (8488797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d332211c7a61227c4955de19b4e1df753fdacf37afc1a3e9a809201801879661`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 1.8 KB (1828 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:530065f3a72215af50a85cdbfc251f7864466f2a8ae839497838fba70ca85816`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c42311d28c692c0aa11cf04b1910f39c2156244441af5c663e403842c370dabb`  
		Last Modified: Wed, 07 Dec 2016 19:29:17 GMT  
		Size: 7.6 KB (7630 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19ea7ab39d82e7669c27d2c3303ba57bdd2b980a88003b9af93e5bd5a69820e6`  
		Last Modified: Wed, 07 Dec 2016 21:14:40 GMT  
		Size: 6.9 MB (6883100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:21d81b45a7e9fbad8e270f27e5f7124747224e286dcd093b21b2561548a14cd6`  
		Last Modified: Wed, 07 Dec 2016 21:14:42 GMT  
		Size: 8.1 MB (8072675 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b04a222216ba41c43d3251abd1bf1b0f9cfda6004afd4c36e199e9214d3b8bf9`  
		Last Modified: Wed, 07 Dec 2016 21:14:37 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
