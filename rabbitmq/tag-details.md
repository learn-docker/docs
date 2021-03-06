<!-- THIS FILE IS GENERATED VIA '.template-helpers/generate-tag-details.pl' -->

# Tags of `rabbitmq`

-	[`rabbitmq:3.6.3`](#rabbitmq363)
-	[`rabbitmq:3.6`](#rabbitmq36)
-	[`rabbitmq:3`](#rabbitmq3)
-	[`rabbitmq:latest`](#rabbitmqlatest)
-	[`rabbitmq:3.6.3-management`](#rabbitmq363-management)
-	[`rabbitmq:3.6-management`](#rabbitmq36-management)
-	[`rabbitmq:3-management`](#rabbitmq3-management)
-	[`rabbitmq:management`](#rabbitmqmanagement)

## `rabbitmq:3.6.3`

```console
$ docker pull rabbitmq@sha256:04a7bbe130908246c646fc2c8ec98fc192f01ec1efe18f637a2c23131f0ee351
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3.6.3` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:07ad51c82a295125321871741706a28c1e53ce0225468320c4daddd7a389db20`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B

## `rabbitmq:3.6`

```console
$ docker pull rabbitmq@sha256:04a7bbe130908246c646fc2c8ec98fc192f01ec1efe18f637a2c23131f0ee351
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3.6` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:07ad51c82a295125321871741706a28c1e53ce0225468320c4daddd7a389db20`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B

## `rabbitmq:3`

```console
$ docker pull rabbitmq@sha256:04a7bbe130908246c646fc2c8ec98fc192f01ec1efe18f637a2c23131f0ee351
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:07ad51c82a295125321871741706a28c1e53ce0225468320c4daddd7a389db20`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B

## `rabbitmq:latest`

```console
$ docker pull rabbitmq@sha256:04a7bbe130908246c646fc2c8ec98fc192f01ec1efe18f637a2c23131f0ee351
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:latest` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407322 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:07ad51c82a295125321871741706a28c1e53ce0225468320c4daddd7a389db20`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B

## `rabbitmq:3.6.3-management`

```console
$ docker pull rabbitmq@sha256:34e2d37bbf141042840ce9efdbd0d7dfcc2101b4db135c55358b82dd84120694
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3.6.3-management` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fee9b40e0edcf4c6daf8d3e9a36fa67aa521073bd9e64b0f4f6b1c137c9ba36b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
# Fri, 08 Jul 2016 19:58:12 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Fri, 08 Jul 2016 19:58:13 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B
	-	`sha256:6da386aad6a32d738915efc642d6f7563f95eb683b46c964f7a2361b1ce24093`  
		Last Modified: Fri, 08 Jul 2016 19:59:01 GMT  
		Size: 186.0 B

## `rabbitmq:3.6-management`

```console
$ docker pull rabbitmq@sha256:34e2d37bbf141042840ce9efdbd0d7dfcc2101b4db135c55358b82dd84120694
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3.6-management` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fee9b40e0edcf4c6daf8d3e9a36fa67aa521073bd9e64b0f4f6b1c137c9ba36b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
# Fri, 08 Jul 2016 19:58:12 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Fri, 08 Jul 2016 19:58:13 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B
	-	`sha256:6da386aad6a32d738915efc642d6f7563f95eb683b46c964f7a2361b1ce24093`  
		Last Modified: Fri, 08 Jul 2016 19:59:01 GMT  
		Size: 186.0 B

## `rabbitmq:3-management`

```console
$ docker pull rabbitmq@sha256:34e2d37bbf141042840ce9efdbd0d7dfcc2101b4db135c55358b82dd84120694
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3-management` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fee9b40e0edcf4c6daf8d3e9a36fa67aa521073bd9e64b0f4f6b1c137c9ba36b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
# Fri, 08 Jul 2016 19:58:12 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Fri, 08 Jul 2016 19:58:13 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B
	-	`sha256:6da386aad6a32d738915efc642d6f7563f95eb683b46c964f7a2361b1ce24093`  
		Last Modified: Fri, 08 Jul 2016 19:59:01 GMT  
		Size: 186.0 B

## `rabbitmq:management`

```console
$ docker pull rabbitmq@sha256:34e2d37bbf141042840ce9efdbd0d7dfcc2101b4db135c55358b82dd84120694
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:management` - linux; amd64

-	Docker Version: 1.10.3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.4 MB (86407508 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fee9b40e0edcf4c6daf8d3e9a36fa67aa521073bd9e64b0f4f6b1c137c9ba36b`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Thu, 09 Jun 2016 21:28:42 GMT
ADD file:76679eeb94129df23c99013487d6b6bd779d2107bf07d194a524fdbb6a961530 in /
# Thu, 09 Jun 2016 21:28:43 GMT
CMD ["/bin/bash"]
# Fri, 10 Jun 2016 04:20:47 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Fri, 10 Jun 2016 04:20:47 GMT
ENV GOSU_VERSION=1.7
# Fri, 10 Jun 2016 04:22:10 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Fri, 10 Jun 2016 04:22:27 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 434975BD900CCBE4F7EE1B1ED208507CA14F4FCA
# Fri, 10 Jun 2016 04:22:28 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Thu, 07 Jul 2016 19:51:53 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:51:54 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Thu, 07 Jul 2016 19:52:12 GMT
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 07 Jul 2016 19:52:13 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Thu, 07 Jul 2016 19:52:14 GMT
ENV RABBITMQ_VERSION=3.6.3
# Thu, 07 Jul 2016 19:52:15 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.3-1
# Thu, 07 Jul 2016 19:53:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Thu, 07 Jul 2016 19:53:17 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 07 Jul 2016 19:53:19 GMT
RUN echo '[ { rabbit, [ { loopback_users, [ ] } ] } ].' > /etc/rabbitmq/rabbitmq.config
# Thu, 07 Jul 2016 19:53:19 GMT
ENV HOME=/var/lib/rabbitmq
# Thu, 07 Jul 2016 19:53:21 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod 777 /var/lib/rabbitmq /etc/rabbitmq
# Thu, 07 Jul 2016 19:53:22 GMT
VOLUME [/var/lib/rabbitmq]
# Thu, 07 Jul 2016 19:53:24 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Thu, 07 Jul 2016 19:53:25 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Fri, 08 Jul 2016 19:58:01 GMT
COPY file:579fd6a1a1fea4d2bd195068ad79d43f3205dc06af9fc3d67be75b8a7721c50b in /usr/local/bin/
# Fri, 08 Jul 2016 19:58:03 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Fri, 08 Jul 2016 19:58:03 GMT
ENTRYPOINT &{["docker-entrypoint.sh"]}
# Fri, 08 Jul 2016 19:58:04 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Fri, 08 Jul 2016 19:58:05 GMT
CMD ["rabbitmq-server"]
# Fri, 08 Jul 2016 19:58:12 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Fri, 08 Jul 2016 19:58:13 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:5c90d4a2d1a8dfffd05ff2dd659923f0ca2d843b5e45d030e17abbcd06a11b5b`  
		Last Modified: Thu, 09 Jun 2016 21:30:47 GMT  
		Size: 51.4 MB (51352535 bytes)
	-	`sha256:6089c6f096b9ba886c0c63a12ed75987261936d8bcbbeb85c69891c5d04ef511`  
		Last Modified: Thu, 07 Jul 2016 19:53:51 GMT  
		Size: 4.3 KB (4341 bytes)
	-	`sha256:23b5bfce8ad4204d923fa6ca9a06a8c72f585647049849238d9fbc8075f6e50f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 1.2 MB (1236805 bytes)
	-	`sha256:13946ed574202c349d5154ee962e9c2e4131d54ef4e94116795a86de100b566f`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 2.5 KB (2509 bytes)
	-	`sha256:f87077e96db630a06e1cbe1878c92d25d7f0153ee5ca7a237c39e17be426e7a5`  
		Last Modified: Thu, 07 Jul 2016 19:53:50 GMT  
		Size: 225.0 B
	-	`sha256:91b271af1b6f22af8d44aab397b8d70fb290ef923283eeb7dc335b48efe1957d`  
		Last Modified: Thu, 07 Jul 2016 19:53:52 GMT  
		Size: 27.5 MB (27517804 bytes)
	-	`sha256:ae50560319c725c8e63c3f8f6f4bac07d336d3735d417c3edab4ce57841ec864`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 5.4 KB (5353 bytes)
	-	`sha256:031a1dcbb47da39f3a5e5552d23e234660b66c6c321f744ee322fc27683fe104`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 214.0 B
	-	`sha256:6ca65936d19d5fa7a85c5daddf201105c8b0d98b5f03be3bfb085abb3d6e4267`  
		Last Modified: Thu, 07 Jul 2016 19:53:48 GMT  
		Size: 6.3 MB (6282106 bytes)
	-	`sha256:44da2c895b8fd5bcee7d290ffa6cd02aab0668b59916d14dfd96e685b2f29344`  
		Last Modified: Thu, 07 Jul 2016 19:53:47 GMT  
		Size: 191.0 B
	-	`sha256:b33963637358cf38692bb1a57e376da1b53edcef531261b0b94042e2f7c1087c`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 2.3 KB (2297 bytes)
	-	`sha256:03658b60e6d0d290dc55061da95b070d62af56b77dc14bd0367e9d8af3c16683`  
		Last Modified: Thu, 07 Jul 2016 19:53:45 GMT  
		Size: 147.0 B
	-	`sha256:cb39c06c1a97d73030e384e2b31ac143327891e9f02e7bbe21bb2b206684d0d7`  
		Last Modified: Thu, 07 Jul 2016 19:53:44 GMT  
		Size: 126.0 B
	-	`sha256:147d1eaf83d5bb5ec8f5677bfecbc45b2b4feb10f04fb18f8bdfff373ebd8704`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 2.6 KB (2551 bytes)
	-	`sha256:d603280e7bb84ee1fc82f932982ec42cc0fe7eaa029f1fcab280e650a9acb5b8`  
		Last Modified: Fri, 08 Jul 2016 19:58:20 GMT  
		Size: 118.0 B
	-	`sha256:6da386aad6a32d738915efc642d6f7563f95eb683b46c964f7a2361b1ce24093`  
		Last Modified: Fri, 08 Jul 2016 19:59:01 GMT  
		Size: 186.0 B
