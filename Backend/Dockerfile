FROM composer

#COPY composer.lock composer.json /var/www/

#COPY database /var/www/database

WORKDIR /laravelapp

#copie des contenus en local dans le dossier du container docker
COPY . /laravelapp

EXPOSE 8000

#RUN se lance avec docker build
## CMD (1 seul, le dernier !) se lance au moment du docker run 
CMD php artisan serve --host=0.0.0.0 --port=8000
#mises à jour préalables + git init
#RUN apt-get update && apt-get -y install git && apt-get -y install zip

#installation de composer
#COPY --from=composer /usr/bin/composer /usr/bin/composer
#RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
#    && php -r "if (hash_file('SHA384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
#    && php composer-setup.php \
#    && php -r "unlink('composer-setup.php');" \
#    && php composer.phar install --no-dev --no-scripts \
#    && rm composer.phar



#RUN chown -R www-data:www-data \
#       /var/www/storage \
#      /var/www/bootstrap/cache

#RUN php artisan cache:clear

#RUN php artisan optimize

# installation du driver entre Laravel et la DB
#RUN  apt-get install -y libmcrypt-dev \
#        libmagickwand-dev --no-install-recommends \
#        && pecl install mcrypt-1.0.2 \
#        && docker-php-ext-install pdo_mysql \
#        && docker-php-ext-enable mcrypt

#renommage du fichier .env.prod récupéré après un gitclone 
#RUN mv .env.prod .env
 
#optimize : remove the cached version of .env
#RUN php artisan optimize