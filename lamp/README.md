# LAMP Dockerfile

Easily set up and develop on a LAMP stack, using [Development Environment](http://github.com/robloach/dockerfiles).


## Features

* [Dev](../dev)
* [Apache](https://httpd.apache.org/) 2.4.7
* [PHP](http://php.net/) 5.5.9
* [MySQL](http://www.mysql.com/) 5.5.37
* [phpMyAdmin](http://www.phpmyadmin.net/) 4.0.10
* [Composer](http://getcomposer.org) 1.0.0-alpha8


## Usage

### Install

Pull `robloach/dockerfiles:lamp` from the Docker repository:
```
docker pull robloach/dockerfiles:lamp
```

Or build `robloach/dockerfiles:lamp` from source:
```
git clone https://github.com/RobLoach/Dockerfiles.git
cd Dockerfiles
docker build -t robloach/dockerfiles:lamp lamp
```

### Run

Run the image, binding associated ports, and mounting the present working
directory:

```
docker run -p 880:80 -p 222:22 -p 33306:3306 -v $(pwd):/var/www/html:rw robloach/dockerfiles:lamp
```


## Services

Service     | Port | Usage
------------|------|-------
SSH         | 22   | Connect with `ssh root@localhost -p 422` with the password `root`
Apache      | 80   | Visit `http://localhost:880` in your browser
phpMyAdmin  | 80   | Visit `http://localhost:880/phpmyadmin` in your browser
MySQL       | 3306 | Connect on `localhost:3306`, user `root`, password `root`
