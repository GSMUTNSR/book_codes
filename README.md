General information
-------------------

Users should be familiar with the concepts introduced in the book and with the user's manual to run the GSM codes.

The GSM codes are in the "GSM_code" directory.

Most files of the GSM codes are commented, in particular the routines in "numlib" and "GSM_dir". However, the GSM-CC reaction code is not commented for the moment.

The provided directory "workspace_for_GSM" contains interaction files for special options. They were created using the codes of Prof. Morten Hjorth-Jensen (Oslo University, Michigan State University). The Github website of Prof. Morten Hjorth-Jensen containing codes producing nuclear interactions can be found at https://github.com/ManyBodyPhysics/CENS .

The parameters of input files are described in the user's manual (GSM_manual.pdf).

README files are present in all directories Exercises/Chapter_[number]/Exercise_[number], associated to the exercises provided in the book. They describe how to run the code dedicated to each exercise. Input and output files are provided.

If users want to use the files in "test_files" directories to test codes, as mentioned in the user's manual, they must copy the content of "workspace_for_GSM" and "Qbox_interaction" to their own workspace.

The use of many-body projectiles in GSM-CC is in development. Codes might run, but results might not be correct. Hence, only partial information is provided for the moment about the use of many-body projectiles in the user's manual.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Version
-------
This is version 2 (GSM-2.0). 

Here are the main changes compared to GSM-1.0 :

_ Bugs found and corrected in rarely used options:

. Truncated spaces with valence holes and energy/particle-hole truncations

. Spectroscopic factors with cluster and nuclei projectiles

. Multipoles in GSM-CC

. 1 valence proton, and different numbers of protons in diagonalized Hamiltonian and basis Hamiltonian was giving wrong results.

. Valence protons, harmonic oscillator shells, and different numbers of protons in diagonalized Hamiltonian and basis Hamiltonian were giving wrong results.

. Codes had to be slightly reworked for Qbox calculations.

. The GSM optimization code did not work when one has spaces of only protons and only neutrons. It is corrected and test files have been added.

. An error was found in the calculation of used memory in some cases (invisible on screen, found only in tests).

. The GSM-CC Berggren basis was not respecting the orthogonality condition model when the GSM basis had only harmonic oscillator states.

. A wrapper to call Coulomb wave functions form a FORTRAN code has been added.

_ Rms radius and rms-radius one-body strength can now be calculated in no-core GSM using realistic interactions.

_ Added tests when reading the input file and removed useless input occurring in some rare cases.

_ Slight changes in input files with overlap function only.

_ Added test files in "test_files" directories.

_ A few misprints found and corrected in the user's manual.

_ He3 is now written 3He.

_ The name of the file containing phases shifts no longer contains useless vector indices.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Exercises
---------

The results of Exercise X of Chapter 9 had to be refitted and recalculated.

Conclusions are the same, but percentages given in the solution changed:

85% -> 90%

75% -> 82%

69% -> 81%

23% -> 13%

22% -> 13%.
  
The results of Exercise XI of Chapter 9 also had to be recalculated and slightly adjusted.
All conclusions remain the same.


