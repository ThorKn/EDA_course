---
title: "Chapter 01 Training"
author: "Course authors (Git file)"
aspectratio: 169
theme: "CambridgeUS"
colortheme: "rose"
fonttheme: "professionalfonts"
urlcolor: red
linkstyle: bold
logo: icons/common.jpg
date:
section-titles: false
toc: true
---

# Chapter 01 - Server, Login, Shell - TRAINING - Common

## Server and user credentials

The PC environment for the course will be provied by IHP.

- Your PC in front of you must be connected to a server
- You will then work in a Ubuntu 24 Linux system
- The desktop GUI will be Gnome

### Connect to the IHP server

##### Follow these steps:

1. Open ThinLinc on the host PC (Windows?)
2. Go to the Options and set "Fullscreen on this monitor"
3. Connect with the login data, given to you by IHP
4. Ubuntu with Gnome desktop should start in ThinLinc

##### For Log out:

1. Just "Log out". Don't Power Off.
2. This will take you back to the host system.

##### Notice:

- Please ask if there is questions!
- We`ll try to do this for all participants first, before proceeding to the next steps of the training.

## GNOME desktop: First lookaround

### Search, start and close programs

##### Create and save a textfile:

1. Search for a texteditor (gedit)
2. Open gedit
3. Write a litte (your name or anything else)
4. Save the textfile with a name and the suffix .txt
5. To a new dirctory: Documents/myfiles
6. Close the texteditor (gedit)

### Tab-switching between programs

##### Tab-switch between opened programs:

1. Search and open at least three different programs (office, gedit, document viewer?)
2. Tab between the programs (with ALT+TAB on the keyboard)
3. It is a circle. After three Tabs you should be at the first again.
4. Close all programs

## The course data

### Download and unpack

#### Get the course data

- Get the latest release download package:

[https://github.com/OS-EDA/Course/releases](https://github.com/OS-EDA/Course/releases)

- Create a directory for the course slides.
- In Linux the ~/Documents is a good place to create the directory. Maybe create the directory Documents/course
- Unpack the course into this directory.

### Look around in the course data

![Course directory structure](pics_lecture/coursed_repo_structure.png)

### The chapters and slides

You will find the slides in the ```build``` dirctory.

- If sorted alphabetical, it makes most sense.
- C0X is the chapter number.
- In each chapter:
    * Start with the lecture
    * Cheasheet (if available) is a single slide
    * Trainnings in the order commcon, advanced and bonus
    * Questions are for the next day (mornings)

##### Task:

- Examine the ```build``` directory. 
- Open and close some of the pdf files.
- Become comfortable with the course structure.

### Links from the slides

#####
This might be outdated for the course, please try yourself.

- An issue with the linux document viewer and snap browsers.
- Links from slides don't open in the browser.

Possible workaround:

- Right click the link and copy
- Open browser
- Paste link to URL line

### Workspace arrangement

Suggestions or Options:

- Arrange windows next to each other
- ALT+TAB between programs (tasks)
- Close unwanted windows after the completion of a chapter

## Linux shell

### Short commandl ist of a linux shell

- ```ls``` (list content of directory)
- ```ls -al``` (list with option for more information)
- ```cd``` directoryname (change to directory)
- ```cd ..``` (change to upper directory)
- ```mkdir``` (make directory)
- ```touch``` (make file)
- ```mv``` (move)
- ```cp``` (copy)
- ```nano``` (opens the nano file editor)

### Man pages

If unsure how to use a command, read the man-page:

```
man <command>
```

##### Task:

- Open the man pages of all the commands in the above list (last slide)
- Find the syntax for the commands (it is given on the top of the man page)
- What are ```OPTION```, ```SOURCE``` and ```DEST``` ? 
- Find the definition of the option ```-al``` for the command ```ls```

## IMPORTANT Tasks

To get ready for working with the open-source EDA tools, you must run (execute) a shell script in your shell terminal.

**This is aboslutly neccessary for the rest of the course**

There are two options to do this:

1. Every time you open a shell and want to work with the tools
2. Once in the bashrc 

### Option 1: Source every time in the shell

##### Task: Setup the linux tool environment 

- Open a shell terminal
- Run ```source /eda/or2/env.sh```
- Do this every time you open a new shell.
- It doesn't hurt of you do it multiple times. Nothing breaks.
- It will lead to strange behaviour and no results if it is not done.

##### 

You should get a message like ```copied flow directory``` or ```flow directory already there```

### Option 2: Source in the bashrc

##### Task: Modify .bashrc with source command

- Find the file ```.bashrc```:
    - Location: go to the users home directory ```cd ~```
    - Hidden files have a point as pre-fix in their name. List the files with ```ls -al```  
- Open the file ```.bashrc``` in a texteditor. ```nano .bashrc```
- At the bottom line, add the command ```source /eda/or2/env.sh```
- Save the file and close the editor
- In a shell terminal: reload bashrc with the command ```. ~/.bashrc```

##### 

You should get a message like ```copied flow directory``` or ```flow directory already there```

### Check the environment

- Check if the setup was successfull.
- **Don't continue if the following checks are errornous, but ask for help from the trainer**

##### Task: Check the environment
- Open a shell terminal
- Run ```source /eda/or2/env.sh```
- See if the tools are sourced (available) with getting their versions:
    * ```openroad -version``` should give your the version number
    * ```yosys --version``` should give you the version number
    * ```klayout -v``` should give you the version number

### Congratulations!

**Congratulations:**

**You have succesfully run some of the open-source EDA tools on a linux server.**

- You did run openroad, yosys and klayout.
- They did not do much, but giving you their version numbers.
- But it is the needed base for the rest of the course.

**You are on a good way**

### Linux Power settings

By default the screen goes black after 5 minutes of idle. Additionaly the screen locks and you have to enter your password again.

This is good and intended. But might be a little too annoying for the course.

##### Task: Disable screen black out

- Find the linux "power settings"
- Disable the "screen black after 5 mins" or higher the value.

## Flow directory

The last step (the important one) created a directory in your linux home directory:

- The ```flow``` directory

This is the most important directory for the course!

### Examine the flow directory

##### Task: Examine the flow directory

- Open a shell terminal
- Run ```source /eda/or2/env.sh```
- Navigate to the ```flow``` directory as you learned before
- List the content with ```ls -al```
- Find:
    * The ```Makefile```
    * The ```/flow/designs/src``` directory. What is inside?
    * The ```flow/designs/ihp-sg13g2``` directory. What is inside?

### The Makefile

##### Task: Open the Makefile

- Open the Makefile in a texteditor (with gedit)
- What is inside the Makefile?
- What could be the meaning of 
    * ```DESIGN_CONFIG=....```
    * ```#DESIGN_CONFIG=----```
- Close texteditor without changes in the Makefile

## Online shell resources

### Online shell tutorial

To learn some Linux shell, you should find a tutorial that matches good to you. 

I found this one simple and good to follow for me while learning Linux shell:

[https://community.linuxmint.com/tutorial/view/100](https://community.linuxmint.com/tutorial/view/100)

### Makefile

OpenROAD flow scripts use Makefiles. So you might want to learn some basics about Makefiles.

Again here is the tutorial that has helped me most:

[https://makefiletutorial.com/](https://makefiletutorial.com/)

### Tips and tricks

- shell: TAB for autocompletion
- shell: 2xTAB for all choices of autocompletion
- Open a new shell terminal with the mouse:
    * Right click on an empty space in the directory window
    * Choose "open in Terminal"

