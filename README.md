# FSND Web Server (Final Project)

  This project is the final project in FSND program, in this project a wweb server is implemented,
  secured and a web application is uploaded to it.

## Getting Started

  Here is the web application address
  ```
  http://168.62.51.177.xip.io/
  ```

After entering the application you will be able to browse the content, but not adding items, once you are logged in you be able to add items and edit or delete the added items.

The server can be accessed using ssh via port 2200:
```
ssh user@168.62.51.177 -p 2200 -i [key path]
```
it can only be accessed using RSA key.

There are only two users can access this server (main,grader).

## About The Project

The project require upating the index of linux program and upgrade it, and this is done using 
```
$ sudo apt-get update
$ sudo apt-get upgrade
```

You also need to change the used port from 22 to 2200 or any other valid port,
then change the login in method, so user can't log in using password but RSA-key

so insted of entering using the command:
```
$ ssh [username]@[IP address]
```
it will become:
```
$ ssh [username]@[IP address] -p [port number] -i [path to RSA key]
```


After that preventing root login and password log in in addition to port changing, all this done by modifying the file sshd_config:
```
$ sudo nano /etc/ssh/sshd_config
```

Some third party APIs are installed such:
* PostgreSQL
* Apach2
* Mod_wsgi
```
$ sudo apt-get install postgresql postgresql-contrib
$ sudo apt-get install apache2
$ sudo apt-get install libapache2-mod-wsgi
```

In order to make the app works, and respond to HTTP requests, some changes need to be done to apache configuration files
```
$ sudo nano /etc/apache2/sites-enabled/[your application name]
```
Some line sholde be added which can be checked here:
[Modifying Apache2 Configuration Files](https://www.bogotobogo.com/python/Flask/Python_Flask_HelloWorld_App_with_Apache_WSGI_Ubuntu14.php)

and to activate the files after that run:
```
$ sudo a2ensite [config file name]
```




### Used utilities 

This project is done using:
* Azure cloude services
* Apach2 http server
* PostgreSQL DataBase
* Flask 
* mod_wsgi

### Some of Third Party Resources 
* [MediaTemplete](https://mediatemple.net/community/products/dv/204643810/how-do-i-disable-ssh-login-for-the-root-user) - for preventing root login
* [Flask-docs](http://flask.pocoo.org/docs/1.0/patterns/appdispatch/) - for configuration file
* [Garron](https://www.garron.me/en/linux/set-time-date-timezone-ntp-linux-shell-gnome-command-line.html) - setting time zone
* [Several nines](https://severalnines.com/blog/how-secure-your-postgresql-database-10-tips) - Databse securing



## Author

* **Abdullah Alamoodi** - [Github](https://github.com/abady1000)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* **Mashael ElSaeed** - Course instructor
