# __Virtualisation install guide - Ruby - Virtualbox - Vagrant__

![Blank diagram (1)](https://user-images.githubusercontent.com/110179866/184345227-e32ba37d-3edb-4e70-b2aa-df578318599e.jpeg)



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

<img width="328" alt="vagrant1 jpeg" src="https://user-images.githubusercontent.com/110179866/184190322-e3b68e60-6d0c-4ab8-9308-b54f5a1fd60a.png">


- Once that process has completed your virtual environment should be setup for use
- You can check this by running `vagrant status`

<img width="244" alt="vagrant2 jpeg" src="https://user-images.githubusercontent.com/110179866/184190367-476e292c-09fd-45dd-afdf-5d8104f51ad1.png">


- Whilst in the correct pathway run `vagrant ssh` to enter your virtual environment and utilise the below cmds to navigate the environment.


<img width="239" alt="vagrant3 jpeg" src="https://user-images.githubusercontent.com/110179866/184190446-a2b82dcb-256a-480c-9f8f-41c24c7198a7.png">





# What is Dev Env & Benefits 
## Vagrant, Virtualbox, and Virtualisation.

- How can we find out the version of the virtual machine that we have created 
- OS `uname` or `uname-a`

- How to create a file in Linux
- ` touch filename` 
- or `nano filename`
- How to check existing file/folders `ls` or `ls -a`
- How to create a folder `mkdir foldername`


<img width="164" alt="vagrant4 jpeg" src="https://user-images.githubusercontent.com/110179866/184190508-08254a0f-c4c1-4486-85bc-7bca521146b6.png">



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

<img width="218" alt="vagrant5 jpeg" src="https://user-images.githubusercontent.com/110179866/184190645-0a7c1b1e-86f3-4975-a74f-3d09a8d3101c.png">


- - `r` or `w` or `rw` or `all` also numbers `400` or `600` for all `700`

- update our ubuntu OS `apt-get update`
- upgrade our ubuntu OS `apt-get upgrade` or `apt-get upgrade -y`
  
- how to create automate tasks with provisioning scripts 
- automate update and upgrade
- run provision.sh `./provision.sh`

<img width="300" alt="vagrant6 jpeg" src="https://user-images.githubusercontent.com/110179866/184190716-22a96a6f-4e5d-4499-83ef-d642684f50d5.png">



- How to kill a process `SIGKILL`
- How to change file name in linux `mv (option) filename1.ext filename2.ext`
- Install nginx `sudo apt-get install nginx -y`
- How to check if it's installed or working `sudo systemctl status nginx`
- how to restart a process - in this case its an NGINX
- restart or start `sudo systemctl restart nginx` 
- enable the process `sudo systemctl enable ngninx`
- vagrant reload/destroy and re install nginx(or whatever) 



# Nodejs

- Time boxing - 1 day
- What are the dependencies 
- Which version of app/nodejs - NodeJs 6.4 or above
- Which environment can this be deployed - Linux ubuntu 16.04 or above
  

  ## Monolith Deployment
  #### Nodejs - backend tool
  ##### by default Nodejs works on port 3000
  - Q&A ` What are the features of this app`
  - `3 pages` 1 `sparta app page` 2 `fibonacii replacement` 3 `192.168.10.100:3000/posts` for mongodb
  - mongodb default port is `27017` and Mongodb allows you to access - `mongod.conf` you need to allow the required ip
  - what is nodejs - how to launch it
  - what are the dependencies - install nodejs -> required version of that `version 6.0 or above`
  - ` sudo apt-get install nodejs -y` centOS ` yum install nodejs -y`
  - Which env is needed in order for us to deploy this app
  - `linux ubuntu 16.04 or above
  

- Be sure the correct path is selected
- Sync our app folder from localhost to VM

<img width="398" alt="vagrant new" src="https://user-images.githubusercontent.com/110179866/184632986-44332183-6386-46b5-9290-61f4885100f4.png">



- `config.vm.synced_folder ".", "/home/vagrant/app"`
- sync data from localhost destination

- Once configured `vagrant reload` in the main folder where the vagrantfile is located
- Once in the VM double check that the correct folders are available

<img width="297" alt="vagrant new 2" src="https://user-images.githubusercontent.com/110179866/184635965-bde44ad7-fc13-46cf-8533-6783a574b5bd.png">




- Use rake spec in `test-code` folder to run the tests


<img width="297" alt="rake spec" src="https://user-images.githubusercontent.com/110179866/184651840-ef4407e9-2f15-404c-987f-41d526fb4f14.png">

- Install all relevant errors/failures
- Once all tests have successfully passed 
- Run `npm install` in VM
- then `npm start` in VM



<img width="299" alt="npm start" src="https://user-images.githubusercontent.com/110179866/184651855-71ed02dd-84a0-4369-9c15-c03bc60cc997.png">



