# Enhancement

Decisyon App Composer Web was initially implemented in AngularJS, but with reaching its end-of-life in December 2021, it became necessary to evolve and keep the software up to date with new technologies. Therefore, the migration to a more recent version of Angular was made, with particular attention to the improvement of user interfaces.

DAC components have been carefully reviewed and optimized. This improved responsiveness and overall performance, ensuring smooth and reliable application operation.

### Migration to Angular latest version

#### **Landing Page** <a href="#landing-page" id="landing-page"></a>

In the Landing page the components that have undergone a restyle with the migration are the following:

* Main Menu
* Section Toolbar
* Tenant selector

<figure><img src="../../../.gitbook/assets/image (1970).png" alt=""><figcaption></figcaption></figure>

* Breadcrumb (when configured)

<figure><img src="../../../.gitbook/assets/image (2017).png" alt=""><figcaption></figcaption></figure>

#### **General Information** <a href="#general-information" id="general-information"></a>

The user interfance has been improved and the width of the buttons will adjust automatically to accommodate the length of the text they contains. This responsive design approach ensures that the buttons always appear properly sized and visually balanced, regardless of the length of the content they display.

<figure><img src="../../../.gitbook/assets/image (2019).png" alt=""><figcaption></figcaption></figure>

#### **Action list & Schedule Action List** <a href="#action-list-and-schedule-action-list" id="action-list-and-schedule-action-list"></a>

The dialog to create schedule in Scheduled Action LIst has been updated in the design, as shown in the figure below. The two tabs "**Details**" and "**Frequency**" have been combined in the same dialog. In addition, a switch has been added to enable the configuration of a cron expression.

<figure><img src="../../../.gitbook/assets/image (1972).png" alt=""><figcaption></figcaption></figure>

#### **Logo and Colors** <a href="#logo-and-colors" id="logo-and-colors"></a>

