---
title: "Quickstart"
weight: 2
date: 2018-09-18T23:04:02-07:00
draft: true
---

In this section we give a brief overview of the absolute basics 
starting with how to connect to NERSC and concluding with running 
a first DFT calculation on NERSC.

## Connecting to NERSC
To login to the cori system on NERSC, simpy open a terminal and type 

    ssh username@cori.nersc.gov

after providing your password, you will be connected to a login node 
on the cori system. To connect edison simply replace cori with edison.

## Navigating the file system
Both the cori and edison systems have four different file systems:

 * Home
 * Local Scratch
 * Project
 * Global Scratch

Every time you log in, you are automatically taken to your home directory.
This can be confirmed with the following commands:

    pwd
    echo $HOME

The home directory is a global directory in the sense that it is shared by all
NERSC systems (ie both cori and edison). This directory is designed primarily for 
storing source code and compiling executables. This is not the place 
to run heavy duty first principles applications. If you do so you will find the I/O is 
very slow and will quickly run out of room, as each user is only alotted 40 GB in their home
directory. 

The best place to setup and run applications is the local scratch. To navigate to your local 
scratch type:

    cd $SCRATCH

The scratch is optimized for I/O and each user is alotted 10TB of space making the local
scratch ideal for handling large _temporary_ files. I emphasize temporary here because  
the scratch directories are purged every 2-3 months. 
## Loading packages

## Transfering between NERSC and a local machine
At times it will be important to transfer files between NERSC and 
your local machine (laptop). The simplest way to do so is with the 
scp command.

To transfer from your 

## Running a first job
