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

### Specific Languages

#### Shell

```bash
#!/bin/bash

### Little fashion app setup ###

# Variable declaration
PACKAGE="apache2 wget unzip"
SVC=apache2
ARTURL='https://www.tooplate.com/zip-templates/2127_little_fashion.zip&#39;
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
