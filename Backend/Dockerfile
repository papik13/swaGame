# Use the specified PHP image from Microsoft Container Registry
FROM mcr.microsoft.com/devcontainers/php:1-8.2-bullseye

# Install Composer globally
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copy your project files into the container
WORKDIR /var/www/html
COPY . .

# Provide permissions for the work directory and link it to the Apache web root, then run Composer install if composer.json exists
RUN sudo chmod a+x /var/www/html && \
    sudo rm -rf /var/www/html && \
    sudo ln -s /var/www/html /var/www/html && \
    if [ -f composer.json ]; then composer install; fi

# Forward port 8080 to the host (as specified in devcontainer.json)
EXPOSE 8080

# Use the default Apache foreground command to run the server
CMD ["apache2-foreground"]
