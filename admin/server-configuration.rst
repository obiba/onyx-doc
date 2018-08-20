Server Configuration
====================

Fine-tuning Tomcat
------------------

For general tips related to Tomcat, see `<http://tomcat.apache.org>`_.

.. note::

  The following tips assume that you are using Sun's Java Virtual Machine

General Comments about Tomcat Memory Settings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

On most default Tomcat installations, the memory allocated to the service is insufficient. You must increase the memory allocated to Tomcat by
tweaking two memory settings.

* *Xmx*
* *XX:MaxPermSize*

In the OS-specific procedures below (see Allocating Memory on Ubuntu and Allocating Memory on Windows ), we assume that your server has
2GB of RAM. We set *-Xmx* to 1024 and *-XX:MaxPermSize* to 256m.

* If your server has more than 2GB of RAM, you can increase the *-Xmx* setting. It is not necessary to increase the *-XX:MaxPermSize* setting.
* If your server has less than 2GB of RAM, you can decrease the *-Xmx* and the *-XX:MaxPermSize* settings. Try to keep the same ratio (4:1). **Do not** allocate less than 128m to *-XX:MaxPermSize*.

Using Tomcat on Ubuntu
^^^^^^^^^^^^^^^^^^^^^^

Two issues need to be addressed when running Tomcat on Ubuntu: insufficient memory and the security manager.

To allocate memory on Ubuntu
""""""""""""""""""""""""""""

To allocate memory to Tomcat, you need to create an environment variable. If Tomcat was installed using apt , you must edit the */etc/default/tomcat6* file as shown below:

.. code-block:: bash
  
  #/etc/default/tomcat6

  JAVA_OPTS="-Xmx1024M -XX:MaxPermSize=256M

To disable the security manager on Ubuntu
"""""""""""""""""""""""""""""""""""""""""
Comment out the *#TOMCAT6_SECURITY=yes* and add the *TOMCAT6_SECURITY=no* line as shown below.

.. code-block:: bash

  #/etc/default/tomcat6

  # Use the Java security manager? (yes/no, default: yes)
  # WARNING: Do not disable the security manager unless you understand
  # the consequences!
  #TOMCAT6_SECURITY=yes
  TOMCAT6_SECURITY=no

Using Tomcat as a Windows Service
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Two issues need to be addressed when running Tomcat as a service on Windows: insufficient memory and making the printer available to
Tomcat.

