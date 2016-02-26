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

## Install apache2 (httpd-2.0)
* Install the lastest stable version of httpd from the website
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


## Future work
Now you have finished all the required steps. You can do the further tasks to employ your own applicationon the server as you wish.
If you've encounted any problems, please do not hesitate to send an email to ```Clark YAN (me)``` at ```clarkyan1993@gmail.com``` or opening an issue on github.