The [Logo & Colors](enhancement.md#logo-and-colors)[ ](enhancement.md#logo-and-colors)page has undergone a complete overhaul, yet the core functionality remains unaltered, and that's by design. Some of the changes are about :

the image crop feature has been improved, and along with it, the selection of primary and secondary colors has been revised.

* Improved image cropping
* New dialod selector for primary and secondary color
* The primary color is now used for less prominent components in the UI such as section/dialog toolbar, progress bar, loading and so on.&#x20;
* The secondary color is used to derive roles for key components across the UI, such as active states.

<figure><img src="../../../.gitbook/assets/image (2023).png" alt=""><figcaption></figcaption></figure>

In the new version has been removes the "Enable Live Preview" switch. Now, when a user selects the Primary and Secondary colors, DAC automatically enable the live preview and have the option to decide whether or not to keep the chosen color.

<figure><img src="../../../.gitbook/assets/image (1960).png" alt=""><figcaption></figcaption></figure>

#### **Terms of Use** <a href="#terms-of-use" id="terms-of-use"></a>

Terms of Use have been renamed to Terms of Use/Privacy Policy

<figure><img src="../../../.gitbook/assets/image (2024).png" alt=""><figcaption></figcaption></figure>

#### User Profile

<figure><img src="../../../.gitbook/assets/image (1897).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (1898).png" alt=""><figcaption></figcaption></figure>

#### Search the page navigation

<figure><img src="../../../.gitbook/assets/image (1899).png" alt=""><figcaption></figcaption></figure>



In the previous paragraphs , we have only looked at a few of the sections that have been migrated to a more recent version of Angular. Below is the complete list of the migrated sections.

* **Page Catalog section**
* **Alert Section**
* **Languages Administration**
* **Task**
* **User Attributes**
* **Terms of Use**
* **User Administration**
* **Api rest**
* **My documents**
* **Groups administration**
* **Labels Management**
* **Application Synchronization**
* **JOB**
* **Widget Catalogue**

### List of processed tickets

<details>

<summary>View the list of processed tickets</summary>

#### USERS ADMINISTRATION

D4C-8074 \[ USERS ADMINISTRATION ] Create users administration section container

D4C-8075 \[ USERS ADMINISTRATION ] Create tenant navigation sidenav

D4C-8076 \[ USERS ADMINISTRATION ] Create the users table

D4C-8077 \[ USERS ADMINISTRATION ] Manage infinity scroll on users table

D4C-8078 \[ USERS ADMINISTRATION ] Manage section toolbar search and filter

D4C-8079 \[ USERS ADMINISTRATION ] Manage user creation dialog

D4C-8080 \[ USERS ADMINISTRATION ] Manage user details sidenav

D4C-8081 \[ USERS ADMINISTRATION ] Create user edit dialog

#### WIDGET CATALOGUE

D4C-8096 \[Widget Catalogue] Update widget edit page&#x20;

D4C-8010 \[Widget Catalogue] Dac Widget Hub Dialog

D4C-8011 \[Widget Catalogue] Search filter

D4C-8012 \[Widget Catalogue] Widget Menu (without dependencies)

D4C-8013 \[Widget Catalogue] Folder Menu&#x20;

D4C-8014 \[Widget Catalogue] Widget dependencies

D4C-8043 \[Widget Catalogue] Widget Import

D4C-8097 \[Widget Catalogue] Highlighting Filtered Text

D4C-8250 Widget catalogue- Update multiple component

#### GENERAL INFORMATION

D4C-8082 \[ GENERAL INFORMATION ] Create general information section container

D4C-8117 \[ GENERAL INFORMATION ] Migrate info-box component

D4C-8118 \[ GENERAL INFORMATION ] Create Decisyon App Composer infobox

D4C-8119 \[ GENERAL INFORMATION ] Create Activation Key info box

D4C-8120 \[ GENERAL INFORMATION ] Create App Composer Environment Variables info box

D4C-8121 \[ GENERAL INFORMATION ] Create Log info box

D4C-8122 \[ GENERIC INFORMATION ] Create Resource info box

#### LANGUAGES ADMINIISTRATION

D4C-8222 Languages Administration - Create section

D4C-8223 Languages Administration - Create table

D4C-8224 Languages Administration - Add new language function

D4C-8225 Languages Administration - Add language menu and delete language function

D4C-8226 Languages Administration - Create Import label function

D4C-8227 Languages Administration - Create Export label function

D4C-8228 Languages Administration - Manage language update function

#### SECTIONS

D4C-7914 \[SECTION] Migrate Logo and Colors Section&#x20;

D4C-7959 \[SECTION] Migrate General Information Section&#x20;

D4C-7963 \[SECTION] Migrate Alert Section&#x20;

D4C-7965 \[SECTION] Migrate Users Administration Section&#x20;

D4C-7967 \[SECTION] Migrate Languages Administration Section&#x20;

D4C-7972 \[SECTION] Migrate Task Board Section&#x20;

D4C-7973 \[SECTION] Migrate Task List Section&#x20;

D4C-7974 \[SECTION] Migrate Task Details Section&#x20;

D4C-8030 \[SECTION] Migrate User Attributes Section&#x20;

#### TERSM OF USE

D4C-8291 \[Section Terms of Use] Migrate Definition of terms&#x20;

D4C-8292 \[Section Terms of Use] Migrate Link to view terms&#x20;

D4C-8293 \[Section Terms of Use] Migrate Request of terms accepting&#x20;

#### ACTION LIST

D4C-8294 Migrate Action list to angular - Tree navigation&#x20;

D4C-8300 Migrate Action list to angular - Folder&#x20;

D4C-8306 Migrate Action list to Angular - Schedule&#x20;

D4C-8312 Migrate Action list to Angular - Action list details&#x20;

D4C-8317 Migrate Action list section to Angular - Schedule details&#x20;

#### USER ADMINISTRATION

D4C-8351 Migrate User Administration to Angular - Create section&#x20;

D4C-8352 Migrate User Administration - Tenants tree integration and check update

D4C-8353 Migrate User Administration - User details on sidenav&#x20;

D4C-8354 Migrate User Administration - Section Filter&#x20;

D4C-8355 Migrate User Administration - Create User dialog&#x20;

D4C-8356 Migrate User Administration - User menu&#x20;

#### API

D4C-8413 Migrate Api rest to Angular - Tree navigation&#x20;

D4C-8420 Migrate Api rest to Angular - Rest api details&#x20;

#### GROUPS

D4C-8460 Migrate Groups administration to Angular - Tree navigation&#x20;

D4C-8467 Migrate Groups administration to Angular - Group details&#x20;

#### LABELS MANAGEMENT

D4C-8473 Labels Management - Create section and datatable&#x20;

D4C-8474 Labels Management - Create and Edit Label&#x20;

D4C-8475 Labels Management - Search field&#x20;

D4C-8476 Labels Management - Import labels&#x20;

D4C-8477 Labels Management - Export labels&#x20;

#### APPLICATION SYNCHRONIZATION

D4C-8538 Application Synchronization - Share metadata file&#x20;

D4C-8539 Application Synchronization - Import Applicatin&#x20;

D4C-8540 Application Synchronization - Create section and datatable&#x20;

#### JOBS

D4C-8588 JOB - Create section and datatable&#x20;

D4C-8591 Jobs - Menu voice&#x20;

D4C-8603 Jobs - Job manager&#x20;

#### IMAGE

D4C-7602 Migrate Big User Images&#x20;

D4C-7603 Migrate User Profile Section&#x20;

D4C-7605 Migrate Crop Image Dialog&#x20;

#### COMPONENT

D4C-7606 \[COMPONENT] Migrate the alert notification component&#x20;

D4C-7601 \[COMPONENT] Migrate Search filters on Section toolbar&#x20;

D4C-7761 \[COMPONENT] Improve the Change Password Dialog&#x20;

#### OTHERS

D4C-7678 Migrate the Generate Token dialog&#x20;

D4C-7679 Migrate the Change Password dialog&#x20;

D4C-7506 Cleaning after migration&#x20;

D4C-7510 Migrate Main Interface&#x20;

D4C-7685 Migrate Landing Page&#x20;

D4C-7789 Migrate page catalog section&#x20;

D4C-7802 Monitoring the execution status of each Dumbella job

D4C-7849 Enable the Report icon on the Landing Page Section Toolbar&#x20;

&#x20;D4C-8091 Migrate the user attribute component&#x20;

</details>



####

####







