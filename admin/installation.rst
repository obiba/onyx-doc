Installation
============

`Onyx <https://www.obiba.org/pages/products/onyx/>`_ is a web application that runs on a server. Users access it on client workstations via a browser over a local network.
This guide is for whoever will set up Onyx in an assessment centre--typically, a system administrator. 
The guide covers hardware and software requirements and includes procedures for deploying Onyx on a server and setting up the client
workstations.

.. _what-you-need-from-your-organization:

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

