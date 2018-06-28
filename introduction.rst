Introduction
============
Onyx can be customized to meet the needs of any organization that is collecting
data from participants for a medical reseacrch study. Customizing Onyx invloves
creating custom questionnaires and configuring Onyx to collect the physical
measurments and biosamples required by the study.

Planning Your Customization
~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. note:: **To the Organization that is Customizing Onyx**

  We recommend that you plan your customization of Onyx using this
  `spreadsheet <_static/files/Onyx_Customization_Planner.xls>`_. The completed
  spreedsheet will serve as a guideline for the programmer who will carry out
  the customization of Onyx for your organization.

.. list-table::
   :widths: 15 60 25
   :header-rows: 1

   * - Item
     - Explaination
     - What you need to do
   * - Enrollment mode
     - Onyx can manage participants with appointments or walk-in participants
       or both.
     - Decide which enrollment mode(s) you will use.
   * - Participant information fields
     - | Before the consent stage, Onyx can capture some identification
       | information about the participant. This information is either provided
       | with the appointment list or obatined when the participant is received.

       | Mandatory fields are: participant ID, name, and DOB. Other fields are configurable.

       | Onyx does not assign participant IDs. The study does. We need to know
       | the format of your participant IDs so Onyx can validate them when
       | participants are received. Participant IDs can be on barcode labels.
     - | Define a list of participant information fields.

       | For each field, define:

       * name (to be displayed onscreen)
       * variable name
       * type (date, list, and so on)
       * validation rule
   * - Stage ordering
     - | Onyx stages (consent, questionnaires, physical measurements, biosample
       | collection) can be listed onscreen in any order that is convenient for the study.
     - | Define a list of the stages in an interview; in the order that you
       | want them to appear onscreen.

       | For each stage, define:

       * name of the stage as it should appear onscreen
       * any stages that must be completed before the current stage can be
         started (and any data that the current stage must receive from those
         stage(s))
       * any stages that could be contraindicated after the current stage is
         completed (and any data that the current stage must send to the
         dependent stage)
       * whether or not the stage can be skipped
   * - Consent form
     - The participant's signature can be obtained in various ways: Manual,
       electronic, or both.
     - | Decide which signature modes will you use.

       | If you will accept consent electronically, prepare the consent form in
       | PDF format
   * - Questionnaire stages
     - | One or more questionnaires can be defined.

       | The questions in a questionnaire should be grouped into pages
       | (questions that you want to appear on the same screen). Questions can
       | also be grouped into sections (by topic).

       | You can define "skip patterns"; whether or not to display certain questions based on
       | answer(s) to previous question(s). A skip pattern can be for a page (hide some questions
       | in the page initially and only display them if the participant gives a particular answer to
       | another question in the page). A skip pattern can also be for a section (do not display
       | section about smoking if participant is a non-smoker).

       | A questionnaire can be displayed in different modes:

       * standard screen
       * touchscreen (suitable for self-administered questionnaires)
       * both
     - | For each questionnaire, define:

       * a list of questions (grouped by section, if sections used)
       * display mode(s)
       * skip patterns

       | For each question, define:

       * text to display onscreen
       * answer type (e.g single choice, multiple choice, open text)
       * variable name(s)
       * category names (answers to display onscreen)
       * category codes
       * validation rule (if required)
   * - Contraindication check
     - | We recommend that you define a preliminary questionnaire to establish if any physical
       | measurements or the collection of certain biosamples are contradicated.
     - You need to define the same information as for any questionnaire.
       In addition, we need to decide which answers contradindicate which stages.
   * - Physical measurement stages
     - | A physical measurement stage usually acquires one type of measurement on one
       | instrument. However, if several measurements are normally taken together, they can all
       | be grouped in one physical measurement stage.

       | Measurements can be entered manually or automatically captured from electronic
       | instruments (if instrument has its own application, or both.

       | A measurement can be obtained once or multiple times.
     - | Define the list of measurements to be acquired.

       | For each measurement, indicate:

       * type of measurement
       * onscreen direction to staff about how to do measurement
       * data entry mode: manual entry or automatic data capture
       * for automatic data capture from an instrument, name any inputs that instrument needs
         to receive from Onyx before it can measure
       * field(s) for measurements with unit of measure and validation rule for the field
       * number of times each measurement should be taken
   * - Biosample collection stages
     - | Several types of sample can be acquired.
       | Multiple samples of each type can be acquired.
       | One or more sample collection stages can be defined: one type of sample per stage, or
       | several types per stage; whatever is convenient for the study.

       | Barcode labels on samples can be scanned. The barcode can have a syntax (participant
       | code, sample type, incremental number, and so on).
     - | List of sample collection stages and type(s) of samples to be collected in each stage.

       | For each sample collection stage, indicate:

       * type(s) of sample
       * onscreen directions for staff about how to collect samples
       * will barcodes labels be used? Provide barcode syntax, if known.
       * how many samples of each type are expected
       * whether or not you need to check for contraindications
       * a list of predefined comments that staff could select to describe a sample if necessary
   * - Report(s) to be given to the participant
     - Optional. You can define one or more reports that staff can print and give to participants
       after completing a stage or at the end of the interview.
     - | Define a list of report(s) that will be printed and given to the participants.

       | For each report, prepare the test in a Word document.
   * - Interview conclusion
     - Optional. You can define a conclusion stage. For example, a checklist for staff members
       to go over at the end of the interview.
     - Define the text display onscreen.
   * - Experimental conditions
     - Optional. You can define one or more logs in which staff will record experimental
       conditions. For example, you could have one log for "Room Conditions" (like temperature
       and relative humidity), and another log for "Location Characteristics" (like meters above
       sea level).
     - | Define a list of logs.

       | For each log, define:

       * log name (to be displayed)
       * a list of condition variables (there may be only one)

       | For each condition, define:

       * condition name (to be displayed)
       * type (integer, text, and so on)
       * unit of measure (if appropriate)
       * validation rule (if necessary)
   * - Instrument calibration
     - | Optional. You can define calibration procedures for physical measurements.

       | For a particular physical measurement, your staff might need to perform one or several
       | calibrations. For example, for a measurement of "Standing Height", they might need to
       | calibrate "Vertical Alignment" and "Accuracy"
     - | A list of the calibration procedures.

       | For each calibration, indicate:

       * name of the calibration (to be displayed)
       * name of the physical measurement to which the calibration is related
       * onscreen directions to the staff
       * list of calibration variables (there may be only one)

       | For each calibration variable, indicate:

       * type of value (integer, text, and so on)
       * unit of measure (if appropriate)
       * validation rule (if necessary)
   * - Data export
     - | Data can be exported to xml files.

       | You can define:

       * one or more export destinations
       * the types of data (participant, experimental conditions, instrument calibrations) that you
         want to export to each destination
       * which data you want to be export for each type of data
       * whether or not to encrypt participant data

       | The names of export files will be composed of the destination name and the date and
       | time of export.
     - | Define a list of export destinations

       | For each export destination, define:

       * destination name (it will be included in the name of the export file)
       * type of data (participant, experimental conditions, instrument calibrations) to
         export to this destination

       | For each type of data, define:

       * the variables to be exported
       * for participant data, whether or not the encrypt the data
       * any particularities: for example, timeframe used to select data for export

Who should read this Guide
~~~~~~~~~~~~~~~~~~~~~~~~~~
This guide is mainly for **Onyx customizers**. By a *customizer*  we mean a
programmer who has been asked by an organization to customize Onyx to meet the
requirements of their research study. Ideally, this person is somewhat or very
familiar with Java and how Java implements web applications. The result of the
customizer's work will be a war file that will be used to install the custom
version of Onyx on a server at the site where Onyx will be used.

This guide may also be used by **Onyx installers** to tweak the Onyx
configuration immediately after installation or later. By an *installer*, we
mean the person who will set up the Onyx server and workstations at the site
where Onyx will be used. An installer may be a system administrator, an IT
person, or even the customizer.
