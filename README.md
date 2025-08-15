# Molecular-dynamics-simulation-of-active-polymers-under-cylindrical-confinement
The project shows how to simulate the motion of active polymers under cylindrical confinement, by using the molecular dynamics simulation method based on the LAMMPS software. 
## Preparation for simulation
This project is conducted with the open-source software LAMMPS, so you should configure the environment and compile the related files accordingly. You can download the packages from <https://www.lammps.org/download.html>. 

Next step is building LAMMPS with cmake. In the linux terminal window, Go to the directory where the downloaded package is located:
```
cd  path
tar -zxvf lammps-stable.tar.gz # replace with your package's name
```
then just follow the instrument of LAMMPS manual to build LAMMPS:
```
cd lammps-23Jun2022                                             # wirte your version
mkdir build; cd build                                           # create and use a build directory
cmake -D PKG_MOLECULE=yes -D LAMMPS_MACHINE=mpi ../cmake      # configuration reading CMake scripts from ../cmake
cmake --build .                                                 # compilation (or type "make")
```
After compilation, you get the LAMMPS executable **lmp_mpi** inside the build folder. For more details, you can read offical manual <https://docs.lammps.org/Manual.html>.
## Coding and running
This project studies the motion of active polymers within a cylinder and on surface of a cylinder respectively. The cylindrical wall has harmonic interaction with active polymers, while actove polymers have pair_style interaction, bond_style and angle_style interaction. Research are focused on the influence of the angle interaction coefficient $\kappa$ on motion of active polymers. 
The key coding file is an input file(with the ".in" suffix). LAMMPS will read the commands in the input file and start the simulation. The running command is as follows:
```
mpirun -np 6 /path/lmp_mpi -in file.in       # 6 is the number of operating cores of the computer, file.in is the coding file. 
```
After running, you can get the dump file which records the information of the atoms and polymers.
## Visualization
Visualization is achieved by the OVITO software. Opening the dump files with OVITO, you can observe the motion of active polymers.
