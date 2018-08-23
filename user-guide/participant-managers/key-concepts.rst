Key concepts
============
This section contains key concepts related to working your way through the stages of an interview.


|key| Obtaining a Lock on an Interview
--------------------------------------
When you enter the **Interview** page of a participant, you obtain a lock on the interview. 
No other user can access the particpant's Interview page until you exit the **Interview** page properly (by selecting an Interview Exit button--- see :ref:`Interview Exit buttons <interview-exit-buttons>`). 
If Onyx crashes or if you exit the Interview page improperly (by selecting the Onyx Exit button---see :ref:`this figure <the-interview-page>`), a participant manager will have to unlock the interview.
See :ref:`Unlocking an Interview <unlocking-an-interview>`.

|key|  Stage Status
-------------------
An interview stage passes through various statuses from "ready" to "completed". Each type of stage (consent, questionnaire, physical measurement, specimen collection, interview conclusion) follows a particular path through the statuses.
The **Actions** that are available depend on the **Status** of the stage Each study defines the conditions that are required for a stage's status to change.
A study can customize the names of the statuses that appear in the **Interview** page.


|key| Stage Actions
-------------------
The Actions column lists the actions that are available to you for a particular stage of the interview. The **Actions** depend on the **status** of the stage.
Each study defines the actions that are available when a stage has a certain status. A study can also customize the names of the actions that appear in the **Interview** page.
Despite all the customization that Onyx allows, only five stage actions are possible: By default, the actions have the names indicated in this list.

* **Start** — You select this action to start a stage.
* **Skip** — You select this action to skip a stage. Some examples of why you might need to skip a stage: the stage is **Not ready**; it is more convenient to do the stage later; another staff member is responsible for the stage.
* **Reinstate** — You select this action to redo a stage that was skipped.
* **Cancel** — You can cancel a stage that is contraindicated or not applicable for some reason.
* **Review** — You can review a stage that was contraindicated in order to determine if the contraindication is appropriate or, if the answers that caused it should be corrected so that the contraindication will be removed.

|key| Closing vs. Cancelling an Interview
-----------------------------------------
Closing an interview means ending the interview early before all stages have been completed (or skipped, if your study permits). The participant is not withdrawn from the study.
Cancelling an interview means withdrawing the participant from the study. The decision to withdraw a participant may come from the participant or a staff member.
**CAUTION**: If you select the **Close** or **Cancel **button in the **Interview** page, you will not be able to continue the interview with the participant later.
If you want to leave the Interview page temporarily and continue the interview later, you need to exit the **Interview** page. :ref:`this figure <the-interview-page>`.
Each study defines what will be done with the data acquired to the point of closing or cancelling an interview.

|key| Reviewing vs. Reinstating a Stage
---------------------------------------
You can review a stage if its status is **Contraindicated**. If you review the stage and change the condition (for example, the answer to a particular question) that caused the stage to be contraindicated, you can actually change the status of the stage from **Contraindicated** to **Ready**.
You can reinstate a stage that was skipped. When you reinstate a stage, its status will change to **Ready** and it will be possible to **Start** the stage again.

|key| Action Windows
--------------------
Depending on how your study customized Onyx, Onyx may display an action window when you select an **Action** in the **Interview** page.
These windows usually require you to enter your password and the Participant ID (you can scan the barcode or enter it manually).
An action window may contain other fields depending on the action that you selected and how your study customized the window.
The purpose of action windows is to ensure the integrity of the data being collected. When you enter your password, you confirm that it was actually you who carried out the action.
When you enter the **Participant ID**, you confirm that the data is indeed being collected for the correct participant. :ref:`this figure <action-windows>`shows an example action window.

.. _action-windows:
.. figure:: /images/actionWindows.png
   :align: center
   :alt: Example of the action windows that may be displayed during an interview

   Example of the action windows that may be displayed during an interview

|key| Stage Navigation Buttons: Previous, Next, Finish
------------------------------------------------------
When you are in a stage, you will see various buttons at the bottom of the page. These buttons allow you to move back and forth through the pages of the stage and to finish the stage.
:ref:`See this figure <stage-navigation-buttons>`.
By default, the buttons are named as shown in :ref:`See this figure <stage-navigation-buttons>`. Your study may have changed the names on the buttons.

.. _stage-navigation-buttons:
.. figure:: /images/stageNavigationButtons.png
   :align: center
   :alt: The buttons that allow you to move through and finish the pages of an interview stage

   The buttons that allow you to move through and finish the pages of an interview stage

You use the buttons as follows:

* **Next** button — Select it to display the next page in the stage.
* **Previous** button — Select it to display the previous page in the stage if you need to check or change something in that page.
* **Finish** button — This is only displayed when you are on the last page of a stage. You select it when you are ready to complete the stage.
* You can also use hot keys to navigate through the pages. See Hot Keys.

