Flask in Raspbian

apt-get update
apt-get upgrade
apt-get install vim-nox
apt-get install pylint
apt-get install apache2 mysql-client mysql-server
apt-get install libapache2-mod-wsgi
a2enmod wsgi
cd /var/wwww
mkdir FlaskApp
cd FlaskApp
mkdir FlaskApp
cd FlaskApp
mkdir static
mkdir templates
vim __init__.py

apt-get install python-pip
apt-get install virtualenv
virtualenv venv
source venv/bin/activate
pip install Flask
vim /etc/apache2/sites-available/FlaskApp.conf
<VirtualHost *:80>
        ServerName mywebsite.com
        ServerAdmin admin@mywebsite.com
        WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
        <Directory /var/www/FlaskApp/FlaskApp/>
            Order allow,deny
            Allow from all
        </Directory>
        Alias /static /var/www/FlaskApp/FlaskApp/static
        <Directory /var/www/FlaskApp/FlaskApp/static/>
            Order allow,deny
            Allow from all
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        LogLevel warn
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>


