README
------

### What is this?

This is a basic, but scalable file structure I use for my Flask projects.

I'm providing this here to hopefully speed up and lessen frustration of people new to Flask and especially those new to Flask on Apache.

I haven't reinvented the wheel or anything like that. This is just the template structure I've ended up with after reading several best practices and trying to get Flask to work with mod_wsgi (Which would have went smoother had I checked what python binary my mod_wsgi was compiled against first). 


### Included

I've left some python modules I use in almost every project(and forsee myself using) such as the following: Flask-WTF, Flask-Login, Flask-SQLAlchemy, and MySQL-Python.

If you have no use for these and would rather remove them, feel free to remove the env directory and recreate the virtualenv with `virtualenv env` inside the project root.

I've also included the Bootstrap frontend framework with some basic templates. You can use as much or as little as you want from this package.


### File Tree

```
../procect_folder/
├── config.py = confuration file for flask + modules, such as SQL URI
├── env = python virtualenv folder. holds libraries and python bin for project
├── flask.wsgi = WSGI file for mod_wsgi
├── log
│   ├── access.log
│   └── error.log
├── README.md
├──run.py = Use to run flask development server vs using apache. Not for prod
│
├── app = actual application directory
   ├── __init__.py = imports all modules, config, flask object, general initialization for project
   ├── mod_1 = example module. use modules to structure better. module can be anything from module that handles authentication, payment processing, etc
   │   ├── __init__.py = makes directory a python package
   │   └── views.py = routing logic. module might also include models.py, forms.py, etc depending on what you're doing
   ├── static = static files
   │   ├── css
   │   ├── fonts
   │   ├── img
   │   └── js
   └── templates = html templates with some examples inside. 
       ├── 404.html
       ├── home.html
       ├── layout.html
       └── mod_1
           └── test.html

```
