# Crear un reino

El siguiente ejemplo se realiza en el emulador AzerothCore.

Consulta la documentación del emulador que utilices para ver las diferencias.

Lo primero que tenemos que hacer es entrar con un usuario administrador. Normalmente este usuario debe tener un rango 3 o superior en el emulador. Recuerda que para dar el rango 3 a un usuario, puedes utilizar el siguiente comando: `account set gmlevel blizzcms 3 -1`. De esta forma, daríamos el rango 3 al usuario blizzcms.

```
AC> account set gmlevel blizzcms 3 -1
You change security level of account BLIZZCMS to 3.
```

Accedemos a la página web, y entramos en el administrador. (en/admin)

Website → realms (en/admin/realms)

![create_realm](https://user-images.githubusercontent.com/2810187/144528594-b403eec8-f2c9-4174-b1c8-654d63ecb311.png)

A continuación, trataremos de explicarle lo que debe rellenar en el formulario.

- **#ID:** Es el id del reino, tienes que comprobarlo dentro de la base de datos auth del emulador.
- **Soap Hostname:** Es la IP o el dominio donde se encuentra el emulador. Por ejemplo: `localhost`, `200.58.25.300` o `wow-cms.com`.
- **Soap Port:** Puerto a utilizar por soap para comunicarse entre el emulador y el cms. Por defecto 7878.
- **Soap User:** Usuario que puede ejecutar comandos a través del terminal. Generalmente de rango 3 o 4.
- **Soap Password:** Contraseña de dicho usuario.
- **Character Database Hostname:** Dominio o IP donde se encuentra la base de datos de characters.
- **Character Database Name:** Nombre de los personajes de la base de datos, por ejemplo, por defecto: `acore_characters` en el caso de AzerothCore.
- **Character Database User:** Usuario que tiene permisos sobre la tabla de characters.
- **Character Database Password:** Contraseña del usuario mencionado.
- **Emulator:** Emulador que está utilizando, para este ejemplo AzerothCore.

![create_realm_1](https://user-images.githubusercontent.com/2810187/144529658-86091963-d312-4fea-9f11-e903c74e65df.png)

Una vez completados los datos, tenemos que comprobar la configuración de soap en el emulador.

```
#
#    SOAP.Enable
#        Description: Enable soap service
#        Default:     0 - (Disabled)
#                     1 - (Enabled)

SOAP.Enabled = 1

#
#    SOAP.IP
#        Description: Bind SOAP service to IP/hostname
#        Default:     "127.0.0.1" - (Bind to localhost)

SOAP.IP = "127.0.0.1"

#
#    SOAP.Port
#        Description: TCP port to reach the SOAP service.
#        Default:     7878

SOAP.Port = 7878
```

Con el emulador encendido, comprobamos la configuración de soap entrando en la siguiente URL: (en/admin/checksoap)

Si al entrar en esta URL, encontramos un mensaje de información del servidor, la configuración de soap es correcta.

![checksoap](https://user-images.githubusercontent.com/2810187/144530146-a1f14322-9f8d-4c98-b9ac-2ebb96a8833f.png)

Después de comprobar todo lo anterior, debemos ver el reino online.

![realm_success](https://user-images.githubusercontent.com/2810187/144530244-50e52948-de25-44b6-972f-e6f0f33e8047.png)
