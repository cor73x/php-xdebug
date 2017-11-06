FROM ubuntu:precise

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CD44D3EE9CE1C29A

RUN echo "deb http://ppa.launchpad.net/sergey-dryabzhinsky/php52/ubuntu precise main" > /etc/apt/sources.list.d/php52.list \
	&& echo "deb http://ppa.launchpad.net/sergey-dryabzhinsky/packages/ubuntu precise main" > /etc/apt/sources.list.d/php52-packages.list \
	&& echo "deb http://ppa.launchpad.net/sergey-dryabzhinsky/php52-modules/ubuntu precise main" > /etc/apt/sources.list.d/php52-modules.list \
	&& echo "deb http://ppa.launchpad.net/sergey-dryabzhinsky/php-modules/ubuntu precise main" > /etc/apt/sources.list.d/php-modules.list \
	&& apt-get update

RUN apt-get -y install php52-cli php52-common php52-mod-bcmath php52-mod-curl php52-mod-readline \
	php52-mod-dom php52-mod-ftp php52-mod-gd php52-mod-json php52-mod-mbstring php52-mod-mcrypt \
	php52-mod-mysql php52-mod-openssl php52-mod-soap php52-mod-sqlite php52-mod-tokenizer php52-mod-xml \
	php52-mod-xmlreader php52-mod-xmlrpc php52-mod-xmlwriter php52-mod-zip php52-mod-posix \
	git unzip curl file default-mta --no-install-recommends \
	php52-mod-xdebug php52-mod-intl php52-mod-fileinfo php52-mod-redis \
	&& rm -r /var/lib/apt/lists/*

RUN ln -s /etc/php52/conf.d/simplexml.ini /etc/php52/cli/conf.d/simplexml.ini

RUN php52-modset -e xdebug && php52-modset -e fileinfo && php52-modset -e intl && php52-modset -e redis

