#
C9 Install Data

```
$ mysql-ctl start

$ mysql-ctrl install

$ phpmyadmin-ctl install.

$ rm README.md php.ini hello-world.php

$ sudo composer self-update

$ composer create-project laravel/laravel ./laravel --prefer-dist shopt -s dotglob

$ mv laravel/* ./

$ rm -rf laravel

$ sudo nano /etc/apache2/sites-enabled/001-cloud9.conf
```

### Change this line

```
$ DocumentRoot /home/ubuntu/workspace
```

### To following

```
$ DocumentRoot /home/ubuntu/workspace/public
$ sudo composer update
---------------------------# update composer
$ mysql-ctl cli
$ use c9;


```

select @@hostname;

exit

```
DB\_HOST=localhost
DB\_DATABASE=c9
DB\_USERNAME='name'
DB\_PASSWORD=
```

install laravel

---

rm README.md php.ini hello-world.php

sudo composer self-update

composer create-project laravel/laravel ./laravel --prefer-dist

shopt -s dotglob

mv laravel/\* ./

rm -rf laravel

sudo nano /etc/apache2/sites-enabled/001-cloud9.conf

composer require appzcoder/crud-generator

add the service provider to config/app.php

'providers' =&gt; \[

..

Appzcoder\CrudGenerator\CrudGeneratorServiceProvider::class,

\]

install laraavelcollective/html helper package.

Run

composer require laravelcollective/html

Add service provider & aliases to config/app.php

'providers' =&gt; \[

...

Collective\Html\HtmlServiceProvider::class,

\]

'aliases' =&gt; \[

...

'Form' =&gt; Collective\Html\FormFacade::class,

'HTML' =&gt; Collective\Html\HtmlFacade::class,

\]

Run composer dump-autoload

Publish vendor files of this package

php artisan vendor:publish --provider="Appzcoder\CrudGenerator\CrudGeneratorServiceProvider"

Note: You shold have configured database for this operation

Commands

Crud command

php artisan crud:generate Posts --fields="title\#string; content\#text ; category\#select\#options=technology,tips,health" --view-path=admin --controller-namespace=Admin --route-group=admin

mysql-ctl cli

change

.env file for database credentials

php artisan migrate

goto

localhost:88/laravel5/public/admin/posts

[https://community.c9.io/t/laravel-5-3-installation-on-cloud9/9038?u=prenna](https://community.c9.io/t/laravel-5-3-installation-on-cloud9/9038?u=prenna)

-----------------update php

sudo add-apt-repository ppa:ondrej/php

sudo apt-get update

sudo apt-get install libapache2-mod-php5.6

sudo a2dismod php5

sudo a2enmod php5.6

sudo add-apt-repository ppa:ondrej/php5-compat

sudo apt-get update

sudo apt-get dist-upgrade

---

------------install laravel

sudo composer global require 'laravel/installer'

export PATH=~/.composer/vendor/bin:$PATH

laravel new laravel

---

sudo nano /etc/apache2/sites-enabled/001-cloud9.conf

DocumentRoot /home/ubuntu/workspace/public

---

Add authentication routes to your app.

Enter the following into the terminal:

php artisan make:auth

php artisan migrate

---

Update NPM and node

NPM and Node need upgrading so that gulp and elixir work properly. Just enter the following commands after the rest of your installation, then the gulp command should work fine.

sudo npm install -g n

sudo n latest

sudo npm install -g npm

npm inst

[https://www.cloudways.com/blog/category/applications/laravel/\\#blg-catg-sec](https://www.cloudways.com/blog/category/applications/laravel/\#blg-catg-sec)
