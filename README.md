This repository contain examples for NISE spectral simulations with the NISE\_2017 code.

### Dimer
The folder Dimer contains the file dimer.py which when executed with *python dimer.py* open a GUI for creating a Hamiltonian trajectory for a dimer system.
1. Use python dimer.py to run the GUI. The default settings creates a homo dimer trajectory when the save button is pressed. 
2. Look at the created Hamiltonian text files: Energy.txt and Dipole.txt. Generate the binary files needed for NISE\_2017 by running *translate inpTra*.
3. Submit the linear absorption calculation using the script script1D. You will have to change the location of the NISE\_2017 binary file.
4. Examine the linear response in TD\_Absorption.dat and the absorption spectrum in Absorption.dat for example by plotting with the plot.py script.
5. Analyse the Hamiltonian by submitting the scriptAnalyse script. Examine the output files. Verify that the information on the average frecuencies and coupling match the input you provided in the GUI.
6. Submit the 2DUVvis calculation using the submit2D\_MPI script.
7. Find the 2D spectra from the calculated response functions with: 2DFFT input2D
8. Plot the 2D spectra with the plot2D.py script. Make sure that the plotted spectral region correspond to the region of interest.

### LH2
The folder LH2 contains the files needed to construct a Hamiltonian tranjectory for the LH2 light harvesting system of purple bacteria. The parameters in this file originate from the paper: https://doi.org/10.1021/acs.jpcb.0c08126
The Hamiltonian trajectory is created from the 1kzu.pdb protein data bank file. 
1. Use python (for example from Anaconda3) to generate the binary files using the command: *python GenHam.py*
2. Submit a linear absorption calculation using the script script1D. You will have to change the location of the NISE\_2017 binary file.
3. Examine the linear response in TD\_Absorption.dat and the absorption spectrum in Absorption.dat for example by plotting with the plot.py script.
4. Analyse the Hamiltonian by submitting the scriptAnalyse script. Examine the output files.
5. Submit a Luminescence calculation using the script scriptLum and plot the output.
6. Submit the 2DUVvis calculation using the submit2D\_MPI script.
7. Find the 2D spectra from the calculated response functions with: 2DFFT input2D
8. Plot the 2D spectra with the plot2D.py script. Make sure that the plotted spectral region correspond to the region of interest.
9. Calculate the circular dichroim by submitting the scriptCD script.

Examples are also given for calculating the couplings on the fly with the transition-dipole (TDC) and extended-dipole (EDC) coupling schemes. This reduce the size of the file needed to store the Hamiltonian considerably as only the diagonal part is stored. The couplings are generated from the dipoles and positions of magnesium atoms in the TDC case and the position of the NB and ND in the EDC case.



