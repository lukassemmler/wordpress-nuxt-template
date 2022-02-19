# Based on https://salzam.com/dockerize-wordpress-with-themes-plugins-and-common-configuration/, by Salman Sohail 2019-12-10
FROM wordpress:latest

# Copying Themes and Plugins into the wordpress image
COPY ["./wp-content/plugins","/usr/src/wordpress/wp-content/plugins"]
COPY ["./wp-content/themes","/usr/src/wordpress/wp-content/themes"]

# Applying the execution right on the folders for apache
COPY ["./bin/entrypoint-child.sh","/usr/bin/"]
RUN chmod +x /usr/bin/entrypoint-child.sh
ENTRYPOINT ["entrypoint-child.sh"]
CMD ["apache2-foreground"]

# Updating the configuration of wordpress image with our own
COPY ["./config/uploads.ini","/usr/local/etc/php/conf.d/uploads.ini"]
