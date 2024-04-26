
# Use the official WordPress image as the base image
FROM wordpress:latest

# Set the working directory to /var/www/html
WORKDIR /var/www/html

# Copy the contents of the local wp-content directory to the container's wp-content directory
COPY ./wp-content /var/www/html/wp-content
RUN apt-get update && \
apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libzip-dev \
&& docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install -j$(nproc) gd mysqli zip

