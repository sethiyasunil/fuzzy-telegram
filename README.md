# Fuzzy Telegram
*A simple vanilla PHP web application displaying random quote of the day.*


useful commands
#composer
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'e0012edf3e80b6978849f5eff0d4b4e4c79ff1609dd1e613307e16318854d24ae64f26d17af3ef0bf7cfb710ca74755a') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
php composer.phar installer


#setup mysql
$sudo yum install mysql-sever
$sudo service mysqld start
$sudo /usr/bin/mysql_secure_installation
mysql -u root -p
mysql>create database quotesdb;

#create database. It used phinx module for dB migration
export APP_STAGE=development
export ASSETS_BASE_URL=http://fuzzy-telegram-sunil.s3-website.ap-south-1.amazonaws.com/beta/public/
export RDS_DB_NAME=quotesdb
export RDS_HOSTNAME=localhost
export RDS_PASSWORD=
export RDS_USERNAME=root
php composer.phar phinx migrate


#run unit test
php composer.phar test


