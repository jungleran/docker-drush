FROM jungleran/drupal-base:8.5.1-apache

MAINTAINER Jungle Ran <jungle.r@intergreat.com>

# Add common extensions
RUN apt-get update && apt-get install -y mysql-client
RUN docker-php-ext-install pdo_mysql

# Set the Drush version.
ENV DRUSH_VERSION 8.1.16

# Install Drush 8 with the phar file.
RUN curl -fsSL -o /usr/local/bin/drush "https://github.com/drush-ops/drush/releases/download/$DRUSH_VERSION/drush.phar" \
  && chmod +x /usr/local/bin/drush

RUN drush --version

# Update the entry point of the application
ENTRYPOINT ["drush"]
