Workstation Configuration
=========================

Setting Up Touchscreens (if applicable)
---------------------------------------

If touchscreen monitors are being used with any of the client workstations, the monitors should be put in "Click on contact" mode. You should
avoid any kind of "mouse emulation" mode, since it will complicate use of the touchscreen.

Registering Instruments
-----------------------

An instrument must be registered on the workstation(s) with which it will be used. An instrument can be reserved for one workstation or it can be shared by several **workstations**.
This is done on the Workstation page of the Onyx user interface, as explained in the :doc:`Onyx User Guide </user-guide/index>`.

Installing Proprietary Software for Instruments
-----------------------------------------------

If your organization has chosen to use any of these `electronic instruments <https://www.obiba.org/pages/products/onyx#supportedInstruments>`_ (except those manufactured by Tanita), you must install the
instrument's proprietary software on the workstation with which the instrument will be used.

General Troubleshooting for Instruments
---------------------------------------

*BadFieldException* when Starting an Instrument
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This exception is caused by a bug in the version of Java installed on the workstation. To fix this issue, ensure that the JRE installed on the Onyx
server is at least *1.6.0_02*.

Unable to Save Instrument Data Due to Timeout of Onyx Session
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

After an instrument's software is launched, the user's Onyx session may timeout because the user is no longer interacting with Onyx.
If the Onyx timeout is set too low (for example, 5 minutes) and the physical measurement takes longer than the timeout, the Onyx session will timeout and the measurement data will not be saved.
The user will need to log in to Onyx again after the test is over, and repeat the measurement or enter the measurements in Onyx manually, if Onyx is configured to accept manual measurments.
The timeout is set when you access Onyx for the first time (see :doc:`Installing Onyx on the Server <installation>`). The timeout setting is stored in the Onyx database.
It cannot be changed in a configuration file or in the Onyx user interface.
When accessing Onyx for the first time, be sure to set the Session Timeout to at least 45 or 60 (minutes).
This should be enough to complete physical measurements. See :doc:`Setting Up the Server <server-configuration>`.

Tanita Scales and Bioimpedance Instruments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If your organization is using instruments manufactured by Tanita, read this section when you are setting up the instrument(s) for use with an Onyx workstation.

Cable for the Tanita scale
""""""""""""""""""""""""""

If the cable provided has a serial 9 pin connector, the Port Settings for Flow control must be set to Hardware.

Configuring the Port Settings on Windows
""""""""""""""""""""""""""""""""""""""""

#. Open the **Control Panel** in classic view.
#. Select **System > Hardware (tab) > Device Manager > Expand Ports**.
#. Double-click the port that needs to be changed (usually COM1).
#. Select the **Port Settings** tab.
#. Set **Flow Control** to **Hardware**.

Achilles Express
^^^^^^^^^^^^^^^^

Achilles Express software (version 5.11 and earlier versions) produces erroneous data. Specifically, the SOS and BUA parameters are not calculated properly. However, the Stiffness Index is correct.
Version 5.12 fixes this issue.

TOPCON TRC-nw8
^^^^^^^^^^^^^^
If SQL Server uses windows authentication to connect to the database, "ntmlauth.dll" library must be added in lib java folder.
This library is provided by jtds driver located at `<http://jtds.sourceforge.net/>`_ .
Once zip archive downloaded (jtds-1.2.x-dist.zip), DLL library is in {x86, x64, IA64}/SSO/ntmlauth.dll (Platform Dependant).




