# vaadin-ckeditor
CKEditor is a javascript-based HTML "rich text" WYSIWYG editor that works in common browsers.  
This component provides a wrapper around it for use in a Vaadin-based (Java servlet plus GWT) application. 

## Using ckeditor for vaadin in your application

Put the pre-built JAR file and in your Vaadin application's WEB-INF/lib. This has everything you need to use it, including a version of CKEditor. You will need to "Compile Vaadin widgets", which is an icon in the Eclipse menubar. Then look at the example application for the basic setup.

## How to setup Eclipse

1. Clone the repository [https://github.com/OpenESignForms/vaadin-ckeditor](https://github.com/OpenESignForms/vaadin-ckeditor).
2. Intall Eclipse IDE for Enterprise Java and Web Developers.
3. Create a Eclipse workspace.
4. Open the project in Eclipse:
    1. Go to File -> Open Projects from File System...
    2. Select the cloned folder "vaadin-ckeditor\VaadinCKEditor".
    3. Click Finish.
5. Install Apache IvyDE: [https://marketplace.eclipse.org/content/apache-ivyde%E2%84%A2](https://marketplace.eclipse.org/content/apache-ivyde%E2%84%A2).
    1. Unfortunately, IvyDE has been archived according to [https://ant.apache.org/ivy/ivyde/](https://ant.apache.org/ivy/ivyde/). The old update site link [http://www.apache.org/dist/ant/ivyde/updatesite](http://www.apache.org/dist/ant/ivyde/updatesite) is NOT valid anymore. Instead, the archived update site seems to be available using this link: [https://archive.apache.org/dist/ant/ivyde/updatesite/](https://archive.apache.org/dist/ant/ivyde/updatesite/).
    2. To install the plugin, go to Help -> Install New Software...
    3. Click the "Add" button:
        1. Name: Apache IvyDE
        2. Location: [https://archive.apache.org/dist/ant/ivyde/updatesite/](https://archive.apache.org/dist/ant/ivyde/updatesite/).
6. Download dependencies:
    1. Right-click on the project in the "Project Explorer" and click on Ivy -> Resolve.
7. Add the CKEditor library manually:
    1. Download the latest version (4.\*.\*) from ckeditor.com, including the Full Package.
    2. Extract the contents - you should have a "ckeditor" folder.
    3. Copy the "ckeditor" folder to src/org/vaadin/openesignforms/ckeditor/widgetset/public.
    4. If you want to use the Vaadin Save button plugin, copy "ckeditor/plugins" vaadinsave to "src/org/vaadin/openesignforms/ckeditor/widgetset/public/ckeditor/plugins". This is already done in the released CKEditor code.
8. Click on Project -> Properties -> Java Build Path -> Libraries -> Add Class Folder and select "WebContent".

## Building the JAR
1. Perform a "Search and Replace" of the current version with the new version:
    1. Example: Change "7.12.9" to "7.12.10."
2. Double-click on the file "build-jar.jardesc."
3. In the "Select the export destination" field, set it to "VaadinCKEditor\vaadinckeditor-\*.\*.\*.jar," where "\*.\*.\*" corresponds to the new version.
4. Click "Finish".

## Note:
This widget is compiled using JDK 1.6 / Java 6.  We have been using 1.6 for years now (it was released December 2006) and see no reason to use such an outdated JDK 1.5 per Vaadin's widget specs.

The CKEditor code, in full as downloaded from http://ckeditor.com, is present in the "src/org/vaadin/openesignforms/ckeditor/public" folder. No changes to CKEditor were made. However, we remove the following files from the standard CKEditor distribution as they are not needed: "ckeditor/samples"

We also install our vaadinsave plugin in addition to the CKEditor plugins shipped in the full package release. If you are compiling yourself, you will need to install CKEditor code into your project as we do not check in the CKEditor code in our source code system.

## GIT Versions/Branches
GIT should have a few branches, with 'master' being the main line latest greatest release.  Branch VAADIN6 contains the version last built for Vaadin 6.  The VAADIN7-fromV6 was a temporary branch for building a Vaadin 7 version based on the Vaadin 6 version.  VAADIN7 is the branch for just Vaadin 7.  

## SVN History from Google Code
We used two SVN branches as of May 2013 to handle the port to Vaadin 7. That created branches named VAADIN6 and VAADIN7 that each contain the VaadinCKEditor Eclipse project code.  The VAADIN7 branch was merged back to the 'trunk' in March 2015.

The older VAADIN6 branch version was developed using Vaadin 6.8.10 and CKEditor 4.1.1 in an Eclipse environment.  You simply can drop the JAR file into your Vaadin WEB-INF/lib, compile widgetsets and then you can begin using it.  No work has been done on this branch since 2013.

**Because Google has removed Downloads from Google Code in 2014 (on its way to its eventual demise!), please visit the [Vaadin Directory to download the JAR](http://vaadin.com/addon/ckeditor-wrapper-for-vaadin) as of version 7.8.9.**

The current Vaadin 7 version is developed using Vaadin 7.7.16 and CKEditor 4.11.3 in an Eclipse environment.  You simply can drop the JAR file into your Vaadin WEB-INF/lib, compile widgetsets and then you can begin using it.

NOTE: This widget is compiled using JDK 1.6 / Java 6. But we only deploy using Java 8.

It was built for use in the [Open eSignForms](https://open.esignforms.com/) open source electronic contracting and electronic signature web-based application (SaaS) where forms can be developed for [electronic signatures](https://www.yozons.com/ElectronicSignatures/), routing, etc.

**NOTE:** *All code contributed to this project will be bundled under the single copyright owner, Yozons Inc., but of course it's released under Apache 2.0 so you are free to do with the code as you please.*

**VAADIN 8**  [Another project has forked our code and taken over CKEditor maintenance for Vaadin 8.](https://github.com/alump/CKEditor)

(Automatically exported from code.google.com/p/vaadin-ckeditor on 3/19/2015)
