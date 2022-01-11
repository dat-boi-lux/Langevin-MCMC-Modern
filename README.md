# Langevin-MCMC

**This fork of https://github.com/luanfujun/Langevin-MCMC includes additional tweaks to enable a more seamless build experience (scroll to the bottom of the readme for detailed build instructions.)**

This is the code repository for paper "[Langevin Monte Carlo Rendering with Gradient-based Adaptation](https://research.cs.cornell.edu/langevin-mcmc/data/paper.pdf)" by Fujun Luan, Shuang Zhao, Kavita Bala, and Ioannis Gkioulekas. Check out the [project page](https://research.cs.cornell.edu/langevin-mcmc/) for more information. 
 
## LMC (44.69 seconds):
![LMC](scenes/torus/lmc_timeuse_44.689152s.png)
## H2MC (45.38 seconds):
![H2MC](scenes/torus/h2mc_timeuse_45.381592s.png)

This code implements proposed LMC algorithms within the open-source reference implementation of H2MC by Tzu-Mao Li. https://github.com/BachiLi/dpt.  

If you use this code, please cite the paper:
```bibtex
@article{luan2020langevin,
  title = {Langevin Monte Carlo Rendering with Gradient-based Adaptation},
  author = {Luan, Fujun and Zhao, Shuang and Bala, Kavita and Gkioulekas, Ioannis},
  journal = {ACM Trans. Graph.},
  volume = {39},
  number = {4},
  year = {2020},
  publisher = {ACM},
}
```

The code has been tested on a 32-core machine with Ubuntu 18.04 and gcc 9.2.1. It has not been tested on OSX or Windows yet.

# Build Instructions (Ubuntu 20.04):

These instructions assume you have basic knowledge of how compiling on Linux works.

This code uses the **Tup** build system. Download and install *Tup*:\
```sudo apt-add-repository 'deb http://ppa.launchpad.net/anatol/tup/ubuntu precise main'```\
```sudo apt-get update```\
```sudo apt-get install tup```

Next install all the required dependencies:\
```sudo apt install libeigen3-dev openimageio-tools libembree-dev zlib1g zlib1g-dev```

Next download the Intel® Implicit SPMD Program Compiler from: https://ispc.github.io/downloads.html \
Extract this file *somewhere*, then locate the **ispc** executable within: *ispc-vX.XX.X-linux/bin* 

Create a symbolic link to this executable within *usr/bin/* with this command: \
```sudo ln -s '/the/directory/to/ispc-vX.XX.X-linux/bin/ispc' '/usr/bin/'```

Next, clone this repository with this command:\
```git clone https://github.com/dat-boi-lux/Langevin-MCMC-Modern.git```

Once it has successfully cloned: navigate to the */Langevin-MCMC-Modern/* directory (usually within your */home/* folder) and run these commands within that directory:\
```tup init```\
```tup```

After a while, the code should have compiled.\
the compiler itself **dpt** is located at: */Langevin-MCMC-Modern/src/bin/dpt*

There are test scenes within */Langevin-MCMC-Modern/scenes/*.

Please feel free to contact (fujun @ cs.cornell.edu) if there are any issues/comments/questions.
