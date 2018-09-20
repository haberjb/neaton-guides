---
title: "Compiling"
date: 2018-09-19T21:47:34-07:00
weight: 5
draft: true
---

For more advanced users (and certianly for developers), it is sometime
necessary to compile codes on NERSC (instead of loading them). In this section I 
give a few suggestions for compiling codes on NERSC.

## Where to compile?
As previously mentioned, heavy-duty code should be compiled in your $HOME
directory. It is important to note though that code that becasue the cori and
edison system have different underlying architectures, it is frequently the case
that code compiled on edison will not run on cori (and visa versa). As a result,
I recommend creating two directories in your $HOME.

    cori-builds/ edison-builds/ tarballs/

As the names suggest, `cori-builds` should be used for compiling files if you 
are logged in to the cori and similarly for edison. 

Most softwares come bundled as tarballs, 

