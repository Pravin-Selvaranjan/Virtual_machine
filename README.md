# __Virtualisation install guide - Ruby - Virtualbox - Vagrant__

(image)

## Please read all the instructions thoroughly and carefully


- Step 1 Ruby

Install [Ruby](https://github.com/oneclick/rubyinstaller2/releases/download/RubyInstaller-2.6.6-1/rubyinstaller-devkit-2.6.6-1-x64.exe)

This link will take you directly to the download (you will see it in your downloads folder immediately)

Once installed in your terminal check the version by typing
 ```Ruby --version```



- Step 2 Vagrant

Install [Vagrant](https://www.vagrantup.com/)

This link will take you to the Vagrant website, according to you machine specs install the relevant package.

Once you have Vagrant installed, you can check the version by using `vagrant --version`

You can also input `vagrant` and a list of cmds should be returned 


- Step 3 - Virtual Box

Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

This link will take you to the Oracle website where you can download and install the relevant version for your machine

We won't actually use VirtualBox directly. Vagrant will handle everything.

NOTE: Windows user, after installing Virtual Box, you will need to manually install the drivers:

## If you cannot see the vboxdrv.inf file ignore the steps in italics

- _In File Explorer, navigate to C:\Program Files\Oracle\VirtualBox\drivers\vboxdrv_
- _Right click on the VBoxDrv.inf Setup Information file and and select Install
When it's finished installing, open up a new terminal window and run sc start vboxdrv_
- Press the Windows Key and search for Control Panel, go from there to Network and Internet, then Network and Sharing Centre, then Change Adapter Settings.
- Right click on VirtualBox Host-Only Network and choose Properties
- Click on Install => Service
- Under Manufacturer choose Oracle Corporation and under Network Service, choose VirtualBox NDIS6 Bridged Networking driver
- This should install all the drivers you need to run Virtual Box on Windows.



# Final steps and prep

- Once you are confident that all the above steps have been installed correctly we need to run a few vagrants steps
- mkdir a new folder
- within this folder create a vagrant file `nano Vagrantfile`
- once in the file insert the following block of code (copy and paste)
```[12:23] Abdul Haseeb Shahrukh Khan
vagrant
Vagrant.configure("2") do |config|

 config.vm.box = "ubuntu/xenial64" # Linux - ubuntu 16.04
# creating a virtual machine ubuntu 

 

end

```
- save the file using `ctrl + x` and select yes 
- once out of the file you can use `cat Vagrantfile` to see if the contents is correct
- You then must run `vagrant up`

(image)

- Once that process has completed your virtual environment should be setup for use
- You can check this by running `vagrant status`

(image)

- Whilst in the correct pathway run `vagrant ssh` to enter your virtual environment and utilise the below cmds to navigate the environment.




# What is Dev Env & Benefits 
## Vagrant, Virtualbox, and Virtualisation.

- How can we find out the version of the virtual machine that we have created 
- OS `uname` or `uname-a`

- How to create a file in Linux
- ` touch filename` 
- or `nano filename`
- How to check existing file/folders `ls` or `ls -a`
- How to create a folder `mkdir foldername`
- How to navigate inside the folder `cd foldername`
- How to come out of the folder or 1 step back `cd ..`
- How can we check our current location/Where am i `pwd`
- `Whoami `
- How to copy file ` cp filename destination`
-  ` cp filename_with_absolute_path destination_with_absolute_path`

- How to remove file `rm -rf file/folder_name`
-  How to cut paste the file/ move the test file inside linux_commands folder `mv test linux_commands`
- How to check all processes `top` and `ps aux`
- find out how to remove /delete /kill processes
- how to use root user `sudo su` or `sudo i`
-  how to use `|` pipe
- how to check file permission `ll`
- change file permission `chmod permission filenanme`
- - `r` or `w` or `rw` or `all` also numbers `400` or `600` for all `700`

- update our ubuntu OS `apt-get update`
- upgrade our ubuntu OS `apt-get upgrade` or `apt-get upgrade -y`
  
- how to create automate tasks with provisioning scripts 
- automate update and upgrade
- run provision.sh `./provision.sh`

- How to kill a process `SIGKILL`
- How to change file name in linux `mv (option) filename1.ext filename2.ext`