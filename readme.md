# flask-adminlte-handler
## Introduction
flask-adminlte-handler is a Python based WEB Backend management system scaffolding，The goal is to use a very small amount of code and to quickly build small WEB applications. Do not try this on medium to large projects.

1. Use the more traditional heavy back-end + light front-end approach to reduce the overall code volume.
2. Web framework --> Flask, default Jinja template
3. ORM --> Peewee
4. The front-end application is based on the BootStrap template of AdminLTE

## System Screenshot
- Login Page  
![](http://oh0ra6igz.bkt.clouddn.com/0ot1s.jpg)

- Home Page  
![](http://oh0ra6igz.bkt.clouddn.com/644d6.jpg)

- Editing Interface  
![](http://oh0ra6igz.bkt.clouddn.com/fojv1.jpg)  

- Query interface  
![](http://oh0ra6igz.bkt.clouddn.com/vvelb.jpg)


## third party dependencies
- peewee
- pymysql
- flask
- flask-script
- flask-wtf
- flask-login


## Environment configuration
### venv Virtual environment installation and configuration
```
sudo pip3 install virtualenv
virtualenv venv
. venv/bin/activate
```

### Third-party dependency installation
```
pip3 install -r requirements.txt

```
### System parameter configuration
1. edit `config.py`， Revise SECRET_KEY and MySQL Database related parameters
```
SECRET_KEY = os.environ.get('SECRET_KEY') or 'your-secret'
DB_HOST = '127.0.0.1'
DB_USER = 'foobar'
DB_PASSWD = 'foobar'
DB_DATABASE = 'foobar'
```

2. edit log-app.conf，Revise Log path
```
args=('/path/to/log/flask-rest-sample.log','a','utf8')
```

### Database initialization
1. Automatic table creation
Run directly `python3 models.py`

2. Insert admin user（default admin/admin)
```
INSERT INTO `user` (`id`, `username`, `password`, `fullname`, `email`, `phone`, `status`)
VALUES
	(1, 'admin', 'pbkdf2:sha1:1000$Km1vdx3W$9aa07d3b79ab88aae53e45d26d0d4d4e097a6cd3', 'administrator', 'admin@admin.com', '18612341234', 1);
```

### Start application
```
nohup ./manage.py runserver 2>&1 &
or
./run_app_dev.py (Testing only)
```


## Project directory structure
![](http://oh0ra6igz.bkt.clouddn.com/963uh.jpg)  
- /app/auth  User authentication related codes
- /app/main  Code related to main function points
- /app/static  JS、CSS Wait for static files
- /app/template  Page template
- /app/models.py  Peewee Model
- /app/utils.py  tool module
- /conf  System parameters and log configuration


## Related learning documents
- [http://flask.pocoo.org](http://flask.pocoo.org)
- [https://flask-login.readthedocs.io](https://flask-login.readthedocs.io)
- [https://flask-script.readthedocs.io](https://flask-script.readthedocs.io)
- [https://flask-wtf.readthedocs.io](https://flask-wtf.readthedocs.io)
- [http://docs.peewee-orm.com](http://docs.peewee-orm.com)
- [https://almsaeedstudio.com/preview](https://almsaeedstudio.com/preview)
