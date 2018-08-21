Procedures
==========

.. _displaying-a-list-of-all-participants:

|proc| Displaying a List of All Participants
--------------------------------------------
You can view a list of all the participants in the Onyx database: past and future participants, as well as those whose interviews are scheduled for the current date---today.
The list does not include participants that have been purged from the Onyx database. See :ref:`Data Purge <data-purge>`.

Procedure
^^^^^^^^^
#. If the **Participants** page is not displayed, click the **Participants**  tab.
#. Click the **All Participants** button. The **Participants**  page is updated to show **all participants** in the Onyx database.

.. _the-participants-page:
.. figure:: /images/theParticipantsPage.png
   :align: center
   :alt: The Participants page

   The Participants page

.. _displaying-a-list-of-today-s-interviews:

|proc| Displaying a List of Today's Interviews
----------------------------------------------
You can view a list of all the participants whose interviews are scheduled for the current date---today.

Procedure
^^^^^^^^^
#. If the **Participants** page is not displayed, click the **Participants** tab.
#. Click the **Appointments of the day** button. The **Participants** list is updated to show all participants who have interviews today.

.. _the-participants-page-appointments:
.. figure:: /images/theParticipantsPageAppointments.png
   :align: center
   :alt: The Participants page

   The Participants page

.. _displaying-a-list-of-participants-currently-being-interviewed:

|proc| Displaying a List of Participants Currently Being Interviewed
--------------------------------------------------------------------
You can view a list of all the participants whose interviews have the status :ref:`In Progress <interview-status>`.
This status does not necessarily mean that the participant is seated with a staff member and that data is being collected from the participant.
**In Progress** simply means that the particicipant's interview was started and that it is not finished yet.

Procedure
^^^^^^^^^
#. If the **Participants** page is not displayed, click the **Participants** tab.# Click the **Interviews in progress** button.
#. cThe **Participants** list is updated to show all participants whose interviews have the status **In Progress**.

.. _the-participants-page-in-progress:
.. figure:: /images/theParticipantsPageInProgress.png
   :align: center
   :alt: The Participants page

   The Participants page

If you see a |lock| icon at the end of the row for the participant, this indicates that an Onyx user has a lock on the interview.
See :ref:`Determining who has a lock on a participant <determining-who-has-a-lock-on-an-interview>`.

.. _finding-a-participant:

|proc| Finding a Participant
----------------------------
Onyx gives you several ways to find participants. this table summarizes the techniques you can use to search for participants.

.. list-table::
      :widths: 50 50
      :header-rows: 1

      * - **Technique**
        - **Result**
      * - Scan participant's barcode (or enter participant ID manually) in the **Home** page and click **Go to interview**
        - The participant's **Interview** page opens.
      * - Scan participant barcode (or enter participant ID in the search field) in the **Participants** page and click |search|
        - The **Participants** list is updated and will include only one participant---the one with the scanned barcode
      * - Enter participant ID or enrollment ID in search field on **Participants** page and click |search|
        - The **Participants** list will be updated and will include only one participant---the one with the ID that you entered.
      * - Enter all or part of participant's name in search field in the **Participants** page and click |search|
        - The **Participants** list is updated---it contains one or more participants, depending on what you entered and the names of the participants in the database.
      * - | Sort the **Participants** list by clicking on the heading of a column. You can sort on:

          * Enrollment ID
          * Participant ID
          * Last Name
          * First Name
          * Appointment
        - | The Participants list will be reordered according to the column you selected. Examples:

          * If you click on **First Name**, the list will be displayed in alphabetical order by participants' first names.
          * If you click on **Enrollment ID**, the list will be displayed in numerical order of enrollment IDs.

If you cannot find a particular person who has arrived for an interview, a couple of explanations are possible:

* The appointment list may not be up-to-date.
* The person does not actually have an interview.

In either case, contact your participant manager who can update the appointment list or enroll a volunteer if your study accepts them.

.. _viewing-a-participant-s-registration-information:

|proc| Viewing a Participant's Registration Information
-------------------------------------------------------
After a participant has been added to the Onyx database (either through an update of the appointment list or when they were enrolled as a volunteer), you can view their registration information.

Procedure
^^^^^^^^^
#. If the **Participants** page is not displayed, click the **Participants** tab.
#. Find the participant whose information you want to view. If you need help finding the participant, see :ref:`Finding a Participant <finding-a-participant>`.
   | When the **Participants** list is displayed, a **View** link appears (in the **Actions** column) for the participant.

   .. _the-participants-page-view:

   .. figure:: /images/theParticipantsPageInView.png
      :align: center
      :alt: To view a participant's registration information, click their View link.

      To view a participant's registration information, click their View link.
#. Select the **View** link for the participant. The **Participant** dialog is displayed.
   | Each study defines the information that is stored for its participants. You may not see the same fields as those shown in :ref:`this figure <participant-dialog>`.

   .. _participant-dialog:

   .. figure:: /images/participantDialog.png
      :align: center
      :alt: Participant dialog each study defines the information that is stored for participants

      Participant dialog each study defines the information that is stored for participants
#. When you have finished viewing the information, select the **Close** button. The **Participant** dialog closes.

.. _determining-who-has-a-lock-on-an-interview:

|proc| Determining Who Has a Lock on an Interview
-------------------------------------------------
If a lock icon |lock| is displayed at the right end of the row for a participant in the **Participants** list, an Onyx user has a lock on the interview, they are probably in the middle of an interview stage.
You might even have a lock on the interview yourself, if you logged in on another workstation and worked on the interview from there.
You can find out who has a lock on the interview as follows:

#. Move the mouse until the arrow cursor is on the lock icon and do not move the mouse for a few seconds.
   | A small popup message will show the name of the person who has the lock on the interview. See this figure.

   .. _see-who-has-a-lock-on-an-interview:

   .. figure:: /images/seeWhoHasALockOnAnInterview.png
      :align: center
      :alt: To see who has a lock on an interview, position the mouse cursor on the lock icon and do not move the mouse.

   To see who has a lock on an interview, position the mouse cursor on the lock icon and do not move the mouse.

If necessary, your participant manager can unlock the interview. See :ref:`Unlocking an interview <unlocking-an-interview>`.