Service Genie
=======
### Service Genie - Work Order management MVC 5 web app


Project home page: http://www.opacus.hr/en/ServiceGenie/General

Demo is here: ~~opacus.hr/ser~~


## INFO

Service Genie is a web based application for Work Order management. Some of key features are:


    Mobile friendly - Works on any device with internet connection. It is a web page!
    For best compatibility only universal web technologies are used
    Digital work order signing
    E-mail notifications
    Price lists for partners and ability not to show finances in work orders
    Group invoicing and later view of orders in invoice. Don't allow yourself not to charge for the work done
    Partner portal for monitoring work orders, creating new ones and view of invoices
    Monitoring of hands efficiency based on hours and finished work orders
    Easy translation to any language
    Beauty in simplicity

If you require hosting, please contact me at igor@opacus.hr or for anything else for that mather.


## INSTALATION

### Pre requirements:

- Windows server with .NET framework 4.5.1
- Entity framework compatible database - check here. Tested only with MSSql
- Notepad and browser
- Application files



### Procedure

- Create a Database and user with appropriate rights. Write down host, user and password or any other information for database connection string.

- Prepare E-mail that will be used for sending notifications from the app.

- Open web.config (first one you find, in the root folder) and find following sections:

```
<add name="DataContext"
    connectionString="Data Source=*HOSTNAME*, *PORT*;
    Initial Catalog=*DATABASE_NAME*;
    Persist Security Info=True;
    User ID=*DATABASE_USER*;
    Password=*PASSWORD*" 
    providerName="System.Data.SqlClient"
/>
```

```
<add key="MailFrom" value="FROM@EMAIL.DOM" />

and

<smtp from="servis@applicon-x.com">
    <network defaultCredentials="false" 
        host="*SMTP HOST*" 
        password="*PASSWORD*" 
        port="*PORT*" 
        userName="*USERNAME*" 
        enableSsl="false"
    />
</smtp>
```

```
<add key="Culture" value="hr" /> //change value to en if english applies

and

<globalization uiCulture="hr" culture="hr-HR" /> //also en is an option
```

- Make necessary changes. Save and upload to you web server.

- In your browser open your root web location and add: /SysAdmin/Initialize (it should be something like http://yourweblocation.com/SysAdmin/Initialize)

- This will create necessary tables and create roles and initial system user with username: SysAdmin and password: OpaSer000

- Installation is complete. Open root web location and you will be redirected to login. Go to Admin and fill your business data, from top to bottom.

- To test e-mail settings go to /SysAdmin/MailTest

Good luck!


## Change log

### 1.0.2
- Material in New One Step Order now is not mandatory

### 1.0.1
- Add material in New One Step Order
- Add group material list when group facturing
- Add group material list when viewing invoces
- Minour bug fixes
