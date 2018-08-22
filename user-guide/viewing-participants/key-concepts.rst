Key concepts
============
This section contains key concepts related to viewing participants.

|key| Participants List
-----------------------
A list of participants stored in the Onyx database.
When you are in the **Participants** page, you can choose to see some or all of the participants in the Onyx database by filtering the participants list in various ways:
by name, enrollment ID, or participant ID. You can view all participants with appointments today or those currently being interviewed.

|key| Appointment List
----------------------
A list of appointments stored in a file or created in a programme other than Onyx.
Since Onyx does not allow you to schedule appointments for participants, it imports an appointment list from a file or another programme.
Onyx users of the type participant manager can update the appointment list.
As a minimum, the appointment list contains the following information for each participant:

* participant name
* apointment date and time
* enrollment ID

The appointment list may contain other information depending on how Onyx was configured for your study.


|key| Enrollment ID
-------------------
A unique identifier for a participant that is imported into Onyx from the appointment list.
Enrollment IDs are either assigned automatically by the programme that schedules appointments, or they are defined in the file containing the appointment list.
After the participant has been received, the Enrollment ID is not used very much in Onyx. Instead, the Participant ID is used to identify the participant during the interview.
However, you can search for a participant by their Enrollment ID.
You may notice that some participants do not have an Enrollment ID. This is probably because your study accepts Volunteer Participants.
Volunteers do not have an enrollment ID since they were never on an appointment list.

|key| Participant ID
--------------------
A unique identifier for a participant that must be entered in Onyx when the participant arrives at the assessment centre and at various times during the interview.
Each study or assessment centre decides how it will assign Participant IDs and the format of its Participant IDs (the pattern of numbers and letters in the ID).
Some studies use barcodes that can be scanned and displayed automatically in Onyx. Other studies will require you to enter the Participant ID manually.

|key| Participant Barcode
-------------------------
A barcode that is used for the Participant ID.
Some studies use a barcode as the source of Participant IDs. The barcodes may be on a blood collection tube, an ID bracelet, or a label of some sort.
If your study uses barcodes, a barcode scanner will be connected to your Onyx workstation so that you can easily obtain the Participant ID.

.. _interview-status:

|key| Interview Status
----------------------
The current state of a participant's interview. See also Stage Status.
The status of a participant's interview appears in the Status column of the Participants list. Before a participant has been received, nothing appears in the status column for that participant.
After a participant has been received, their interview can have one of these statuses:

* **In Progress** — This status means that the participant has been received and that their interview has been started.
  | Even if the participant leaves the room for some reason (and a stage of their interview has been paused), the status of their interview remains In Progress.
  | See Displaying a list of In Progress interviews.
* **Locked** — The lock icon  means another staff member is interviewing the participant. If you suspect that there is a problem or if you need to work on the interview, contact your participant manager who can remove the lock, if necessary.
  | See Unlocking an Interview.
* **Completed** — This status means that the interview was completed and that all stages were completed successfully and the interview was concluded correctly by a staff member.
* **Closed** — This status means that the interview was closed without all the stages being completed. An interview can be closed at any stage, if necessary.
  | A closed interview cannot be restarted. The data collected cannot be changed in any way. Depending on how your study configured Onyx, it may or may not be possible to export the data.
  | See Closing an Interview.
* **Cancelled** — This status means that the participant was withdrawn from the study. A staff member cancelled the interview. A cancelled interview cannot be restarted. See Cancelling an Interview.

Your study customized what Onyx does when an interview is cancelled or closed. It may delete the participant or may keep some or all of the data so it can be exported.