To allocate memory on Windows
"""""""""""""""""""""""""""""

#. Open the Apache Tomcat Properties dialog in either of these ways:
   
   * If you have a Tomcat icon on your taskbar, right-click it and select Configure.
   * From the Start menu, select All Programs > Apache Tomcat 6.0 > Configure Tomcat.

#. Select the Java tab. See screenshot below.
#. Add this line in the Java Options field: -XX:MaxPermSize=256M .
#. In the Maximum memory pool field , enter the value 1024

.. note::

  The Maximum memory pool setting is equivalent to passing the -Xmx argument to Java.

.. image:: /images/allocateMemoryOnWindows.png

To enable printing from Tomcat
""""""""""""""""""""""""""""""

When running Tomcat as a Windows Service, make sure that the user running the Tomcat service can use the printer. This is not the case by
default. Permissions must be given to the tomcat user in order for Onyx to see the printer you wish to use.

Configuring MySQL
-----------------

To check the database connection settings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The default Onyx connection to the MySQL server uses the settings shown in the table below.
They are defined in the *onyx-config.properties* file, which is Onyx's main configuration file.

===================== ===========
Settings              value
===================== ===========
hostname\:port        localhost\:3306
username              Onyx
password              onyx-demo
===================== ===========

Your organization may have already changed the defaults. You can check the values in the *onyx-config.properties* file ( :ref:`What You Need from Your organization <what-you-need-from-your-organization>`). If the settings are different from the defaults shown in the table , note them so you can use them when Creating a
Database for Onyx in MySQL.

.. code-block:: bash

    #WEB-INF/config/onyx-config.properties
    # Database configuration (if applicable)
    [...]
    # MySQL
    org.obiba.onyx.datasource.driver=com.mysql.jdbc.Driver
    org.obiba.onyx.datasource.url=jdbc:mysql://localhost:3306/onyx
    org.obiba.onyx.datasource.username=onyx
    org.obiba.onyx.datasource.password=onyx-demo
    org.obiba.onyx.datasource.dialect=org.hibernate.dialect.MySQL5InnoDBDialect
    org.obiba.onyx.datasource.validationQuery=SELECT 1;
    org.obiba.onyx.datasource.testOnBorrow=true

To create a database for Onyx in MySQL
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You must create a database for Onyx in MySQL, and you must also set up a user that has all privileges on that database. When Onyx starts for
the first time, it will automatically create its schema in this database.

In a MySQL client:

#. Execute the command: *create database onyx* (or whatever name that defined at the end of this line in *onyx-config.properties:org.obiba.onyx.datasource.url=jdbc:mysql://localhost:3306/onyx*)
#. Ensure that the MySQL users ( onyx in this case) granted all privileges on that database instance (CREATE TABLE, ALTER, and so on)

Alternatively, in the MySQL Administrator application:

#. Select **Catalogs**.
#. Right-click in the field that lists the existing schemata, and select **Create New Schema**.

#. When prompted for a name for the new schema, enter onyx or whatever name was defined at the end of this line in *onyx-config.properties: org.obiba.onyx.datasource.url=jdbc:mysql://localhost:3306/onyx*).
#. Add a new user (with the name onyx or whatever value is defined in this line of *onyx-config.properties: org.obiba.onyx.datasource.username=onyx*).
#. Assign all priveleges on the new database to the new user.

Setting Up an SSL Connection
----------------------------

To set up Onyx to run over a secured connection on the local network, you must do two tasks on the Onyx server: :ref:`create a keystore <to-create-a-keystore-for-the-ssl-connection>` and :ref:`configure Tomcat to use an SSL connection <to-configure-tomcat-to-use-an-ssl-connection>`.

.. note::
  The procedures in this section use the following shortcuts to refer to certain directories:
  JAVA_HOME = the directory where java is installed
  CATALINA_BASE = the directory where Tomcat is installed

.. _to-create-a-keystore-for-the-ssl-connection:

To create a keystore for the SSL connection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. From the JAVA_HOME directory, execute this command:

.. code-block:: bash

  ./bin/keytool -genkey -alias tomcat -keyalg RSA -keystore CATALINA_BASE/keystore/onyx.jks.

2. When prompted, enter the requested information for the certificate and a new password.
#. Export the certificate to a file. You will import this file on each of the client workstations. See Setting Up the SSL Connection to Onyx.

.. _to-configure-tomcat-to-use-an-ssl-connection:

To configure Tomcat to use an SSL connection
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Edit the file *CATALINA_BASE\...\conf\server.xml* as follows:

1. Comment out this section:

.. code-block:: bash
  
    <!-- Define a non-SSL HTTP/1.1 Connector on port 8080 -->
      <!-- <Connector 
        port="8080" maxHttpHeaderSize="8192"
        maxThreads="150" minSpareThreads="25" maxSpareThreads="75"
        enableLookups="false" redirectPort="8443" acceptCount="100"
        connectionTimeout="20000" disableUploadTimeout="true" /> -->

2. Remove comments from this section:

.. code-block:: bash

   <!-- Define a SSL HTTP/1.1 Connector on port 8443 -->
      <Connector 
        port="8443" maxHttpHeaderSize="8192"
        maxThreads="150" minSpareThreads="25" maxSpareThreads="75"
        enableLookups="false" disableUploadTimeout="true"
        acceptCount="100" scheme="https" secure="true"
        clientAuth="false" sslProtocol="TLS"/>

3. In the *< Connector>* element, add the following attributes:

.. code-block:: bash

   keystoreFile="keystore\onyx.jks" keystorePass="password"

where *"keystore\onyx.jks"* and *"password"* are the values you entered when Creating a :ref:`keystore for the SSL connection <to-create-a-keystore-for-the-ssl-connection>`.

.. _generating-a-key-and-certificate-for-data-export:

Generating a Key and Certificate for Data Export
------------------------------------------------
Onyx can export data to one or more export destinations (see Configuring Data Export and Purge ).
If your organization has decided to encrypt participant data upon export to a articular destination, you must generate a key and certificate for that destination.
You can check whether or not data is supposed to be encrypted on export, look in the file export-destinations.xml which is in your custom *-onyx.war* file (:ref:`What You Need from Your organization <what-you-need-from-your-organization>`).
If any of the destinations include an *<encrypt>* element, the data will be encrypted on export.
You will need the key and certificate when you carry out the procedure for :ref:`Deploying Onyx <deploying-onyx>`. You can use a utility (`like openSSL <https://www.openssl.org/>`_) to generate keys and certificates. For a Windows program that uses openSSL to generate keys and certificates, see `Shining Light Productions <http://slproweb.com/products/Win32OpenSSL.html>`_.

Fine-tuning the Onyx Configuration
----------------------------------
The global configuration settings for Onyx are contained in the file *onyx-config.properties* . See :ref:`What You Need from Your organization <what-you-need-from-your-organization>`.

.. Todo link to sections onyx-customization-configuration

As a minimum, you should check the configuration settings listed in this section. If you think other settings need to be fine-tuned, see :ref:`Customizing the Global Configuration <onyx-customization-configuration>` in the :ref:`Onyx Customization & Configuration Guide <onyx-customization-configuration>`.

To check the application mode
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Onyx should be configured to run in deployment mode. This is very important since it improve the overall performance of the application. Check
that the following property *onyx-config.properties* is set to deployment in :

.. code-block:: bash

   # WEB-INF/config/onyx-config.properties
   # Onyx Web application mode: deployment or development
      org.obiba.onyx.webapp.configurationType=deployment

To set the printer
^^^^^^^^^^^^^^^^^^
On startup, Onyx decides which printer to use. Onyx will try to find a printer with a particular name. If that printer does not exist, or does not
support PostScript printing, then Onyx will fall back to using the system's default printer. If that printer does not support PostScript printing, Onyx
will not be able to print reports.
You can change the printer that Onyx should look for at startup by editing this line in *onyx-config.properties*.

.. code-block:: bash

   # WEB-INF/config/onyx-config.properties
   # Name of printer for PDF printing.
      org.obiba.onyx.pdfPrinterName=ONYX PDF Printer

To set up the appointment list
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. Check the input and output directories for the appointment list file. The output directory is optional. The default paths are shown below. They may have been changed in your version of Onyx.

.. code-block:: bash

  # WEB-INF/config/onyx-config.properties
  # Appointment management
  # Directory that contains the appointment list files to process dropped by external process
    org.obiba.onyx.appointments.inputDirectory=WEB-INF/appointments/in
  # Optional directory that contains the successfully processed files
    org.obiba.onyx.appointments.outputDirectory=WEB-INF/appointments/out
  # Schedule for automatic appointment list updates (4am every day)
    org.obiba.onyx.appointments.schedule=0 0 4 * * ?

2. Create the input and output directories on the Onyx server.
#. If your organization gave you an appointment list file, put it in the input directory.

To set up the data export directory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Check the export directory setting in onyx-config.properties . The default export directory is target in Onyx's current working directory (usually the Tomcat home directory). It may been changed in your version of Onyx.

.. code-block:: bash

  # WEB-INF/config/onyx-config.properties
  # System path where to export Onyx Data
    org.obiba.onyx.export.path=target

2. Create the export directory on the Onyx server.

To set up the keystore for data export
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. Check where the keystore file should be written to. The default path and filename are shown below. They may have been changed in your version of Onyx.

.. code-block:: bash

  # WEB-INF/config/onyx-config.properties
  # Keystore
    org.obiba.onyx.keystore.file=file:${java.io.tmpdir}/onyxKeyStore.jks
    org.obiba.onyx.keystore.password=youshouldchangethispassword

2. Change the password for the keystore and save onyx-config.properties .
#. Create the keystore directory on the Onyx server.

.. _deploying-onyx:

Deploying Onyx
--------------
To deploy Onyx, you need a war file ( custom-onyx .war) containing a customized version of Onyx. If you do not already have it, see here

.. note::
   You must enter the custom-onyx part of the war filename when you access Onyx in a browser in the procedure below.

#. Copy the war file to the webapps directory in the Tomcat installation directory *$TOMCAT_HOME/webapps*.
#. If Tomcat is already running, it should deploy Onyx automatically. To check if Tomcat is running on Windows:

   #. Select Control Panel > Administrative Tools > Services > Apache Tomcat
   #. Click Start if Tomcat is not running. Onyx will be deployed when Tomcat starts.

#. Check that you can access Onyx by opening a browser and pointing it to: http://localhost:8080/custom-onyx . If you cannot access Onyx, try restarting Tomcat. If you still have trouble, see :ref:`Troubleshooting <troubleshooting>`.
#. When you access Onyx for the first time, you must complete the Onyx setup page (see the screenshot below) as follows:

   #. Enter details about the Onyx instance (study name, site name and site id).
   #. | If you configured Onyx to Generate Participant Identifiers Automatically, you will have to specify the Identifier Prefix and the First Indentifier (starting point for generating the identifiers).
      | See :ref:`Configuring Participant ID Generator <onyx-customization-configuration>` for more details about generating identifiers.
   #. Set up an account for the Onyx Administrator.
   #. Set the Session Timeout (minutes) to at least 45 or 60 (which should be enough for any physical measurements that must be performed).
   #. | If your organization will encrypt participant data upon export, copy and paste the certificate you generated for this purpose into the field provided.
      | If you did not generate a certificate yet, see :ref:`Generating a Key and Certificate for Data Export <generating-a-key-and-certificate-for-data-export>`.

.. image:: /images/keyGeneration.png

.. note::
    Take note of these values for future reference:

    * Administrator's user name and password. You will always need them to log in to Onyx.
    * | Collection Site Id. This value will be used in the appointment list file. If your organization has or will have several sites (each with its own Onyx server), each site should have a unique Id.
      | The value can be alphanumeric, but should not contain spaces.

Checking the Deployment
^^^^^^^^^^^^^^^^^^^^^^^
Here are a few items to check after you have deployed Onyx:

.. toDo ref to section Setting up the appointment list

* If your data will be encrypted upon export (see :ref:`Generating a Key and Certificate for Data Export <generating-a-key-and-certificate-for-data-export>`), check that the file *onyxKeyStore.jks* was created at the location defined by the property *org.obiba.onyx.keystore.file* in *onyx-config.properties*.
* If you put an appointment list file in the input directory (see :ref:`Setting up the appointment list <onyx-customization-configuration>`), check that you can update the appointment list from the Participants tab of the Onyx user interface.

.. _troubleshooting:

Troubleshooting
^^^^^^^^^^^^^^^
The first place to look is Tomcat's console output which is written in the *log* directory. 
Under windows, the file is called *stdout_XXX.log* on Debian/Ubuntu, this file is called *catalina.out*.

Miscellaneous
-------------

Consent Form Submission Problems
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You may encounter an error when attempting to submit a consent form, especially a large multi-page consent form written in a double-byte character set.
This error occurs because the consent form is too large to be stored in the database. To get around this, you must modify the MySql database settings to allow storage of larger amounts of data.
The configuration file that you must edit is *my.ini* on Windows and *my.cnf* on Linux.
This is the line you need to change:

.. code-block:: bash

   max_allowed_packet=3M

To start, try a value of 3M (for 3 megabytes). If it still doesn't work, increase the value. You will need to restart the MySql database server after making the change.

