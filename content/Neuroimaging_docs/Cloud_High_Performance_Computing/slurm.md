---
title: SLURM
linktitle: SLURM
toc: true
type: book
date: "2019-05-05T00:00:00+01:00"


# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---
Slurm is an open-source cluster management and job scheduling system.

1. Slurm allocates access to resourses (compute nodes)
2. Slurm provides a framework for starting, executing and monitoring work on allocated nodes
3. Slurm manages queues of pending work

We can use the Slurm manager when running a parallel cluster. AWS is pre-installed on AWS parallel cluster at ```/opt/slurm/```.

Log into the parallel cluster using ```pcluster ssh```. 

Two main commands are used to sumbit jobs: 
- ```srun```: used to submit a job in real time. It has a wide range of options to specify resource requirements
- ```sbatch```: used to sumbit a job script for later exection. The script submitted using sbatch often contains one or more srun commands to launch tasks in parallel


