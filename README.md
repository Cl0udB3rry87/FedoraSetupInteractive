# Fedora Setup Interactive


### Notice:  This project is currently under development and will change.  Until this notice disappears things will likely not work as expected.

## Project Task List
- [X] Finish Rough Draft of README.md - Project Information
- [ ] DNF Packages Intall - Scripted & Tested
- [ ] DNF Packages Remove - Scripted & Tested
- [ ] FlatPak's Install - Scripted & Tested
- [ ] Gnome Extensions Install - Scripted & Tested
- [ ] Network Shares Setup - Scripted & Tested
- [ ] OpenVPN Setup - Scripted & Tested
- [ ] Tailscale - Scripted & Tested
- [ ] .local/bin Script Copy - Scriped & Testedt
- [ ] Import Settings - Scripted & Tested
- [ ] Final Draft of README.md - Project Completion

## Project Overview

The Fedora Setup Interactive project is a post install script that simplies and automates the setup of the current version of Fedora (Fedora 42).  The script will provide the setup of the following:

- Install applications with the package manager (dnf).
- Remove any un-needed applications that are in the package manager.
- Install Nvidia drivers if needed.
- Install FlatPak applications.
- Install Gnome Extensions.
- Remove un-needed Gnome Extensions.
- Setup SMB network shares 
- Setup OpenVPN connections using profiles with username/password access.
- Setup Tailscale.
- Copy scripts to the /home/$USER/.local/bin folder.
- Import system settings.

The reason I created this script was to make setting up a new install of Fedora easier, faster, and a more pleasant experience.  Installing Fedora is simple and easy to do, but I found that after the install was done installing everything was a bit time consuming and I often forget to install things while doing so.  The script takes a lot of that away and you can add to your new system how ever you want (USB Drive, Network Share, Installation Media, etc).  I have also found that doing this keeps multiple system more in sync with each other.  If you only have one system thats fine, but I have a Desktop and a Laptop.  They are setup the same with only a few minor differences.  If I have to do a re-install for any reason I am able to update the script and get the fresh install how I want it.  I am sharing my project for anyone who may find a use for it.  You can comment (#) out any sections you do not need or simply remove them.  The script will work for other distros you will just need to update the package manager to match the distro.  FlatPak's are beautiful and nothing changes.


## How To Use
### Notice: This project is currently in development and will change.  These instructions are ahead of my code.  This notice will be removed when it is complete.

Before you start be sure to update your system.  I usually open software, go to the updates tab, refresh the page, and update everything.  The system will reboot and check for any further updates.

 1. I recommend cloning the script to the root of your local home directory.  The pwd should be,
 /home/$USER.
  2. There are several text files that you will need to add things to in order for the script to work.  They will all be covered below.  The format will be Text File - Instructions.
     - dnfpackages.txt - Add the names of the dnf packages you want to install to this file.  I put one package name per line.  If you do not know the name of the package doing a, dnf search *PackageName* in terminal can help.
     - dnfrmpackages.txt - Add the names of any packages that you want to remove in this file.  Just as the previous file just add one package name per line.
     - flatpaks.txt -  I find it best to go to flathub (https://flathub.org/), search for the application and copy the package name from the manual install.  For example Ghost Writers manual install is, *flatpak install flathub org.kde.ghostwriter*.  You would add, **org.kde.ghostwriter** to the file.  See picture below for reference. ![flathub](https://github.com/Cl0udB3rry87/FedoraSetupInteractive/blob/main/READMEfiles/FlatHub.png)  Just one name per line.
 3. GnomeExtension - Will update, currently a work in progress.
 4. Network Share Setup
     -  NetworkDirectories.txt - Add the name(s) of your network directories to the file.  Just one name per line.
     -  networkshares.txt -  Add the information for your network shares.  This is usually found in /etc/fstab.  I have 3 SMB shares that I use and they are all formated like the following: //*serverIP*/*ShareName*/ /home/*username*/*FolderName*/ cifs username=*username*,password=*password*,noperm,_netdev 0 0
5. OpenVPN Profiles
6. Tailscale Setup
7. Scripts for /home/$USER/.local/bin folder
8. Import Settings


## Requirements

- Installation of Fedora 42 - Includes packages needed for most of the script.
-  Tailscale - Can be installed with other DNF Packages section of script.



## Credits/Influences

There are a few people who I give credit to for motivating me to work on this project.  I have never interacted with them directly but the information, thoughts, and knowledge that they have shared has led me to here.

- Jorge Castro - [Project BlueFin](https://projectbluefin.io/) & [Jorge Castro Website](https://www.ypsidanger.com/)  Project BlueFin is a project/build, not a distro.  It is his build of Linux that he uses everyday.  I tried it out and decided that it was not for me, but it did change how I use Linux and I have not looked back.  Thank you Jorge!
- Louis Rossmann - [Louis Rossmann linktr.ee](https://linktr.ee/louisrossmann) I have watched his YouTube videos for years.  We have a lot in common.  The highlights are the importance of Open Source Software.  The importance of not only being able to repair your devices, but to be able to own them as well.  They should not own you and the software you use should not be data mining everything you do to sell it to anyone who wants to pay for it.
- Seuros - [Seuros Blog](https://www.seuros.com/blog/)  I found his blog recently and enjoyed reading the tales about being an OSS Dev, his AWS account issues, and his other posts on the current state of Tech.  Every post I have read so far I have been able to relate to in some way and makes me feel like I am not alone when I encounter certain scenarios.  We do not hear about the horror stories enough!  Through his blog I have found inspiration to do this project and grow from their with future projects.

## Future Developments - Post Completion
GUI Version of the Install?


## License

GPL-3.0 license
See LICENSE file