# BioDeg, a biodegradation and corrosion simulation code for metallic materials

This repository contains the source code of BioDeg, a code for simulating  mathematical models of biodegradation and corrosion process of metallic materials. This code has been used in the following publications so far, so please cite these if you are interested in using the code for your own research.

    @misc{barzegari2020highly,
          title={Highly scalable numerical simulation of coupled reaction-diffusion systems with moving interfaces},
          author={Mojtaba Barzegari and Liesbet Geris},
          year={2020},
          eprint={2008.11057},
          archivePrefix={arXiv},
          primaryClass={cs.CE}
    }

    @misc{barzegari2021computational,
        title={Computational modeling of degradation process of biodegradable magnesium biomaterials},
        author={Mojtaba Barzegari and Di Mei and Sviatlana V. Lamaka and Liesbet Geris},
        year={2021},
        eprint={2102.10064},
        archivePrefix={arXiv},
        primaryClass={cs.CE}
    }

## Getting started

The code is implemented in FreeFEM, a domain-specific language for finite element computing. So, a parallel version of FreeFEM should be installed. A proper MPI runtime is required to run parallel FreeFEM (such as OpenMPI or MPICH). The PETSc module should also be installed and linked to FreeFEM (which is usually the default config for installing/compiling FreeFEM). The installation procedure can be found [here](https://doc.freefem.org/introduction/installation.html) for different platforms.

After installing the required software packages, the code can be run like this:

`$ mpirun -n 4 FreeFem++-mpi src/main.edp -v 0`

You can specify the number of employed cores (which also implies the number of mesh sub-partitions) by the `-n` switch (it is 4 in this example). The `-v 0` switch is used to suppress the verbosity of FreeFEM. The configs (such as the input mesh or the output location) can be modified in the source file `parameters.idp`.
