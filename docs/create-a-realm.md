# Create a realm

The following example is performed on the AzerothCore emulator.

Check the documentation of the emulator you are using to see the differences.

The first thing we have to do is to log in with an administrator user. Normally this user must have rank 3 or higher in the emulator. Remember that to give rank 3 to a user, you can use the following command: `account set gmlevel blizzcms 3 -1`. That way, we would give rank 3 to the blizzcms user.

```
AC> account set gmlevel blizzcms 3 -1
You change security level of account BLIZZCMS to 3.
```

We access the website, and enter the administrator. (en/admin)

Website → realms (en/admin/realms)

![create_realm](https://user-images.githubusercontent.com/2810187/144528594-b403eec8-f2c9-4174-b1c8-654d63ecb311.png)

In the following, we will try to explain what you should fill in the form.

- **#ID:** It is the id of the realm, you have to check inside the auth database of the emulator.
- **Soap Hostname:** This is the IP or domain where the emulator is located. For example: `localhost`, `200.58.25.300` or `wow-cms.com`.
- **Soap Port:** Port to be used by soap to communicate between the emulator and the cms. By default 7878.
- **Soap User:** User, who can execute commands through the terminal. Generally rank 3 or 4.
- **Soap Password:** Password of the above mentioned user.
- **Character Database Hostname:** Domain or IP where the characters database is located.
- **Character Database Name:** Name of the database characters, for example, by default: `acore_characters` in the case of AzerothCore.
- **Character Database User:** User who has permissions on the characters table.
- **Character Database Password:** Password of the above-mentioned user.
- **Emulator:** Emulator you are using, for this example AzerothCore.

![create_realm_1](https://user-images.githubusercontent.com/2810187/144529658-86091963-d312-4fea-9f11-e903c74e65df.png)

Once we complete the data, we have to check the soap configuration of the emulator.

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

With the emulator turned on, we check the soap configuration by entering the following URL: (en/admin/checksoap)

If when entering this URL, we find a server info message, the soap configuration is OK.

![checksoap](https://user-images.githubusercontent.com/2810187/144530146-a1f14322-9f8d-4c98-b9ac-2ebb96a8833f.png)

After checking all of the above, we should look at the online realm.

![realm_success](https://user-images.githubusercontent.com/2810187/144530244-50e52948-de25-44b6-972f-e6f0f33e8047.png)
