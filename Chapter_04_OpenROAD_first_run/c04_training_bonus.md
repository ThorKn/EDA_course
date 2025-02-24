---
title: "Chapter 04 Training"
author: "Course authors (Git file)"
aspectratio: 169
theme: "CambridgeUS"
colortheme: "rose"
fonttheme: "professionalfonts"
urlcolor: red
linkstyle: bold
logo: icons/bonus.jpg
date:
section-titles: false
toc: true
---

# Chapter 04 - OpenROAD first run - TRAINING - Bonus

## Create a new design

In this training session you will integrate a new design for using it with OpenROAD flowscripts.

You can either:

- Have your own design ready.
- Take an opensource design from someone else.

### Pick a design to integrate

##### Task: Choose a design

- LFSR from earlier?
- TinyTapeOut design? (See earlier Bonus Training)
- Write a new Verilog file with your own design idea.

### Create a new design in ORFS

##### Task: Insert a new design

- In the ```flow/designs/src``` directory: create new design
- Create or copy Verilog to there
- In the ```flow/designs/ihp-sg13g2``` directory: create a new design(same name as in src)
- Create or copy the ```config.mk``` and ```constraints.sdc``` from the gdc example to there
- Modify both files to match the Verilog src file and top module.

### Makefile

##### Task: Enable the design

- Navigate to the ```/flow``` folder
- Edit the Makefile:
    * Uncomment the line with your choosen DESIGN_CONFIG from ihp-sg13g2.
    In this case you must create a new line

        ```
        DESIGN_CONFIG=./designs/ihp-sg13g2/<your design>/config.mk
        ```
    
    * Re-comment the previous uncommented line with DESIGN_CONFIG.    
    * The line with the default design does not need to be commented. This only applies when no previous line with DESIGN_CONFIG is set.

### Run

##### Task: Run ORFS with the design

- Run ```make``` from inside the ```/flow``` folder.

### Success

- The choosen design should finish after a while and a lot of console output with a table (time/memory) like this:
```
Log                            Elapsed seconds Peak Memory/MB

``` 

CONGRATS! Your design got build to a GDS!

### The GDS

##### Task: Examine the GDS

- See the GDS with the command ```make gui_final```

##### Task: Save an image from the GDS

- In the TCL console at the bottom of the GUI:
    * ```save_image <imagename>.png```
    * Find the saved image in your directories.