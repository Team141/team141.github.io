---
title: Bash Scripting
author:
  name: Team141
  link: https://github.com/Team141
date: 2022-02-18 11:33:00 +0530
categories: [Bash scripting, Linux]
tags: [Bash scripts]
math: true
mermaid: true
pin: false
---

## Code block

---

### Today's Assignment

>Single *BASH Script* for Webserver launch in **CENTOS** and **UBUNTU**

### Type-2
```bash
#!/bin/bash

# Variable Declaration
echo
webtemplate=https://templatemo.com/tm-zip-files-2020/templatemo_520_highway.zip
webpage=templatemo_520_highway

# Condition to test whether it is Centos or Ubuntu
echo
sudo apt --help

if [ $? -eq 0 ]
then
	echo "############### UBUNTU MACHINE ################"
	pkgmanage=apt
	pkgname=apache2
else
	echo "############### CENTOS MACHINE ################"
	pkgmanage=yum
	pkgname=httpd
fi

# Package installation and starting webhost service
echo
sudo $pkgmanage update -y > /dev/null
sudo $pkgmanage install $pkgname wget unzip figlet -y > /dev/null
sudo systemctl start $pkgname
sudo systemctl enable $pkgname
sudo ss -tunlp | grep $pkgname
sudo mkdir -p /tmp/webfile
     cd /tmp/webfile
sudo wget $webtemplate
sudo rm -rf $webpage.zip.*
sudo unzip -oq $webpage.zip
sudo cp -r $webpage/* /var/www/html/ > /dev/null
sudo systemctl restart $pkgname
sudo ss -tunlp | grep $pkgname

# Acknowledging installation
echo
echo "###############################"
figlet Done
echo "###############################"
```
{: .nolineno}

---

### Type-1

```bash
#!/bin/bash

sudo apt --help

if [ $? -eq 0 ]
then


echo "########    UBUNTU MACHINE       #######"

sudo apt update -y
sudo apt install apache2 wget unzip -y
sudo systemctl start apache2
sudo systemctl enable apache2
mkdir -p /tmp/webfile
cd /tmp/webfile
wget https://templatemo.com/tm-zip-files-2020/templatemo_520_highway.zip
rm -rf templatemo_520_highway.zip.*
unzip -o templatemo_520_highway.zip
cp -r templatemo_520_highway/* /var/www/html/
sudo systemctl restart apache2


else

echo "########    CENTOS MACHINE       #######"

sudo yum update -y
sudo yum install httpd wget unzip -y
sudo systemctl start httpd
sudo systemctl enable httpd
mkdir -p /tmp/webfile
cd /tmp/webfile
wget https://templatemo.com/tm-zip-files-2020/templatemo_520_highway.zip
rm -rf templatemo_520_highway.zip.*
unzip -o templatemo_520_highway.zip
cp -r templatemo_520_highway/* /var/www/html/
sudo systemctl restart httpd

fi
```
{: .nolineno}

---

#### Shell Example

```bash
#!/bin/bash

### Little fashion app setup ###

# Variable declaration
PACKAGE="apache2 wget unzip"
SVC=apache2
ARTURL='https://www.tooplate.com/zip-templates/2127_little_fashion.zip'
ARTDIR=2127_little_fashion
TEMPDIR='/tmp/webtempfiles'

# Installing Dependencies
echo
echo "#####################"
echo "Installing Packages"
echo "#####################"
sudo apt update > /dev/null
sudo apt install $PACKAGE -y > /dev/null

# Start & Enable apache2
echo
echo "#####################"
echo "Starting Service."
echo "#####################"
sudo systemctl start $SVC
sudo systemctl enable $SVC

# Deploy app
echo
echo "#####################"
echo "Deploying Web App."
echo "#####################"
mkdir -p $TEMPDIR
cd $TEMPDIR
wget $1 > /dev/null
unzip $2.zip > /dev/null
sudo cp -r $2/* /var/www/html/

# Bouncing service
echo
echo "#####################"
echo "Bouncing Service"
echo "#####################"
sudo systemctl restart $SVC


sudo systemctl status $SVC
# Cleanup
echo
echo "#####################"
echo "Clean Resedual files"
echo "#####################"
rm -rf $TEMPDIR
```
{: .nolineno}


