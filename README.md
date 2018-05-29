# config-phalcon-and-mongodb-on-ubuntu-windows
How to config phalcon and mongodb on ubuntu windows until work

### install lxrun.exe
```
lxrun.exe /install
```
### uninstall lxrun.exe

```
lxrun.exe /uninstall /full
```


if you got problem you can uninstall and install again.

### Next you need to install mongoDB on ubuntu windows. You need to run.

Import they key for the official MongoDB repository.

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
```

Than create a list file for MongoDB.

```
echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
```

Update the packages list.

```
sudo apt-get update
```

Now we can install the MongoDB package itself.

```
sudo apt-get install -y mongodb-org
```


### PhalconPhp with PHP7 installation on ubuntu:16.04


```
sudo apt-get install -y php7.0-fpm \php7.0-cli \php7.0-curl \php7.0-gd \php7.0-intl \php7.0-pgsql \php7.0-mbstring \php7.0-xml \php-msgpack \curl \vim \wget \git
```


### For zephir installtion; the following packages are needed in Ubuntu:

```
sudo apt-get install -y gcc make re2c libpcre3-dev php7.0-dev build-essential php7.0-zip
```


### Install composer

```
sudo curl -sS http://getcomposer.org/installer | php
```


```
sudo mv composer.phar /usr/local/bin/composer
```


### Install zephir

```
sudo composer global require "phalcon/zephir:dev-master"
```


### Install phalcon dev tool

```
sudo composer require "phalcon/devtools" -d /usr/local/bin/
```


```
sudo ln -s /usr/local/bin/vendor/phalcon/devtools/phalcon.php /usr/bin/phalcon
```



### Install phalconphp with php7

```
sudo git clone https://github.com/phalcon/cphalcon.git -b 2.1.x --single-branch
```


```
cd cphalcon/
```


```
sudo ~/.composer/vendor/bin/zephir build --backend=ZendEngine3
```


```
sudo echo "extension=phalcon.so" >> /etc/php/7.0/fpm/conf.d/20-phalcon.ini
```


```
sudo echo "extension=phalcon.so" >> /etc/php/7.0/cli/conf.d/20-phalcon.ini
```


### restart php-fpm

```
sudo service php7.0-fpm restart
```


you can also check there
[github Tosyn](https://gist.github.com/Tosyn/fef6437dd3906ff200e471e478eaae95).
[Phalcon Instalation](https://docs.phalconphp.com/en/3.3/installation)


We use PECL for install mongoDb Driver.
### Install PECL

```
sudo apt-get install php-pear
```


```
sudo apt-get install php5-dev
```


if you get error.
[Install PECL packages on ubuntu](https://askubuntu.com/questions/403327/install-pecl-packages-on-ubuntu).

### Install mongoDB Driver

```
pecl install mongodb
```


If you need to Update mongoDB driver
### Update mongoDB Driver

```
pecl upgrade mongodb
```



[install-phpize-for-php7-ubuntu](https://askubuntu.com/questions/819797/is-is-possible-to-install-phpize-for-php7-ubuntu16-04?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)
[lxrun /uninstall](https://www.neontribe.co.uk/windows-10-bash-ubuntu-16-04-upgrade/)

use if error [Unable to locate package php7.0 [duplicate]](https://askubuntu.com/questions/715944/unable-to-locate-package-php7-0?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)
```
apt-add-repository ppa:ondrej/php
```
