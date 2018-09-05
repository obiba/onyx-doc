|proc| Updating the appointment list
====================================
Onyx does not schedule appointments for participants. Instead it imports an appointment list from a file. The appointment list is updated automatically.
If necessary, Onyx users of type participant manager can also update the appointment list manually as explained in this section.
Your study customized how often the appointment list is updated. Contact your system administrator if you want to know how often the list is updated or have any other questions about the list.

Prerequisite
------------
* You are an Onyx user of type participant manager.
* If you want to select an appointment list file, you must know the name and location of such files. Appointment files usually have an XML or XLSL extension.

Each study customizes its appointment list. Your study defined the file type, name, and location, as well as the information stored for each participant.
Contact your system administrator to know more about appointment list files for your study.

Procedure
---------
#. If the **Participants** page is not displayed, select the **Participants** tab to display it. The **Update appointment list button** is displayed in the upper right corner. See :ref:`this figure <update-appointment-list-button>`.

   .. _update-appointment-list-button:
   .. figure:: /images/UpdateAppointmentListButton.png
      :align: center
      :alt: Participant managers see the Update appointment list button in the Participants page

      Participant managers see the Update appointment list button in the Participants page
#. Select the Update appointment list button. The Update Appointments dialog is displayed. See :ref:`this figure <the-update-appointments-dialog>`.

   .. _the-update-appointments-dialog:
   .. figure:: /images/theUpdateAppointmentsDialog.png
      :align: center
      :alt: The Update Appointments dialog

      The Update Appointments dialog
#. If you want to use the appointment file from the default location, select the first option button (**Update appointments with the latest appointment file available**).
#. If you want to search for an appointment list file to use for the update, select the second option button (**Update appointments with an alternative appointment file**). If you need help locating a file, contact your system administrator.
#. If you decide not to update the list, select the **Cancel** button. The **Update Appointments** dialog is closed and the Participants page is visible again.
#. If you want to proceed with updating the list, select the Update Appointments button. During the update, a progress bar is displayed in the dialog. When the update is complete, the dialog displays a report about the update. See this figure.

   .. _the-update-appointments-dialog-displays-a-report:
   .. figure:: /images/theUpdateAppointmentsDialogDisplaysAReport.png
      :align: center
      :alt: The Update Appointments dialog displays a report when the update is complete

      The Update Appointments dialog displays a report when the update is complete
#. | Select the **Details** button if you want to read more about how the update went. A **Log** dialog is displayed. If any errors were reported in the log, contact your system administrator.
   | When you have finished viewing the log, select the **Close** button of the dialog.
#. | When you have finished viewing the report in the **Update Appointments** dialog, select its **Close** button. 
   | The dialog is closed and the **Participants** page is visible again. The list of participants is now up-to-date.