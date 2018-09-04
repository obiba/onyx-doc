|proc| Enrolling a Participant from an External System
======================================================
If Onyx has been configured to look up participant information stored in an external system (a "participant registry"), the enrollment procedure is slightly different.
You will first search for the participant in that system, using whatever unique identifier that system requires. After that, you will assign to that participant a Participant ID.

Prerequisites
-------------
The prerequisites are the same as in "regular" enrollment.

Procedure
---------
#. The **Participant Registry** button is displayed in the upper right corner of the Participants page. See :ref:`this figure <participant-registry-button>`.

   .. _participant-registry-button:
   .. figure:: /images/participantRegistryButton.png
      :align: center
      :alt: Participant Registry button

      Participant Registry button
#. | Select the **Participant Registry** button. The **Participant Registry Lookup** pop-up window is displayed. See :ref:`this figure <the-participant-registry-lookup-pop-up>`.
   | The fields you see were defined by your study and may differ from those shown in :ref:`this figure <the-participant-registry-lookup-pop-up>`.

   .. _the-participant-registry-lookup-pop-up:
   .. figure:: /images/participantRegistryLookupPopUp.png
      :align: center
      :alt: Example of the Participant Registry Lookup pop-upthe fields are defined by the study

      Example of the Participant Registry Lookup pop-upthe fields are defined by the study
#. Enter the participant's unique identifier and select **Lookup**. Upon a successful lookup, the participant fields will be filled in with the retrieved information.
#. To enroll the participant, select **Receive**. The **Volunteer Registration** page will be displayed. Now proceed the same way as with "regular" enrollment.
#. If you decide not to enroll the participant, select the **Cancel** button. The **Participant Registry Lookup**  pop-up window closes and the **Participants** page is redisplayed unchanged.