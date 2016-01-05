FROM ubuntu:xenial

ENV DEBIAN_FRONTEND noninteractive

# Setup repositories
RUN apt-get update
RUN apt-get install -y software-properties-common python-software-properties
RUN apt-get install -y language-pack-en-base
ENV LC_ALL en_US.UTF-8
RUN add-apt-repository ppa:ondrej/php-7.0

# Install packages
RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y php7.0
RUN apt-get install -y php7.0-mcrypt
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

VOLUME ["/data"]
WORKDIR /data

CMD ["composer", "install"]
