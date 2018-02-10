# Docker image of Nginx and PHP
Docker image based on Alpine Linux 3.7 with Nginx, PHP, PHP extension Pinba, Composer and Git 

Run the image:
`docker run -d --name php -p 80:80 vendelev/php:7.1` 
Then you can type http://localhost or http://host-ip in your browser and see phpinfo.

Document root for your project: /var/www/web

Versions of apps:
Nginx: 1.12.2
PHP: 7.1.14
Composer: 1.6.3

Image contains the following extensions:
- mbstring
- iconv
- mysqli
- pdo_mysql
- gd
- json
- memcached
- mcrypt
- amqp
- xdebug
- zip
- xml
- bcmath
- curl
- phar
- zlib
- pear
- soap
- pcntl
- ctype
- posix
- fileinfo
- session
- imagick
- opcache
- dev
- openssl
- redis
- pgsql
- intl
- gmp
- dom
- tokenizer
- xmlwriter
- pinba

The extensions Pinba and Xdebug are disabled (see pinba.ini, xdebug.ini), you can enable them in your child images. Expample: `RUN sed -i 's/pinba.enabled=0/pinba.enabled=1/g' /etc/php7/conf.d/20-pinba.ini`

By default, the image exposes the the following ports:
- 80 Nginx
- 9000 PHP
- 9999 Supervisor