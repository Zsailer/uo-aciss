# ACISS: University of Oregon
## Useful scripts for working on UO's computational cluster


Just clone this repo onto ACISS to begin using. 

## Useful commands

- `qstat`: check status of job running on nodes.
- `qdel <jobid>`: kill a job running on nodes.


##Queues 

Limited to 24 hours of wallclock time.

- `generic`: nodes with 12 cores and 72GB of RAM. 
- `fatnodes`: nodes with 32 cores 384GB of RAM.
- `gpu`: nodes with 12 cores, 72GB RAM, and 3 nVidia M2070 GPUs.

Long queues with default 4 day wallclock, 2 week maximum.

- `longgen/longfat/longgpu`
- `short`: generic node with 4 hour time limit
- `student`: reserved for students in class.

## Included

- **Python 3 Virtual environment setup**: submit the virtualpy.pbs file to automatically setup a scientific python 3 environment.

## How to write PBS file

```
#################################################################
###### Example PBS (Portable Batch System) Script
#################################################################
#! /bin/bash -l
#
### Name the job
#PBS -N stuff
#
### Set the number of nodes and cores to use for the job
#PBS -l nodes=1:ppn=12
#
### Type of job to run
#PBS -q generic
#
### Path to start this script from
#PBS -d /path/to/run/directory
#
### Path to output file
#PBS -o /path/to/output
#
### Path to the output error
#PBS -e /path/to/output
#
### Combine the output and error file
#PBS -j oe
#
### Email me when the job is done
#PBS -m e 
#
##################################################################
###### Write program to run here 
##################################################################
```