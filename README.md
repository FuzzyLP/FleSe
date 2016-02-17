# Documentation of Dan's contribution into FleSe project

## Possibility of sharing (or not sharing) a file

Before this update, each file imported into FleSe was shared with
everyone else. I added the possibility for the user to change that,
using User Options. 

Every file has a Java sharing attribute. This attribute is updated via
an Javascript Ajax request.

## Median algorithm for fuzzifications

The fuzzications values of a new user is calculated following a median
function applied on the existing personalized values of the
app. Contents in Fuzzification algorithms.

## Preventing the owner of the file to modify the fuzzifications of a personalized file

So that the personalization of the users is one of the main axis of
FleSe. Impossible modification if one user personalized it but still
the owner can see all personalization.

## Configuration properties file `config.properties`

The file contains the following variables that can change from one machine to another:

 - Paths of `programFiles`
 - Paths of `plserver`

The file contains 2 or more locations for plserver so it will test the
first one, and if fails takes the second one and etc. So it is
possible to enter the more probable locations into the configuration
file to cover up a maximum range of configuration.

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
    - In the Storage tab, under the controler IDE, add the location of the VirtualBox Guest Additions ISO file.

   5.3. **Launch the virtual machine**
   5.4. **Install the ISO launching the wizard** (in the left bar)
   5.5. **Restart the machine**

   5.6. **Remove the VirtualBox Guest Additions ISO from the virtual machine configuration.**

        In the machine configuration, in the Storage tab, under the
        controler IDE, remove the location of the ISO file.

## Instructions for Ciao - Emacs installation

1. Open Ubuntu Software Center
2. Look for Emacs and install it
3. Install CiaoDE (or Ciao) in Ubuntu Software Center

   Emacs is automatically open Ciao perspective. 
   If not, add the following line in the .emacs file of your system:
```elisp
   (load <CIAOLIBDIR>/ciao-mode-init)
```

## Instructions for Flese Installation

1. Install Ciao special version
  1.1. Open /etc/apt/sources.list file
  1.2. Add the following lines:

```
deb http://babel.ls.fi.upm.es/~ ./ 
deb-src http://babel.ls.fi.upm.es/~ ./ 
```

  1.3. Open the console
  1.4. Type the following lines
```sh
apt-get update
apt-get install ciao-prolog
```

2. Download Rfuzzy tar.gz - http://babel.ls.fi.upm.es/~

 - Download the last package
 - Unzip the package and move it to the folder "CIAOINSTALLDIR"/library/
   "CIAOINSTALLDIR" is the installation folder of ciao. It could be /usr/ib/ciao/ciao-1.15
    You need to have the administrator rights

3. Check for Java installation

 - Open a terminal
 - Type java: The Java manual should be displayed. If not, Java is not installed. Follow the next instructions:

3.1. (Optional) Install Java
 - Open Ubuntu Software Center
 - Look for Java 7 (or 8) and install it

4. Download Flese tar.gz - http://babel.ls.fi.upm.es/~

   Download and unzip Flese last version.

5. Download Tomcat Server 7 tar.gz - https://tomcat.apache.org/

   Download and unzip Tomcat Server 7.

6. Install Eclipse Mars and do the setup

6.1. Download Java IDE for Java EE and unzip it - https://eclipse.org/downloads/
(The updated version of Eclipse on the Ubuntu Software Center is not available)
Install Java IDE for Java EE Developers manually (64 bits)

6.2. Run Eclipse and install the Webtools
 - right click on the executable, run
 - Specify Eclipse workspace. It must contains the Flese files.
 - In Help tab, click on install new Software
 - Choose the source Mars
 - Download all of category Web, XML, Java EE, and OSGi development
 - Ignore packages with errors

6.3 Import Flese project
 - Either you can get the package by downloading the full FleSe package at :
   or you can get the lastest version and stay updated with git.

 - FleSe Zip package version:
   from github at https://github.com/vpablos/
   or from server at http://babel.ls.fi.upm.es/~ (take the latest version)

 - Git version:
   Install git with 
```
apt-get install git-core
git clone http://babel.ls.fi.upm.es/
```

Next part, the soft links is optional:

Make a soft link from `"CIAOINSTALLDIR"/library/` to `negation_and_fuzzy_logic/`

```
# Remove old versions included in Ciao Prolog package
rm -fR /usr/ib/ciao/ciao-1.15/
# Link to the latest version.
ln -s ~/negation_and_fuzzy_logic/
```

6.4. Add servlet-api.jar to the project - http://www.java2s.com/Code/ervletapijar.htm (drag and drop works well)

6.5. Change the java compiler to 7 (optional) 
 - In the Project menu, Properties
 - Java compiler tab
 - Choose Java 7 

6.6. Add the Tomcat server
 - In the window menu, switch to the Web perspective
 - In the Server tab, add a new server following the wizard. Give the path of the Server's folder

6.7. Run Flese
 The IP adress of the server is http://localhost:8080/flese/
