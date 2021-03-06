## `python:rc-windowsservercore`

```console
$ docker pull python@sha256:9d9bfc03f9828d8820f23ee778f6636972829167635a0cd1317db65d4fddb8f6
```

-	Platforms:
	-	windows; amd64

### `python:rc-windowsservercore` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.7 GB (4673085622 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e44ef5b315ac93d730bbf1bbb2327870bf7ae65cd469309d3f8a9f3cbdd4c429`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 15 Nov 2016 00:01:58 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Fri, 09 Dec 2016 00:29:49 GMT
ENV PYTHON_VERSION=3.6.0rc1
# Fri, 09 Dec 2016 00:29:53 GMT
ENV PYTHON_RELEASE=3.6.0
# Fri, 09 Dec 2016 00:29:56 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Fri, 09 Dec 2016 00:32:34 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	(New-Object System.Net.WebClient).DownloadFile($url, 'python.exe'); 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		$pipInstall = ('pip=={0}' -f $env:PYTHON_PIP_VERSION); 	Write-Host ('Installing {0} ...' -f $pipInstall); 	pip install --no-cache-dir --upgrade --force-reinstall $pipInstall; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Fri, 09 Dec 2016 00:32:38 GMT
CMD ["python"]
```

-	Layers:
	-	`sha256:9c7f9c7d9bc2915388ecc5d08e89a7583658285469d7325281f95d8ee279cc60`  
		Size: 3.7 GB (3737824348 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:d33fff6043a134da85e10360f9932543f1dfc0c3a22e1edd062aa9b088a86c5b`  
		Size: 878.9 MB (878852116 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:f24cd6bb1240a6a8641fa44a4bbea3e59d3729b9e1513ca48370c4576b6fddea`  
		Last Modified: Tue, 15 Nov 2016 00:13:12 GMT  
		Size: 1.2 KB (1217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:756ecac1eaccbf6767018c8d12b3002eec060cf1702f9530f070b73b2d8e2f96`  
		Last Modified: Fri, 09 Dec 2016 00:33:02 GMT  
		Size: 1.2 KB (1210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a20ae93861007b2c804b7dae5ff7e2f4d192ceeb88da5fd87302e1a2513295ea`  
		Last Modified: Fri, 09 Dec 2016 00:33:00 GMT  
		Size: 1.2 KB (1224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a044c5771dea5bce624c3f7113545778d70a54fea98f3944323eb574cffc1597`  
		Last Modified: Fri, 09 Dec 2016 00:33:01 GMT  
		Size: 1.2 KB (1214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebe48d2ce92ee154835eb1aafe460565d7240df3d89216544faf1edd62b27bb3`  
		Last Modified: Fri, 09 Dec 2016 00:33:12 GMT  
		Size: 56.4 MB (56403080 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71a0d3e07ea8344b8f41586c1d3bf0c7fb488ec3dcf0f4b7d8fe1eb17cdac90d`  
		Last Modified: Fri, 09 Dec 2016 00:33:01 GMT  
		Size: 1.2 KB (1213 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
