FROM php:8.3-fpm

# Install unzip
RUN apt-get update && apt-get install -y \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl \
    libzip-dev \
    libonig-dev \
    libxml2-dev

# Limpiar cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Composer using another strategy but with the same result
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set the environment variables
ENV HOME="/root"
ENV PATH="/root/.composer/vendor/bin:${PATH}:/root/.bun/bin"

# Install Bun
RUN curl -fsSL https://bun.sh/install | bash

# Create some symlinks to the bun executable
RUN ln -s $(which bun) /usr/local/bin/npm
RUN ln -s $(which bunx) /usr/local/bin/npx

# Install Laravel Installer
RUN composer global require laravel/installer

# Install pcntl extension
RUN docker-php-ext-install pdo_mysql mbstring zip exif pcntl bcmath
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install gd


CMD 'php-fpm'

EXPOSE 8000