Key concepts related to the way Onyx works
==========================================

|key| Participant
-----------------
A participant is a person who has come to the assessment centre in order to participate in the research study.
Assessment centre staff collect data from participants by asking questions, collecting biospecimens, and taking physical measurements.
Each research study determines how they will recruit participants. Typically, participants are either :ref:`invited <invited-participant>` or :ref:`volunteers <volunteer-participant>`.
Onyx can be customized to accept volunteer participants or not. Whether or not this functionality appears in Onyx at your assessment centre depends on how Onyx was configured for your study. See :ref:`Receiving vs. Enrolling Participants <refTodo>`

.. _refTodo:

.. _invited-participant:

|key| Invited Participant
-------------------------
A participant who was selected by the study and given an appointment time for their interview.

.. _volunteer-participant:

|key| Volunteer Participant
---------------------------
A volunteer participant (also known as a "walk-in" Walk-in participants) arrives at the assessment centre without an appointment. They heard
about the study in some way and decided that they would like to participate.

|key| Interview
---------------
Onyx treats an interview as a set of interdependent stages that a participant goes through in order to complete their visit to the assessment centre.
See :ref:`this figure <onyxMainFunctionalities>` . An interview starts when a staff member receives the participant and enters registration information for the participant in
Onyx. The participant then passes through some or all the stages that have been defined for the study. The interview ends when a staff member
clicks the Close interview button in Onyx.

.. _onyxMainFunctionalities:
.. figure:: /images/onyxMainFunctionalities.jpg
   :align: center
   :alt: Onyx treats an interview as a set of interdependent stages

   Onyx treats an interview as a set of interdependent stages

|key| Interview Stages
----------------------
An interview stage is one of the interdependent parts of an interview during which a particular type of data is collected from the participant.
Each research study defines the stages it requires to obtain the necessary data, as well as the sequence in which the stages appear in Onyx.
Typical interview stages include:

* Signing a consent form
* Questionnaires (one or more)
* Physical measurements (one or more)
* Collection of biospecimens (one or more)
* Conclusion of the interview (may include printing a report for the participant that includes information considered appropriate by the research study)

Each research study defines its own stages, creates its own questionnaires, and decides which physical measurements and biospecimens must be collected.
Onyx stores the data collected during the stages centrally and makes it available to all workstations.
