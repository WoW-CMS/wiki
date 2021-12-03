# Requisitos

Para instalar el CMS, se necesita un servidor web.

En el caso de Windows, puedes utilizar [XAMPP](https://www.apachefriends.org/es/index.html)

El proyecto utiliza [CodeIgniter framework](https://codeigniter.com/) versión 3 como núcleo. Esto es sólo información para los desarrolladores que quieran contribuir con él. Si sólo vas a utilizar el CMS, esta información no es realmente necesaria. El tema por defecto, llamado default, es creado con la ayuda de [UIkit](https://getuikit.com/). Sin embargo, puedes crear tus propios temas, utilizando este framework u otros, como por ejemplo [Bootstrap](https://getbootstrap.com/).

En el caso de que utilices Linux, tienes que instalar [Apache](https://httpd.apache.org/) o [Nginx](https://www.nginx.com/).

**Nota:** Por favor, tenga en cuenta que el CMS no es compatible con la versión 8.x de PHP en este momento.

También tendrá que habilitar las extensiones de php y los módulos de apache.

#### Módulos Apache

- [mod_headers](https://httpd.apache.org/docs/2.4/mod/mod_headers.html)
- [mod_rewrite](https://httpd.apache.org/docs/2.4/mod/mod_rewrite.html)
- [mod_expires](https://httpd.apache.org/docs/2.4/mod/mod_expires.html)

#### Extensiones de PHP

- [curl](https://www.php.net/manual/en/book.curl.php)
- [gd](https://www.php.net/manual/en/book.image.php)
- [mbstring](https://www.php.net/manual/en/mbstring.installation.php)
- [mysqli](https://www.php.net/manual/en/book.mysqli.php)
- [openssl](https://www.php.net/manual/en/book.openssl.php)
- [soap](https://www.php.net/manual/en/class.soapclient.php)
- [gmp](https://www.php.net/manual/en/book.gmp.php)

### Algunas configuraciones a realizar en linux

Dado que el emulador utiliza el mod_rewrite de apache2, para escribir URLs amigables. Es necesario habilitar este módulo. En caso de que esté utilizando una terminal. Si está utilizando un servidor web, esta configuración debe ser realizada por su proveedor.

**Nota:** Antes de contratar un servidor de hosting o VPS, asegúrate de que habiliten los puertos necesarios o que tienen todas las extensiones de php y módulos de apache, porque no todos los servicios a veces lo ofrecen.

## Algunas configuraciones

#### Módulos Apache

Puede utilizar el siguiente comando para habilitar las extensiones de apache mencionadas anteriormente.

```sh
a2enmod headers
a2enmod rewrite
a2enmod expires
```

#### Editar el fichero sites-available/

/etc/apache2/sites-available/000-default.conf

Para que el mod_rewrite funcione correctamente y genere URLs amigables, es necesario tener permisos sobre el directorio donde se encuentra el CMS, comúnmente, ubicado en `/var/www/html`.

```
<Directory "/var/www/html">
    AllowOverride All
</Directory>
```

#### Reiniciar el servicio

```sh
/etc/init.d/apache2 restart
```
