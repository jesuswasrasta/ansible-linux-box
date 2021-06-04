# Linux Machine Setup

This repository contains scripts to set up my Linux box.   
They have been tested with KDE Neon (Ubuntu x64).  

Shell customization assumes you're using `bash`.   
GUI shell customization assumes you're using KDE.   

## Ackowledgements 
I originally forked this repo:  [Ansible Dev PC](https://github.com/bradwilson/ansible-dev-pc).   
Then I realized I was customizing it too much, so I decided to build a brand new repo.   
I want to thank [Brad Wilson](https://github.com/bradwilson)  for his repo, it helped me a lot.   

## Please fork this and customize it

The purpose here is to document what I use for my personal Linux box. You will likely want to make changes to my customizations, including adding/removing software, choosing different defaults, etc. While you can make those changes locally, if you plan to use these scripts long-term, it will likely be more beneficial for you if you fork this project so you can preserve your changes and easily merge newer versions of these scripts.

## Pre-Requisites

### Linux

1. Make sure you're up to date:

   ~~~bash
   $ sudo apt update
   $ sudo apt -y full-upgrade
   ~~~

2. Install pre-requisites:
   ~~~bash
   $ sudo apt -y install git
   $ sudo apt -y install ansible
   ~~~

## Running

Before running the scripts, please review `_all.yaml` and `_all_no_customization.yaml`, and comment out software you don't want installed. In particular, most folders contain `customization.yaml` files which tend to contain my personal opinions on customizations; feel free to comment out sections of those files, or ignore them entirely.

To run the setup:

~~~bash
$ ansible-playbook -K _all.yaml
~~~

You will be prompted for your password, so that administrative-level software can be installed. _**You must be a sudoer to run these scripts, otherwise the installation process will fail.**_ You can also run individual files if you'd prefer to take more control over what's executed.

Since core OS packages are upgraded, it is safest to reboot the PC/VM after running these scripts. At a bare minimum, many UI shell customizations done here will require you to log out and log back in.

## Notes on differences between Linux distros

In general, these scripts are optimized around the experience of users of Ubuntu desktop distributions. These scripts install GUI-based applications, and manipulate the GUI shell for development purposes. They will probably most work on a server-based distribution if that's what you use for development, though they will require significant reworking.


### Third party notices

Portions copyright (c) Microsoft Corporation, licensed [under the MIT license](https://github.com/microsoft/vscode/blob/afd102cbd2e17305a510701d7fd963ec2528e4ea/LICENSE.txt).
