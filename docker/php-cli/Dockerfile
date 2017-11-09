FROM fratellowebshop_php-base

MAINTAINER DIETER PROVOOST <info@dieterprovoost.be>

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Allow Composer to be run as root
ENV COMPOSER_ALLOW_SUPERUSER 1

RUN apt-get update && apt-get install -y \
    nodejs \
    ant \
    sqlite3 \
    yarn

RUN docker-php-ext-install pcntl

WORKDIR /var/www
