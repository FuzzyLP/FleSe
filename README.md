List of contributions:

 - [Dan's contributions](README_Dan.md)

# Installation Guide

## Instructions for Ubuntu virtual machine installation

1. Install VirtualBox 5.0 - https://www.virtualbox.org/

   The version is not entirely compatible with Windows 10.

2. Download Ubuntu ISO - http://www.ubuntu.com/

   Choose the last stable version: Ubuntu 14.04.02 LTS (996 Mo)

3. Create your virtual machine with VirtualBox:

   - Run the Software
   - Create a new virtual machine following the wizard
   - Choose wisely the size of the RAM and the hard disk
   - In the machine configuration, in the Storage tab, under the
     controler IDE, add the location of the Ubuntu ISO file. The
     virtual machine will boot on the virtual ISO.
   - Launch the machine and follow the Ubuntu wizard instructions

4. Remove the Ubuntu ISO from the virtual machine configuration:

   - In the machine configuration, in the Storage tab, under the
     controler IDE, remove the location of the Ubuntu ISO file.

5. Optional: the size of the screen does not fit?

   5.1. Download VirtualBox Guest Additions -  http://download.virtualbox.com :
    - Choose the VirtualBox version in the list
    - Download the file `VBoxGuestAdditions.*.iso`

   5.2. Add the ISO file to the virtual machine
    - Browse the virtual machine configuration
    - In the Storage tab, under the controler IDE, add the location of
      the VirtualBox Guest Additions ISO file.

   5.3. Launch the virtual machine
   5.4. Install the ISO launching the wizard (in the left bar)
   5.5. Restart the machine

   5.6. Remove the VirtualBox Guest Additions ISO from the virtual
   machine configuration.
     - In the machine configuration, in the Storage tab, under the
       controler IDE, remove the location of the ISO file.

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

 - Next part, the soft links is optional. Make a soft link from `"CIAOINSTALLDIR"/library/` to `negation_and_fuzzy_logic/`
```
# Remove old versions included in Ciao Prolog package
rm -fR /usr/lib/ciao/ciao-1.15/
# Link to the latest version.
ln -s ~/negation_and_fuzzy_logic/
```

 7. Add `servlet-api.jar` to the project - http://www.java2s.com/Code/Jar/s/Downloadservletapijar.htm (drag and drop works well)

 8. Change the Java compiler to 7 (optional) 
  - In the Project menu, Properties
  - Java compiler tab
  - Choose Java 7 

 9. Add the Tomcat server
 - In the window menu, switch to the Web perspective
 - In the Server tab, add a new server following the wizard. Give the path of the Server's folder

 10. Run FleSe. The URL adress of the server is http://localhost:8080/flese/
