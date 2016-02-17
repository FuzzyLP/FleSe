# Instructions for Ubuntu virtual machine installation

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
