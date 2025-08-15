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
After compilation, you get the LAMMPS executable **lmp_mpi** inside the build folder.

for more details, you can read offical manual <https://docs.lammps.org/Manual.html>.
## coding and running
