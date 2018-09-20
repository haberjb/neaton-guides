---
title: "Share"
date: 2018-09-18T23:04:30-07:00
weight: 6
draft: true
---

As you work on your projects and collaborate with others in the group,
(and beyond), you will likely need to share files, scripts, executables
etc... There are a couple options here, Ill start with my favorite.

## Give Take
NERSC has a very handy give take command that allows users to share 
file and directories with other NERSC users.

To send files to another user simply type:

    give -u <recipient-username> <file-or-directory>

The recipient will recieve an email informing them they have been given 
a file on NERSC and providing them with instructions on how to take it. 

To see files that have been sent to you simply type:

    take -u <sender-user>

To actually take the files, follow up with the command:

    take -u -a <sender-username> (-d <destination folder>) <filename>

NOTE: If sending many files, the give command will automatically tar them. You 
will need to untar in the usuall way after taking the files, namely 

    tar -xvf files.tar

For more information on the give/take command click [here]
(http://www.nersc.gov/users/storage-and-file-systems/sharing-data/). That same page
also has information on how to create directories visible to those outside 
the NERSC system
