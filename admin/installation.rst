Installation
============

`Onyx <https://www.obiba.org/pages/products/onyx/>`_ is a web application that runs on a server. Users access it on client workstations via a browser over a local network.
This guide is for whoever will set up Onyx in an assessment centre--typically, a system administrator. 
The guide covers hardware and software requirements and includes procedures for deploying Onyx on a server and setting up the client
workstations.

What You Need from Your Organization
------------------------------------

Your organization should provide you with the following:
  * war file ( custom-onyx .war) that contains a version of Onyx customized to your organization's requirements.
  * An appointment list (may be an Excel or XML file)

.. note::

  The war file is actually a zip file. You will need some information from two files in the war file before they are extracted during installation. Your organization may provide you with copies of the files. Or you can extract copies of the two files from the war file:
    * onyx-config.properties.
    * export-destinations.xml.

Requirements
------------

Server Hardware Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

============ ===============
Component    Requirement
============ ===============
CPU	         Recent server-grade or high-end consumer-grade processor
Memory (RAM) Minimum: 2 GB
Disk space	 Minimum: 160 GB Rule of thumb calculation: 10 GB for operating system + ((8 GB/2000 participants) * (expected number of participants))
============ ===============

Server Software Requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. list-table::
  :widths: 10 10 20 40 20
  :header-rows: 1

  * - Software
    - Suggested version
    - Download link
    - Usage
    - Installation/Configuration
  * - Firefox
    - Latest
    - `<http://www.mozilla-europe.org/en/firefox>`_
    - Browser- useful for checking Onyx
    - `<http://java.sun.com/javase/6/webnotes/install/index.htm>`_
  * - JRE
    - JRE 1.6.x
    - | `<http://www.java.com/en/download/manual.jsp>`_
      | or
      | `<http://java.sun.com/javase/downloads/index.jsp>`_
    - Java runtime environment - needed to run Tomcat and Onyx
    - `<http://java.sun.com/javase/6/webnotes/install/index.htm>`_
  * - Tomcat
    - 6.0.x
    - `<http://tomcat.apache.org/download-60.cgi>`_
    - Servlet container - needed to run Onyx
    - `Fine-tuning Tomcat <http://onyxdoc.obiba.org/en/latest/admin/configuration.html#Fine-tuning-tomcat>`_

While Java is required by Mica server application, MongoDB can be installed on another server.

Install
-------

Mica is distributed as a Debian/RPM package and as a zip file. The resulting installation has default configuration that makes Mica ready to be used (as soon as a MongoDB server is available). Once installation is done, see :doc:`configuration` instructions.

Debian Package Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Mica is available as a Debian package from OBiBa Debian repository. To proceed installation, do as follows:

* `Install Debian package <http://www.obiba.org/pages/pkg/>`_. Follow the instructions in the repository main page for installing Mica.
* Manage Mica Service: after package installation, Mica server is running: see how to manage the Service.

RPM Package Installation
~~~~~~~~~~~~~~~~~~~~~~~~

Mica is available as a RPM package from OBiBa RPM repository. To proceed installation, do as follows:

* `Install RPM package <http://www.obiba.org/pages/rpm/>`_. Follow the instructions in the RPM repository main page for installing Mica.
* Manage Mica Service: after package installation, Mica is running: see how to manage the Service.

Zip Distribution Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Mica is also available as a Zip file. To install Mica zip distribution, proceed as follows:

* `Download Mica distribution <https://github.com/obiba/mica2/releases>`_
* Unzip the Mica distribution. Note that the zip file contains a root directory named **mica-x.y.z-dist** (where x, y and z are the major, minor and micro releases, respectively). You can copy it wherever you want. You can also rename it.
* Create an ``MICA_HOME`` environment variable
* Separate Mica home from Mica distribution directories (recommended). This will facilitate subsequent upgrades.

Set-up example for Linux:

.. code-block:: bash

  mkdir mica-home
  cp -r mica-x-dist/conf mica-home
  export MICA_HOME=`pwd`/mica-home
  ./mica-x-dist/bin/mica

Launch Mica. This step will create/update the database schema for Mica and will start Mica: see Regular Command.

For the administrator accounts, the credentials are "administrator" as username and "password" as password. See User Directories Configuration to change it.

Upgrade
-------

The upgrade procedures are handled by the application itself.

Debian Package Upgrade
~~~~~~~~~~~~~~~~~~~~~~

If you installed Mica via the Debian package, you may update it using the command:

.. code-block:: bash

  apt-get install mica

RPM Package Upgrade
~~~~~~~~~~~~~~~~~~~

If you installed Mica via the RPM package, you may update it using the command:

.. code-block:: bash

  yum install mica

Zip Distribution Upgrade
~~~~~~~~~~~~~~~~~~~~~~~~

Follow the Installation of Mica Zip distribution above but make sure you don't overwrite your mica-home directory.

Execution
---------

Server launch
~~~~~~~~~~~~~

**Service**

When Mica is installed through a Debian/RPM package, Mica server can be managed as a service.

Options for the Java Virtual Machine can be modified if Mica service needs more memory. To do this, modify the value of the environment variable ``JAVA_ARGS`` in the file **/etc/default/mica**.

Main actions on Mica service are: ``start``, ``stop``, ``status``, ``restart``. For more information about available actions on Mica service, type:

.. code-block:: bash

  service mica help

The Mica service log files are located in **/var/log/mica** directory.

**Manually**

The Mica server can be launched from the command line. The environment variable ``MICA_HOME`` needs to be setup before launching Mica manually.

==================== ======== ===========
Environment variable Required Description
==================== ======== ===========
``MICA_HOME``        yes      Path to the Mica "home" directory.
``JAVA_OPTS``        no       Options for the Java Virtual Machine. For example: `-Xmx4096m -XX:MaxPermSize=256m`
==================== ======== ===========

To change the defaults update:  ``bin/mica`` or ``bin/mica.bat``

Make sure Command Environment is setup and execute the command line (bin directory is in your execution PATH)):

.. code-block:: bash

  mica

Executing this command upgrades the Mica server and then launches it.

The Mica server log files are located in **MICA_HOME/logs** directory. If the logs directory does not exist, it will be created by Mica.

Usage
~~~~~

To access Mica with a web browser the following urls may be used (port numbers may be different depending on HTTP Server Configuration):

* http://localhost:8082 will provide a connection without encryption,
* https://localhost:8445 will provide a connection secured with ssl.

Troubleshooting
~~~~~~~~~~~~~~~

If you encounter an issue during the installation and you can't resolve it, please report it in our `Mica Issue Tracker <https://github.com/obiba/mica2/issues>`_.

Mica logs can be found in **/var/log/mica**. If the installation fails, always refer to this log when reporting an error.
