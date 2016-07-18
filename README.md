Please Note:

Before doing any change, please configure your username and email address with git. Any unknown changes will be deleted.

Development Environment Setup

Prerequsites

Install 64 bit versions of Eclipse IDE for Jave EE and Java JDK 7.

Intall Git and eGit (see details below)

Install Eclipse M2Eclipse plugin (Mandatory!).

Configure Maven web proxy (see section below)
Install Eclipse TestNG plugin (Optional!).

Details on Setting up Git and eGit

mporting Projects

Note: If you have followed all the steps above (including the link to the HPRS setup) then you now should have the project appearing in Eclipse.

Alternatively the following is just a basic summary of how to import a project. It assumes you already have Git, Eclipse (incl. required plugins) and Java already installed.

Steps to import a project:

Delete previous non-Maven project

Note: Don't delete contents though!
Import Maven projects into Eclipe

Choose: Import...->Maven -> Existing Maven Projects
Click Next
Browse to Test Automation Git project
Choose: /Automation Framework/pom.xml
Click Finish
The project should now be in your Eclipse Project Explorer.

You shouldn't need to mess with the classpath. If there are compilation errors then it is either that somebody has forgotten to check in a java file or update the POM dependencies.

Note: Maven builds the project in the "target" dir so you may need to delete the "bin" if it exists.

Troubleshooting

(1) I'm seeing "org.apache.maven.plugin.PluginResolutionException"s in the Eclipse error log.

Resolution: If the the Maven web proxy isn’t configured the first time you import a Maven project into Eclipse the M2Eclipse plugin fails to download any project dependencies or Maven plugins and you will get errors like this and there will be a red X annotation on the pom.xml in your project in Eclipse.

If this happens please verfiy the correct Maven web proxy is configured as specified above then do the following:

Restart Eclipse
Right click on your project and choose Maven->Update Project
Check the "Force Update of Snapshots/Releases" box
Click OK
Maven should now be able to download all dependencies and plugins and the red X on the pom.xml should go away after a few minutes.
