---
title: "Python@NERSC"
date: 2018-09-18T23:06:20-07:00
weight: 4
draft: true
---

After running jobs on NERSC, we typically want to analyze our data 
using some scripting language (python, gnuplot, matlab etc...). One
approach is to simple copy files from NERSC to your local machine and 
do all the post-processing there. This is a completely valid apporach,
however if you are dealing with large data sets (like wavefunction files
or dielectric tensors) it may be more conveint to post-process directly on 
NERSC. In this section, I will detail one possible workflow for doing so. I
assume users have some familiarity with python.

## Before we can 
