# Requirements

In order to install the CMS, a web server is required.

In the case of Windows, you can use [XAMPP](https://www.apachefriends.org/es/index.html)

The project uses [CodeIgniter framework](https://codeigniter.com/) version 3 as its core. This is only information for developers who want to contribute to it. If you are only going to use the CMS, this information is not really necessary. The default theme, called default, is created, with the help of [UIkit](https://getuikit.com/). However, you can create your own themes, using this framework or others, such as [Bootstrap](https://getbootstrap.com/).

In case you are using Linux, you need to install [Apache](https://httpd.apache.org/) or [Nginx](https://www.nginx.com/).

**Note:** Please note that the CMS does not support PHP version 8.x at the moment.

You will also need to enable php extensions and apache modules.

#### Apache Modules

- [mod_headers](https://httpd.apache.org/docs/2.4/mod/mod_headers.html)
- [mod_rewrite](https://httpd.apache.org/docs/2.4/mod/mod_rewrite.html)
- [mod_expires](https://httpd.apache.org/docs/2.4/mod/mod_expires.html)

#### PHP Extensions

- [curl](https://www.php.net/manual/en/book.curl.php)
- [gd](https://www.php.net/manual/en/book.image.php)
- [mbstring](https://www.php.net/manual/en/mbstring.installation.php)
- [mysqli](https://www.php.net/manual/en/book.mysqli.php)
- [openssl](https://www.php.net/manual/en/book.openssl.php)
- [soap](https://www.php.net/manual/en/class.soapclient.php)
- [gmp](https://www.php.net/manual/en/book.gmp.php)

### Some configurations to be made in linux

Since the emulator uses the apache2 mod_rewrite, in order to write friendly URLs. It is necessary to enable this module. In case you are using a terminal. If you are using a web hosting, this configuration must be done by your provider.

**Note:** Before hiring a hosting server or VPS, make sure that they enable the necessary ports or that they have all the extensions, because not all services sometimes offer that.

## Some configurations

#### Apache Modules

You can use the following command to enable the apache extensions mentioned above.

```sh
a2enmod headers
a2enmod rewrite
a2enmod expires
```

#### Edit Sites Available

/etc/apache2/sites-available/000-default.conf

For the mod_rewrite to work correctly and generate friendly URLs, it is necessary to have permissions on the directory where the CMS is located, commonly, located in `/var/www/html`.

```
<Directory "/var/www/html">
    AllowOverride All
</Directory>
```

#### Restarting the service

```sh
/etc/init.d/apache2 restart
```
