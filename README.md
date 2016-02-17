List of contributions:

 - [Dan's contributions](README_Dan.md)

# Installation Guide

Look at [INSTALL_VM](INSTALL_VM.md) for instructions for Ubuntu
virtual machine installation.

## Ciao (and emacs) Installation

 - Install git with:
```
apt-get install git-core
```

 - Follow Ciao's
   [INSTALLATION](https://github.com/ciao-lang/ciao/blob/master/INSTALLATION)
   for Ubuntu.

## Instructions for FleSe Installation

 1. Clone [FleSe](https://github.com/FuzzyLP/FleSe) repository

 2. Clone [RFuzzy](https://github.com/FuzzyLP/RFuzzy) into `<CIAOINSTALLDIR>/library/`.

   `<CIAOINSTALLDIR>` is the installation folder of Ciao. It could be
   `/usr/lib/ciao/ciao-1.15`. You may need administrator rights.

 3. Check for Java installation

   - Open a terminal
   - Type `java`: The Java manual should be displayed. If not, Java is not installed. Follow the next instructions:

      - Open Ubuntu Software Center
      - Look for Java 7 (or 8) and install it

 4. Download and unzip Tomcat Server 7 tar.gz - https://tomcat.apache.org/

 5. Install Eclipse Mars and do the setup

   - Download Java IDE for Java EE and unzip it -
     https://eclipse.org/downloads/ (The updated version of Eclipse on
     the Ubuntu Software Center is not available) Install Java IDE for
     Java EE Developers manually (64 bits)

   - Run Eclipse and install the Webtools
     - right click on the executable, run
     - Specify Eclipse workspace. It must contains the FleSe files.
     - In Help tab, click on install new Software
     - Choose the source Mars
     - Download all of category Web, XML, Java EE, and OSGi development
     - Ignore packages with errors

 6. Import FleSe project

 7. Next part, the soft links is **optional**. Make a soft link from `<CIAOINSTALLDIR>/library/` to `negation_and_fuzzy_logic/`
```
# Remove old versions included in Ciao Prolog package
rm -fR /usr/lib/ciao/ciao-1.15/
# Link to the latest version.
ln -s ~/negation_and_fuzzy_logic/
```

 8. Add `servlet-api.jar` to the project - http://www.java2s.com/Code/Jar/s/Downloadservletapijar.htm (drag and drop works well)

 9. Change the Java compiler to 7 (optional) 
  - In the Project menu, Properties
  - Java compiler tab
  - Choose Java 7 

 10. Add the Tomcat server
  - In the window menu, switch to the Web perspective
  - In the Server tab, add a new server following the wizard. Give the path of the Server's folder

 11. Run FleSe. The URL adress of the server is http://localhost:8080/flese/
