# Installation

Before attempting installation, review the [requirements](requirements.md).

When [downloading](https://github.com/WoW-CMS/BlizzCMS/archive/refs/heads/master.zip) / [cloning the repository](https://github.com/WoW-CMS/BlizzCMS). In the case of Windows, you must place the files inside `htdocs`, and in the case of Linux, normally the path is `/var/www/`, usually in a folder called `html`. Once the files are placed in the corresponding folders, the CMS will open an installation form for the first time.

![migration](https://user-images.githubusercontent.com/2810187/144492952-e28090e2-ee35-4fc8-bf82-734f2c06c12a.png)

As you can see in the image, the CMS has some built-in validations. This means that if these validations are not met, the button to install it will not appear no matter how many times you fill in the form fields. Below, we provide information on what to complete in the forms.

- **Website Database Hostname:** This is the domain name or ip of the database to be used by the cms.

In contraction, we give you some examples:
- `localhost` → If you are working in a test environment.
- `200.50.29.300` → a public ip.
- `wow-cms.com` → a domain where associated to the machine or webhosting where you are installing.

**Note:** By default, the port is 3306 in MySQL. But if you change the port, you can use the following format: `localhost:3310` for example.

- **Website Database Name:** This is the name of the database to be used by the cms.

(Remember that the CMS creates the tables by means of migrations, but it does not create the database, it must be created manually).

- **Website Database Username:** User with access to the cms database, to make changes. SELECT, INSERT INTO, UPDATE, DELETE
- **Website Database Password:** Password, of the above mentioned user.

In the second form, the data from the emulator's auth database are requested. I do not repeat again what the fields mean, because basically it is the same as above, only, that it is possible to change the user, the port or even the hostname. It all depends on the project and the configuration that each one has, the security, the servers...

For example, if you are using MySQL 8.x, you can create the databases, user and password with the following script.

Remember to change the key, user and password. Do not use default values in your production projects.

```sql
DROP USER IF EXISTS 'acore'@'localhost';

CREATE USER 'acore'@'localhost' IDENTIFIED BY 'acore' WITH MAX_QUERIES_PER_HOUR 0 MAX_CONNECTIONS_PER_HOUR 0 MAX_UPDATES_PER_HOUR 0;

CREATE DATABASE `acore_auth` DEFAULT CHARACTER SET UTF8MB4 COLLATE utf8mb4_general_ci;

CREATE DATABASE `blizzcms` DEFAULT CHARACTER SET UTF8MB4 COLLATE utf8mb4_general_ci;

GRANT ALL PRIVILEGES ON `acore_auth` . * TO 'acore'@'localhost' WITH GRANT OPTION;

GRANT ALL PRIVILEGES ON `blizzcms` . * TO 'acore'@'localhost' WITH GRANT OPTION;
```

- In the first line, we delete the user, if it does not exist.
- In the second one, we create it, establishing name, connection mode and password.
- In the third and fourth, we create the auth database and the cms table.
- And in the fifth and sixth, we give permissions to the user on those databases.

**Note:** You do not have to create 2 auth databases, the auth database, you usually create it, while compiling the emulator, but for practical purposes, here we explain how you can do it. [Thanks to AzerothCore, for the sql script](https://github.com/azerothcore/azerothcore-wotlk/blob/master/data/sql/create/create_mysql.sql).

> 6 queries executed, 6 success, 0 errors, 1 warning

![migration_successful](https://user-images.githubusercontent.com/2810187/144518673-3a5e6d1c-e737-4ccd-bd1d-04c3d172e74a.png)

If all the data is correct, you will get to the next screen.

![migration_finish](https://user-images.githubusercontent.com/2810187/144518947-6ef0cb80-df06-4c30-82a5-71590f25c768.png)

- **Server Name:** This is the name of the server. For example: `BlizzCMS test`.
- **Realmlist:** The hostname or IP to access the server. For example: `wow-cms.com` or `200.52.28.177`.
- **Expansion:** Emulator expansion. For example: `Wrath of the Lich King`.
- **Discord Invitation ID:** The ID of the discord invitation URL.

For example, if the invitation is: https://discord.com/invite/QXhHZpbeu5. Just enter `QXhHZpbeu5`.

- **Emulator:** The type of encryption the emulator uses. `SRP6`, `Hex`...
- **Bnet Enabled?:** Does the emulator use bnet?

> In case you make a mistake, do not worry. Changes can be made later in the configuration file.

![finish_migration](https://user-images.githubusercontent.com/2810187/144524017-eaf2f466-7c9e-4581-be78-cf6cd49473e3.png)

If all goes well, you should see an image similar to this one.

![home](https://user-images.githubusercontent.com/2810187/144524538-ac6282fc-1d39-40f0-937d-cdaf621537a6.png)

The BlizzCMS community and the WOW-CMS staff would like to kindly ask you not to remove the credits from the footer. This is the only way to make the CMS known to people who don't know about it yet, and maybe find developers interested in participating in the project.

Thank you for downloading and using BlizzCMS.
