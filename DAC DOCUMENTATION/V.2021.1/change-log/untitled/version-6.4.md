# Version 6.4

## 6.4.1

### Fixed Defects ​​

**This section of the Change Log provides a list of the defects solved.**

[D4C-4971](https://decisyon.atlassian.net/browse/D4C-4971) Custom Widget: error associated-workflow property invalid value .

[D4C-4973](https://decisyon.atlassian.net/browse/D4C-4973) Application Synchronization Fails.

[D4C-4975](https://decisyon.atlassian.net/browse/D4C-4975) Error using ExtSubscribeEvent js function.

[D4C-4978](https://decisyon.atlassian.net/browse/D4C-4975) Deploy page (also with catalogue) not synchronized on Azure environment.

[D4C-4984](https://decisyon.atlassian.net/browse/D4C-4984) Unable to fully authenticate users on Schneider IDMS.

## 6.4.0

### New Features Introduced

**This section of the Change Log provides a list of the new requirements implemented in version Katy**\
<br>

* [D4C-4485 Activate a DAC instance:](https://decisyon.atlassian.net/browse/D4C-4485) Now it’s possible to activate a new DAC instance.
* [D4C-4486 Deactivate a DAC instance:](https://decisyon.atlassian.net/browse/D4C-4486) Now it’s possibe  to deactivate an existing DAC instance.
* [D4C-4487 Change existing DAC activation key:](https://decisyon.atlassian.net/browse/D4C-4487) Now it’s possible  to replace an existing product activation key with another one.&#x20;
* [D4C-4489 View DAC instance activation info:](https://decisyon.atlassian.net/browse/D4C-4489)  Now it’s possible to view DAC activation info
* [D4C-4660 Russian chars are not supported for crosstab PDF export: ](https://decisyon.atlassian.net/browse/D4C-4660) Now, when the crosstab contains records in russian language, they are correcly exported in PDF.
* [D4C-4744 Create a demoable version of Decisyon Workflow (Flowable)](https://decisyon.atlassian.net/browse/D4C-4744)&#x20;
* [D4C-47 Fusion Chart Upgrade:](https://decisyon.atlassian.net/browse/D4C-47) The ‘FusionCharts’ library is now used for graphs.
* [D4C-3713 Upgrade of “Logo and Colors” Page:](https://decisyon.atlassian.net/browse/D4C-3713) It’s now available a new version of the ‘Logo & Colors’ section.
* [D4C-4490 Refresh active key information:](https://decisyon.atlassian.net/browse/D4C-4490) Now the information on an active key can be updated.
* [D4C-4597 Task details section:](https://decisyon.atlassian.net/browse/D4C-4597)  A new task details section is available.
* [D4C-4742 Import system language labels:](https://decisyon.atlassian.net/browse/D4C-4742) Now it’s possible to  be able to import system labels for existing language.
* [D4C-4743 Languages section:](https://decisyon.atlassian.net/browse/D4C-4743)  A new “Languages Administration” section is now available on the Run Time, to manage the system labels.
* [D4C-4781 Export system language labels:](https://decisyon.atlassian.net/browse/D4C-4781)  Now it’s possible to export all system language labels, to be translated.
* [D4C-4782 Update system language labels:](https://decisyon.atlassian.net/browse/D4C-4782) Now it’s possible to  xport the system language labels to be translated to update an existing language.
* [D4C-4783 Use a breadcrumb to navigate among Pages:](https://decisyon.atlassian.net/browse/D4C-4783) Now it’s possible to navigate among the pages using a breadcrumb in order to select and refresh pages easily.
* [D4C-4808 Synchronize languages:](https://decisyon.atlassian.net/browse/D4C-4808) When synchronizing two environments, any defined languages and system labels are now synchronized
* [D4C-4871 New Landing Page Section Toolbar:](https://decisyon.atlassian.net/browse/D4C-4871) has been changed the section toolbar in Landing page adding a new breadcrumb

### Enhancements Introduced

**This section of the Change Log provides a list of the new enhancements implemented in version Katy**<br>

* [D4C-3895 ](https://decisyon.atlassian.net/browse/D4C-3895)Manage the page navigation through UI-Router: Now the navigation of the pages ( tree and tabs ) is manage  through UI-Router.
* [D4C-3932](https://decisyon.atlassian.net/browse/D4C-3932)Refactoring of exceptions management for Controllers Users, Tasks, Labels, REST Api, User Profile, Groups and Alerts.&#x20;
* [D4C-4214](https://decisyon.atlassian.net/browse/D4C-4214) Change the UX of landing page when user doesn’t have access to app and pages : Now when the user has no APP associated, the system displays a message to warn him.
* [D4C-4236](https://decisyon.atlassian.net/browse/D4C-4236) Improve REST Api Authentication when invoked internally : It has been improved authentication REST API when invoked internally.
* [D4C-4247](https://decisyon.atlassian.net/browse/D4C-4247) Add @Role annotation for authorising access to the REST Api of administration.&#x20;
* [D4C-4171](https://decisyon.atlassian.net/browse/D4C-4171) Alert UI add search box in the dropdown component.&#x20;
* [D4C-4181](https://decisyon.atlassian.net/browse/D4C-4181) Use Fusion Chart library when using charts in web report editor.
* [D4C-4688](https://decisyon.atlassian.net/browse/D4C-4688) Tasks that exceeded the due date must not be flagged as “invalid”.&#x20;
* [D4C-4312](https://decisyon.atlassian.net/browse/D4C-4312) \[F-end] exceptions management User Administration Section.&#x20;
* [D4C-4313](https://decisyon.atlassian.net/browse/D4C-4313) \[F-end] exceptions management User Profile Section.&#x20;
* [D4C-4314](https://decisyon.atlassian.net/browse/D4C-4314) \[F-end] exceptions management Groups Section.&#x20;
* [D4C-4315](https://decisyon.atlassian.net/browse/D4C-4315) \[F-end] exceptions management Business Labels Section.
* [D4C-4316](https://decisyon.atlassian.net/browse/D4C-4316) \[F-end] exceptions management REST Api Section.
* [D4C-4317](https://decisyon.atlassian.net/browse/D4C-4317) \[F-end] exceptions management Alert Section.
* [D4C-4318](https://decisyon.atlassian.net/browse/D4C-4318) \[F-end] exceptions management Task Section.
* [D4C-4402](https://decisyon.atlassian.net/browse/D4C-4402) Alert section refactoring for UI-Routing support.
* [D4C-4511](https://decisyon.atlassian.net/browse/D4C-4511) Add the code name to the DAC’s General Info and Design Studio’s About panel: Now in the DAC’s General Info and Design Studio’s About panel has been added code name to the version shown.
* [D4C-4538](https://decisyon.atlassian.net/browse/D4C-4538) Improve client and back end side language support.
* [D4C-4576](https://decisyon.atlassian.net/browse/D4C-4576) Task section refactoring for UI-Routing support.&#x20;
* [D4C-4588](https://decisyon.atlassian.net/browse/D4C-4588) Replace AbstractConnectedThread with @Scheduled tasks.                        &#x20;
* [D4C-4674](https://decisyon.atlassian.net/browse/D4C-4674) Contextual link on task opens dialog with report, not the page.
* [D4C-4728](https://decisyon.atlassian.net/browse/D4C-4728) Metric editor doesn’t keep wrapping in the SQL formula.
* [D4C-4746](https://decisyon.atlassian.net/browse/D4C-4746) User DAC’s token to authN and authZ Gertrude and Flowable-Modeler.
* [D4C-4809](https://decisyon.atlassian.net/browse/D4C-4809) Add new Fusion Chart graphs.
* [D4C-4810](https://decisyon.atlassian.net/browse/D4C-4810) Migrate static charts to the dynamic counterpart.                                       &#x20;
* [D4C-4812](https://decisyon.atlassian.net/browse/D4C-4812) Remove the Report’s charts preview from the DS.
* [D4C-4868](https://decisyon.atlassian.net/browse/D4C-4868) Make DS use the Spring Profile.
* [D4C-4182](https://decisyon.atlassian.net/browse/D4C-4182) Hide application selection sidebar in case of only one app: Now, when the user is associated with only one application, the application section toolbar is hidden.  &#x20;

### Fixed Defects ​

**This section of the Change Log provides a list of the defects solved.**

[D4C-4803](https://decisyon.atlassian.net/browse/D4C-4803) Dialogs opens in the background in Design Studio.

[D4C-4051](https://decisyon.atlassian.net/browse/D4C-4051) Back button in the Pages: works on the second click and the original page remains selected. Non assegnata&#x20;

[D4C-4075](https://decisyon.atlassian.net/browse/D4C-4075) Unstandardized management of the tag in a discussion.&#x20;

[D4C-4343](https://decisyon.atlassian.net/browse/D4C-4343) Error opening task from mail notification.&#x20;

[D4C-4630](https://decisyon.atlassian.net/browse/D4C-4630) Custom Label not translated on Landing Page.

[D4C-4663](https://decisyon.atlassian.net/browse/D4C-4646) Empty page on Drill Through from Charts.

[D4C-4670](https://decisyon.atlassian.net/browse/D4C-4670) Pages of selected application disappear when click on logo in header.

[D4C-4671](https://decisyon.atlassian.net/browse/D4C-4671) No legend and level value on some animated charts.

[D4C-4721](https://decisyon.atlassian.net/browse/D4C-4721) The user can delete the default system language.

[D4C-4727](https://decisyon.atlassian.net/browse/D4C-4727) Widget Designer preview doesn’t work (HTTP 404 error in console).

[D4C-4877](https://decisyon.atlassian.net/browse/D4C-4877) the properties in sidebar of DAC depends on user’s language.

[D4C-4886](https://decisyon.atlassian.net/browse/D4C-4886) In report’s pageby search is limited only to visible elements.

[D4C-1593](https://decisyon.atlassian.net/browse/D4C-1593) Object not draggable on crosstab’s Advanced Sorting.

[D4C-3785](https://decisyon.atlassian.net/browse/D4C-3785) Wrong Owner importing a widget.

[D4C-3811](https://decisyon.atlassian.net/browse/D4C-3811) The system creates but not populates the EI table of an excel integration.

[D4C-4094](https://decisyon.atlassian.net/browse/D4C-4094) Open task by code javascript (extCreateTask) on a page and the task is not created.

[D4C-4116](https://decisyon.atlassian.net/browse/D4C-4116) Sort by Priority doesn’t work on Task Board.

[D4C-4463](https://decisyon.atlassian.net/browse/D4C-4463) Document not created on Azure.

[D4C-4611](https://decisyon.atlassian.net/browse/D4C-4611) Error connectin on DAC DS using Open Connect.

[D4C-4614](https://decisyon.atlassian.net/browse/D4C-4614) Report not filtered on Discussion tag selection.

[D4C-4615](https://decisyon.atlassian.net/browse/D4C-4615) Error Creating a new alert.

[D4C-4616](https://decisyon.atlassian.net/browse/D4C-4616) Logo and Favicon no more available on Logo and Colors section.

[D4C-4622](https://decisyon.atlassian.net/browse/D4C-4622) Error generating User Token.

[D4C-4629](https://decisyon.atlassian.net/browse/D4C-4629) Console ERROR saving using profile.

[D4C-4633](https://decisyon.atlassian.net/browse/D4C-4633) Exceptions management REST Api Section.

[D4C-4634](https://decisyon.atlassian.net/browse/D4C-4634) The “Set user local timezone” fail.

[D4C-4636](https://decisyon.atlassian.net/browse/D4C-4636) Users with no Admin role are wrongly not authorised to use most of the DAC functionality.

[D4C-4637](https://decisyon.atlassian.net/browse/D4C-4637) Exceptions management User Profile Section.

[D4C-4646](https://decisyon.atlassian.net/browse/D4C-4646) Unable to view the Space Wizard Page.

[D4C-4648](https://decisyon.atlassian.net/browse/D4C-4648) Javascript error.

[D4C-4649](https://decisyon.atlassian.net/browse/D4C-4649) WebSocket Javascript error.

[D4C-4662](https://decisyon.atlassian.net/browse/D4C-4662) Multi language labels are not applied on some dialogs of crosstab.

[D4C-4664](https://decisyon.atlassian.net/browse/D4C-4664) No Admin user can edit Page on DAC web aplication.

[D4C-4680](https://decisyon.atlassian.net/browse/D4C-4680) User Not disconnected when Admin change Email or Username.

[D4C-4681](https://decisyon.atlassian.net/browse/D4C-4681) No Administrator user can’t save User Profile.

[D4C-4682](https://decisyon.atlassian.net/browse/D4C-4682) Generic message on User Profile Email or Username already used.

[D4C-4683](https://decisyon.atlassian.net/browse/D4C-4683) Wrong Aler on Wrong Password on User Profile/Management.

[D4C-4685](https://decisyon.atlassian.net/browse/D4C-4685) Error saving new user.

[D4C-4686](https://decisyon.atlassian.net/browse/D4C-4686) Generic error on no standard password for user creation.

[D4C-4687](https://decisyon.atlassian.net/browse/D4C-4687) No alert on tab title for Aler DATA.

[D4C-4673](https://decisyon.atlassian.net/browse/D4C-4673) Report re-designed after a contextual discussion is attached.

[D4C-4698](https://decisyon.atlassian.net/browse/D4C-4698) Error running Design Studio on empty database/schema.

[D4C-4701](https://decisyon.atlassian.net/browse/D4C-4701) Console exceptions on open task preview dialog.

[D4C-4705](https://decisyon.atlassian.net/browse/D4C-4705) white icons on main toolbar.

[D4C-4733](https://decisyon.atlassian.net/browse/D4C-4733) Error on Landing page when there are no visible applications.

[D4C-4734](https://decisyon.atlassian.net/browse/D4C-4734) The system doesn’t allow to open or run a report in a read mode if the report id locked by another administrator user.

[D4C-4778](https://decisyon.atlassian.net/browse/D4C-4778) Group Management: error when loading groups.&#x20;

[D4C-4541](https://decisyon.atlassian.net/browse/D4C-4541) Error adding Execute button on Page Designer.

[D4C-4807](https://decisyon.atlassian.net/browse/D4C-4807) SUBJECTS locker on user creation.

[D4C-4817](https://decisyon.atlassian.net/browse/D4C-4817) Business label not translated if user language is English.

[D4C-4820](https://decisyon.atlassian.net/browse/D4C-4820) labels not translated on Alert section.

[D4C-4847](https://decisyon.atlassian.net/browse/D4C-4847) ERROR generatin user tocken.

[D4C-4850](https://decisyon.atlassian.net/browse/D4C-4850) Appcomposer container do not run due to an error.

[D4C-4864](https://decisyon.atlassian.net/browse/D4C-4864) No version for languages added before new languages mnanagement.

[D4C-4867](https://decisyon.atlassian.net/browse/D4C-4867) Timezone NO set in the DS after a new metadata installation.

[D4C-4869](https://decisyon.atlassian.net/browse/D4C-4869) Links in the task’s mail doesn’t work.

[D4C-4882](https://decisyon.atlassian.net/browse/D4C-4882) Russian character not rendered on Alert Details.

[D4C-4893](https://decisyon.atlassian.net/browse/D4C-4893) “My Document” graphical issue.

[D4C-4894](https://decisyon.atlassian.net/browse/D4C-4894) Impossible to save a non-administrator user profile.

[D4C-4895](https://decisyon.atlassian.net/browse/D4C-4895) Appcomposer Restart necessary to refresh system labels.

[D4C-4896](https://decisyon.atlassian.net/browse/D4C-4896) system labels last update missed.

[D4C-4898](https://decisyon.atlassian.net/browse/D4C-4898) Default language not setted for users when a language is deleted.

[D4C-4903](https://decisyon.atlassian.net/browse/D4C-4903) No color on new Logo And Colors management migration&#x20;

[D4C-4910](https://decisyon.atlassian.net/browse/D4C-4910) Additional notification recipients list empty on alert creation.

[D4C-4661](https://decisyon.atlassian.net/browse/D4C-4661) Advanced sorting dialog doesn’t show levels aliases .

[D4C-4693](https://decisyon.atlassian.net/browse/D4C-4693) Error when creating contextual task on a SQL Report.

[D4C-4873](https://decisyon.atlassian.net/browse/D4C-4873) Button create signal, from section my signal, is covered.

