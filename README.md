Charlie Sheen Persona Jenkins (Hudson) Plugin
=============================================

Chuck Norris sucks.  Charlie Sheen is king now.  

This plugin gives your Jenkins or Hudson CI server the full winning
power of the original Vatican Assassin Warlock - Charlie Sheen.

The plugin is built using the generic Persona plugin from
the Jenkins team:  https://github.com/jenkinsci/persona-plugin

Installation
------------

* Download the charliesheen.hpi file
* Connect to your Hudson/Jenkins CI server, browse to:
  Manage Hudson > Manage Plugins > Advanced > Upload Plugin
* Boom. Winning.

Configuring
-----------

When you create a job or edit a job, in the "Post-Build Steps"
section you will see an option to "Associate Persona".  Check
this box and choose 'Charlie Sheen' from the drop-down.

Issues, Support, Patches, Quotes and Image submissions
----------------------------------------------------

Please use the Issues section on the github page to submit
any issues, patches, quotes, images, etc.

    https://github.com/joemiller/charliesheen-jenkins-plugin/issues

I could especially use some additional quotes.  Please make
sure the quotes are around 100-140 characters, otherwise
they will wrap and look funky.


How to package your own custom Persona plugin into an .hpi
----------------------------------------------------------

Pre-reqs:
    
* a github account
* maven2 installed on your build machine

Process:

1. Fork the persona-plugin.git repo on github:  https://github.com/jenkinsci/persona-plugin
    
2. Rename your fork by clicking on the Admin button in the github interface.  
   I renamed my fork to "charliesheen-jenkins-plugin"

3. Clone your new repo and edit the pom.xml file.  You probably want 
   to change at least the following:

         <artifactId>
         <name>
         <url>
         Add yourself to the <developers> list
         under <scm> section, modify url's to point to your github repo
         
4. Create a directory to hold your static resources.  Files in this 
   directory will be placed at the top of the .hpi file when you
   build the project which is important.

        $ mkdir src/main/webapp
    
5.  Create your persona.xml, failure.jpg, icon.jpg, other.jpg,
    success.jpg files in src/main/webapp

6.  Build and run Jenkins with your plugin loaded.

        $ mvn hpi:run
        
7. Browse to http://localhost:8080.  If the build was successful, you
   will have a running instance of Jenkins with your plugin loaded.
   
   Create a New Job.  Name it and choose 'free-style software project'. 
   In the Post-Build section there should be an option to Associate Persona
   with your Persona loaded.
   
9. To create an .hpi file run 'mvn package'.  The .hpi file will be in the target/ directory.
   
10. Add your files, commit to github, and share your persona =) 