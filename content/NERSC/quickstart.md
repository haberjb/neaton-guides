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

## Loading modules

NERSC comes with many of your favorite packages ready to load, 
no compiling required! NERSC does this with the help of the module utility.
The module utility manages the MANPATH andbasically tells the system where 
to look for executables. 

Lets do an example. We will begin by looking for the main
Quantum Espresso executable, pw.x (pw = plane wave).

Make sure you are logged in to a NERSC system and type:

    which pw.x

NERSC should tell you its looked a bunch of places but cant locate
pw.x. Now type:

    module load espresso
    which pw.x

The first line updates the manpath to point to a global quantum espresso
installation. The second line confirms that the system can now find 
pw.x. The module utility allows users to load, remove, list and, search
for different programs already compiled on NERSC. If you are new to the module,
utility, please take a look at the NERSC [documentation](http://www.nersc.gov/users/software/user-environment/modules/).

## Transfering files

At some point, you will need to transfer files between NERSC and 
your local machine (laptop). The simplest way to do so is with the 
scp command.

To transfer files from NERSC to your local machine

    scp username@dtn01.nersc.gov:/remote/path/myfile.txt /local/path

To transfer files to NERSC from your loacl machine

    scp /loca/path/myfile.txt user_name@dtn01.nersc.gov:/remote/path

Please note, both commands should be run from your local machine. You can read
more about these commands [here](http://www.nersc.gov/users/storage-and-file-systems/transferring-data/scp-sftp/)

## Hands On: Running a job
We will now put all the above steps to gether and, we walk through 
a very simple calculaton on NERSC. As our example, we will compute the 
ground state energy of bulk Silicon in Quantum Espresso. 

If you havent already, begin by logging in to edison and navigating to the 
scratch directory:

    ssh username@edison.nersc.gov
    cd $SCRATCH

Create a new director called silicon and navigate inside:

    mkdir silicon
    cd silicon

We now need to generate our Quantum Espresso input and upload an 
appropriate pseudopotential. 

{{%attachments style="orange" /%}}
