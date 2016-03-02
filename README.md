# buildService
This project is a tool for building server on ubuntu with apache, mysql and php automatically.

This project can be recommended for building on Ubuntu 14.04

## Install some related library dependencies in the beginning
* Try to ```update``` your software first
```
sudo apt-get update
```
* Install ```gcc``` and ```g++``` to your current operating system
```
sudo apt-get install gcc g++
```
* Install ```libjpeg-dev``` and ```libpng-dev``` to your current operating system
```
sudo apt-get install libjpeg-dev libpng-dev
```
* Install the ```make``` instruction to your current operating system
```
sudo apt-get install make
```
* Install ```apr```, ```apr-util``` and ```pcre```

  Install the lastest stable version of ```apr```
```
wget http://archive.apache.org/dist/apr/apr-1.5.2.tar.gz
tar -zxf apr-1.5.2.tar.gz
cd apr-1.5.2
./configure --prefix=/usr/local/apr
make
sudo make install
```
  Install the lastest stable version of ```apr-util```
```
wget http://archive.apache.org/dist/apr/apr-util-1.5.4.tar.gz
tar -zxf apr-util-1.5.4.tar.gz
cd apr-util-1.5.4
./configure --prefix=/usr/local/apr-util --with-apr=/usr/local/apr/bin/apr-1-config
make
sudo make install
```
  Install the lastest stable version of ```pcre```
```
wget http://jaist.dl.sourceforge.net/project/pcre/pcre/8.38/pcre-8.38.tar.gz
tar -zxf pcre-8.38.tar.gz
cd pcre-8.38
./configure --prefix=/usr/local/pcre
make
sudo make install
```

## Install MYSQL 
* Install ```mysql-server```, and you need to set your own password during the installation
```
sudo apt-get install mysql-server
```
* Install ```mysql-client```
```
sudo apt-get install mysql-client
```
* Install the ```mysql-client lib``` library dependency
```
sudo apt-get install libmysqlclient15-dev
```
* After finish installing the related ```mysql``` files, you can test your tasks (Type your own password)
```
mysql -u root -p
```

## Install apache2 and httpd-2.0
* Install ```apache2```
```
sudo apt-get install apache2
```
* Install the lastest stable version of ```httpd``` from the website
```
wget http://mirrors.tuna.tsinghua.edu.cn/apache//httpd/httpd-2.4.18.tar.gz
```
  You can change the version according to the following website
```
http://httpd.apache.org/download
```
* Unzip this ```tar``` file
```
tar zxvf  httpd-2.4.18.tar.gz
```
* Move the Unzip file to /usr/src/apache2
```
sudo mv httpd-2.4.18 /usr/src/apache2
```
  If there is not an ```apache2``` under your directory, try to create a new file called ```apache2```
```
sudo mkdri /usr/src/apache2
```
* Configure ```httpd```
```
cd /usr/src/apache2/httpd-2.4.18
./configure -prefix=/usr/local/apache  -enable-module=so  -enable-rewrite=shared -enable-authn-dbm --with-apr=/usr/local/apr --with-apr-util=/usr/local/apr-util/ --with-pcre=/usr/local/pcre
```
* Compile ```httpd``` and Install ```httpd```
```
make
sudo make install
```
* Start ```apache```
```
cd /usr/local/apache/bin
sudo ./apachectl -k start (to start)
sudo ./apachectl -k stop (to stop)
sudo ./apachectl -k restart (to restart)
```

## Install PHP7
* Install the related lib libraries
```
sudo apt-get install libxml2-dev
sudo apt-get install libapache2-mod-php5
```
* Install the lastest stable version of ```PHP``` from the website
```
http://www.php.net/downloads.php
```
* Unzip this ```tar``` file
```
tar zxvf  php-7.0.3.tar.gz
```
* Move the Unzip file to /usr/src/apache2
```
sudo mv php-7.0.3 /usr/src/php7
```
* Configure ```php-7.0.3```
```
cd /usr/src/php/php-7.0.3
./configure -prefix=/usr/local/php5 -with-apxs2=/usr/local/apache/bin/apxs -with-mysql=/usr/  -with-mysqli=/usr/bin/mysql_config -with-gd  -with-pear -with-libxml-dir
```
* Compile ```php-7.0.3``` and Install ```php-7.0.3```
```
make
sudo make install
``` 

## Test the environment
* Try to open your browser and type the following address, the welcome page of apache2 will be shown here. ```"It works!"```  
```
http://localhost/ or http://[your server's IP address]/
```

## Encounted problems
* When you do the configuration of php-7.0.3, you may meet an error
```
make: ***[ext/date/lib/parse_date_lo]
```

  Suggestion: Try to use the following instructions and then do the previous configuration again
```
./configure --disable-all --disable-cgi
sudo make clean
```
* Do I need to install all the dependencies?

  Suggestion: The readme file is based on a raw ubuntu system, so all the related dependencies are needed. If you have already been installing some of them, actually, you do not need to install them again.


## Future work
Now you have finished all the required steps. You can do the further tasks to employ your own applicationon the server as you wish.
If you've encounted any problems, please do not hesitate to send an email to ```Clark YAN (me)``` at clarkyan1993@gmail.com or opening an issue on github.

