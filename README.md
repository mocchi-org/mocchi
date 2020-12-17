# mocchi

Tiny PHP framework with an even smaller footprint.
mocchi is based on Symfony MicroKernel 

## Installation

```bash
git@github.com:SineMah/mocchi.git
```

Rename `.env.example` to `.env`.

Add vhost (Apache)
```apacheconfig
# /etc/apache2/sites-available/mocchi.conf
<VirtualHost *:80>
    ServerName dev.mocchi
    ServerAlias www.dev.mocchi
    
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/mocchi/public
    
    <Directory /var/www/mocchi/public>
        AllowOverride All
        Allow from All
        Require all granted
        Options Indexes FollowSymLinks
        
        FallbackResource /index.php
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Enable configuration and reload Apache.

```bash
a2ensite mocchi.conf
systemctl reload apache2
```

## Keep in mind
* Twig templating
* no Db adapter - use whatever you want and need
* use middleware
* use mocchi as a skeleton to create apps as fast as possible

## License
MIT