# Installation

Before attempting installation, review the [requirements](requirements.md).

When downloading / cloning the repository. In the case of Windows, you must place the files inside `htdocs`, and in the case of Linux, normally the path is `/var/www/`, usually in a folder called `html`. Once the files are placed in the corresponding folders, the CMS will open an installation form for the first time.

![migration](https://user-images.githubusercontent.com/2810187/144492952-e28090e2-ee35-4fc8-bf82-734f2c06c12a.png)

As you can see in the image, the CMS has some built-in validations. This means that if these validations are not met, the button to install it will not appear no matter how many times you fill in the form fields. Below, we provide information on what to complete in the forms.

**Website Database Hostname:** This is the domain name or ip of the database to be used by the cms.

In contraction, we give you some examples:
- `localhost` → If you are working in a test environment.
- `200.50.29.300` → a public ip.
- `wow-cms.com` → a domain where associated to the machine or webhosting where you are installing.

**Note:** By default, the port is 3306 in MySQL. But if you change the port, you can use the following format: `localhost:3310` for example.

**Website Database Name:** This is the name of the database to be used by the cms.

Remember that the CMS creates the tables by means of migrations, but it does not create the database, it must be created manually.

**Website Database Username:** User with access to the cms database, to make changes. SELECT, INSERT INTO, UPDATE, DELETE

**Website Database Password:** Password, of the above mentioned user.

In the second form, the data from the emulator's auth database are requested. I do not repeat again what the fields mean, because basically it is the same as above, only, that it is possible to change the user, the port or even the hostname. It all depends on the project and the configuration that each one has, the security, the servers...
