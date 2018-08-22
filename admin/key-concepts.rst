Key concepts related to the way Onyx works
==========================================

|key| User Roles
----------------
These are the roles that are possible for Onyx users:
* Data collector - has basic permissions
* Participant manager - has data collector permissions plus a few more
* System administrator - has permissions of participant manager plus a few more

For details about what each user role can do, see :doc:`Who Uses Onyx </user-guide/introduction/who-uses-onyx>`.

|key| User Status
-----------------
Onyx users have one of these statuses:
* **Active**: The user can log in. By default, when a user is created, their status is active.
* **Inactive**: The user will not be able to log in. For example, you may want to deactivate a user who is away on leave.

The word that appears in the **Status** column in the **User** administration page is the user's current status.
Only system administrators can change the status of an Onyx user. See :ref:`Activating and Deactivating Onyx Users <>`.

.. _data-export:

|key| Data Export
-----------------
Exporting data from Onyx means reading data from the Onyx database and writing it to one or more export destinations.
Here are some points worth noting about the Onyx export function:

* Exporting does not delete any data from the Onyx database. Deleting data from the database is done by the purge function. See :ref:`Data Purge <data-purge>` (page 139).
* An export destination is a compressed zip file. The name given to an export destination may indicate the location into which the data will be imported—for example, a data repository like Opal.
* Participant data and experimental conditions data can be exported. See :ref:`Participant Data <participant-data>` and :ref:`Experimental Condition Data <experimental-conditions-data>`.
* Configuration of data export is done entirely in configuration files, not through the Onyx user interface. Some things that can be configured:
    + Which data is selected for export
    + Directory to which export files are written
    + How many export destinations are defined

For detailed information about how the export function is configured, see the :ref:`OBiBa Wiki Onyx+1.6.0+Upgrade <>`.
Only system administrators can execute a data export from the Onyx user interface. See :ref:`Exporting Data <>`.

.. _data-purge:

|key| Data Purge
----------------
In Onyx, purging data means deleting data from the Onyx database. Only :ref:`participant data <participant-data>` can be purged—not :ref:`experimental conditions data <experimental-conditions-data>`.
Configuration of data purging is done entirely in configuration files, not through the Onyx user interface.
For detailed information about how the purge function is configured, see the :ref:`OBiBa Wiki Onyx+1.6.0+Upgrade <>`.
Only system administrators can execute a purge from the Onyx user interface. See :ref:`Purging Data <>`.

.. _participant-data:

|key| Participant Data
----------------------
Participant data includes personal information (such as the participant's name and address),
as well the data from all stages of the interview (consent, questionnaires, physical measurements, and information about the biospecimens collected).
Participant data can be exported (see :ref:`Exporting Data <exporting-data>`) and purged (see :ref:`Purging Data <purging-data>`).

.. _experimental-conditions-data:

|key| Experimental Conditions Data
----------------------------------
Each study can define experimental conditions that it would like to track on a regular basis. This information is stored in one or more experimental condition logs.
The Workstation page of the Onyx user interface allows users to make entries in these logs.
As a system administrator, you will export this data, so you should be familiar with the experimental condition logs that were defined for the study.
The user interface for experimental condition logs is in the lower half of the Workstation page. Instrument data is a special case of experimental conditions data.
See :ref:`Instrument Data <instrument-data>`.
Experimental conditions data can be exported (see :ref:`Data Export <data-export>`), but it cannot be purged (see :ref:`Data Purge <data-purge>`).
This data is not purged because it is needed for the log history, and because no privacy issues are involved with this kind of data.

.. _instrument-data:

|key| Instrument Data
---------------------
Instruments are part of the experimental setup, so data about instruments is a special case of :ref:`experimental conditions data <experimental-conditions-data>`.
As a system administrator, you will export this instrument data, so you should be familiar with the instrument calibrations that are done for the study.
The user interface for instrument calibration is in the the top half of the Workstation page.
Like other experimental condition data, instrument data can be exported but not purged.