# Instalación

Antes de intentar la instalación, revise los [requisitos](requirements.md).

Al [descargar](https://github.com/WoW-CMS/BlizzCMS/archive/refs/heads/master.zip) / [clonar el repositorio](https://github.com/WoW-CMS/BlizzCMS). En el caso de Windows, debe colocar los archivos dentro de `htdocs`, y en el caso de Linux, normalmente la ruta es `/var/www/`, normalmente en una carpeta llamada `html`. Una vez colocados los archivos en las carpetas correspondientes, el CMS abrirá un formulario de instalación por primera vez.

![migration](https://user-images.githubusercontent.com/2810187/144492952-e28090e2-ee35-4fc8-bf82-734f2c06c12a.png)

Como puede ver en la imagen, el CMS tiene algunas validaciones incorporadas. Esto significa que si estas validaciones no se cumplen, el botón para instalarlo no aparecerá por mucho que se rellenen los campos del formulario. A continuación, proporcionamos información sobre lo que hay que rellenar en los formularios.

- **Website Database Hostname:** Es el nombre de dominio o ip de la base de datos que va a utilizar el cms.

A continuación, le damos algún ejemplos:
- `localhost` → Si está trabajando en un entorno de prueba.
- `200.50.29.300` → Una ip pública.
- `wow-cms.com` → un dominio asociado a la máquina o al webhosting donde se está instalando el cms.

**Nota:** Por defecto, el puerto es 3306 en MySQL. Pero si cambia el puerto, puede utilizar el siguiente formato: `localhost:3310` por ejemplo.

- **Website Database Name:** Es el nombre de la base de datos que utilizará el cms.

(Recuerde que el CMS crea las tablas mediante migraciones, pero no crea la base de datos, hay que crearla manualmente).

- **Website Database Username:** Usuario con acceso a la base de datos del cms, para realizar cambios. SELECT, INSERT INTO, UPDATE, DELETE
- **Website Database Password:** Contraseña, de dicho usuario.

En el segundo formulario, se solicitan los datos de la base de datos auth del emulador. No vuelvo a repetir lo que significan los campos, porque básicamente es lo mismo que lo anterior, sólo que se puede cambiar el usuario, el puerto o incluso el hostname. Todo depende del proyecto y la configuración que tenga cada uno, la seguridad, los servidores...

Por ejemplo, si está utilizando MySQL 8.x, puede crear las bases de datos, el usuario y la contraseña con el siguiente script.

Recuerda cambiar la clave, el usuario y la contraseña. No utilice los valores por defecto en sus proyectos de producción.

```sql
DROP USER IF EXISTS 'acore'@'localhost';

CREATE USER 'acore'@'localhost' IDENTIFIED BY 'acore' WITH MAX_QUERIES_PER_HOUR 0 MAX_CONNECTIONS_PER_HOUR 0 MAX_UPDATES_PER_HOUR 0;

CREATE DATABASE `acore_auth` DEFAULT CHARACTER SET UTF8MB4 COLLATE utf8mb4_general_ci;

CREATE DATABASE `blizzcms` DEFAULT CHARACTER SET UTF8MB4 COLLATE utf8mb4_general_ci;

GRANT ALL PRIVILEGES ON `acore_auth` . * TO 'acore'@'localhost' WITH GRANT OPTION;

GRANT ALL PRIVILEGES ON `blizzcms` . * TO 'acore'@'localhost' WITH GRANT OPTION;
```

- En la primera línea, borramos el usuario, si existe.
- En la segunda, lo creamos, estableciendo nombre, modo de conexión y contraseña.
- En la tercera y cuarta, creamos la base de datos auth y la del cms.
- Y en la quinta y sexta, damos permisos al usuario sobre esas bases de datos.

**Nota:** No es necesario crear 2 bases de datos de auth, la base de datos de auth, se suele crear, mientras se compila el emulador, pero a efectos prácticos, aquí explicamos como se puede hacer. [Gracias a AzerothCore, por el script sql](https://github.com/azerothcore/azerothcore-wotlk/blob/master/data/sql/create/create_mysql.sql).

> 6 queries executed, 6 success, 0 errors, 1 warning

![migration_successful](https://user-images.githubusercontent.com/2810187/144518673-3a5e6d1c-e737-4ccd-bd1d-04c3d172e74a.png)

Si todos los datos son correctos, pasará a la siguiente pantalla.

![migration_finish](https://user-images.githubusercontent.com/2810187/144518947-6ef0cb80-df06-4c30-82a5-71590f25c768.png)

- **Server Name:** Este es el nombre del servidor. Por ejemplo: `BlizzCMS test`.
- **Realmlist:** El nombre de host o la IP para acceder al servidor. Por ejemplo: `wow-cms.com` o `200.52.28.177`.
- **Expansion:** Expansión del emulador. Por ejemplo: `Wrath of the Lich King`.
- **Discord Invitation ID:** El ID de la URL de invitación al discord.

Por ejemplo, si la invitación es: https://discord.com/invite/QXhHZpbeu5. Sólo tienes que introducir `QXhHZpbeu5`.

- **Emulator:** El tipo de cifrado que utiliza el emulador. `SRP6`, `Hex`...
- **Bnet Enabled?:** ¿El emulador utiliza bnet?

> En caso de que cometa un error, no se preocupe. Los cambios se pueden hacer más tarde en el archivo de configuración.

![finish_migration](https://user-images.githubusercontent.com/2810187/144524017-eaf2f466-7c9e-4581-be78-cf6cd49473e3.png)

Si todo va bien, deberías ver una imagen similar a esta.

![home](https://user-images.githubusercontent.com/2810187/144524538-ac6282fc-1d39-40f0-937d-cdaf621537a6.png)

La comunidad de BlizzCMS y el personal de WOW-CMS quieren pedirle amablemente que no elimine los créditos del pie de página. Esta es la única manera de dar a conocer el CMS a la gente que aún no lo conoce, y quizás encontrar desarrolladores interesados en participar en el proyecto.

Gracias por descargar y utilizar BlizzCMS.
