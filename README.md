Copyright notice
----------------

Licensed under the Academic Free License version 3.0 (see file LICENSE.txt in the source code).

General information
-------------------

Users should be familiar with the concepts introduced in the book and with the user's manual to run the GSM codes.

The GSM codes are in the "GSM_code" directory.

Most files of the GSM codes are commented, in particular the routines in "numlib", "GSM_dir" and "CC_dir".

The provided directory "workspace_for_GSM" contains interaction files for special options. They were created using the codes of Prof. Morten Hjorth-Jensen (Oslo University, Michigan State University). The Github website of Prof. Morten Hjorth-Jensen containing codes producing nuclear interactions can be found at https://github.com/ManyBodyPhysics/CENS .

The parameters of input files are described in the user's manual (GSM_manual.pdf).

README files are present in all directories Exercises/Chapter_[number]/Exercise_[number], associated to the exercises provided in the book. They describe how to run the code dedicated to each exercise. Input and output files are provided.

If users want to use the files in "test_files" directories to test codes, as mentioned in the user's manual, they must copy the content of "workspace_for_GSM" and "Qbox_interaction" to their own workspace.

The use of many-body projectiles and no-core framework in GSM-CC is in development. Codes might run, but results might not be correct. Hence, only partial information about it is provided for the moment in the user's manual.

Hypernuclei are also being developed, but the code has not been tested in this case. Hence, no information is being given about it.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Version
-------
This is version 2 (GSM-2.0). 

Here are the main changes compared to GSM-1.0 :

_ Bugs found and corrected in rarely used options:

. Truncated spaces with valence holes and energy/particle-hole truncations

. Spectroscopic factors with cluster and nuclei projectiles

. Multipoles in GSM and GSM-CC were not correct. They are corrected.

. EM transition strengths in GSM-CC were not correct. It is corrected.

. 1 valence proton, and different numbers of protons in diagonalized Hamiltonian and basis Hamiltonian was giving wrong results.

. Valence protons, harmonic oscillator shells, and different numbers of protons in diagonalized Hamiltonian and basis Hamiltonian were giving wrong results.

. Codes had to be slightly reworked for Qbox calculations.

. The GSM optimization code did not work when one has spaces of only protons and only neutrons. It is corrected and test files have been added.

. An error was found in the calculation of used memory in some cases (invisible on screen, found only in tests).

. The GSM-CC Berggren basis was not respecting the orthogonality condition model when the GSM basis had only harmonic oscillator states.

. The Berggren basis for proton in the particle-rotor code was not calculated properly. It is corrected.

. Splines derivatives were too approximate. Effects are only quantitative and small, so that conclusions do not change. 
  The outputs of the exercises using splines derivatives, i.e. Exercises III and IV of Chapter 7, have been recalculated.
  
. M1 transitions were not given in units of magnetons in EM transitions. It is corrected. M1 cross sections were correct.

. The units of spherical harmonics was not standard. It has been corrected. It was not visible in previous applications.

. The GSM code was stuck when using the KKNN potential and HF calculations were wrongly handled. These options had never been used before. KKNN potential use has been corrected and slightly reworked. Test files have been added.

. Rms radii functions were not correct with standard HO-SM. This option had never been used before. It is corrected.

. Errors found in the GSM and GSM-CC hybrid 1D/2D codes (rarely used codes) in proton-neutron configuration print in GSM, use of MSDHF in GSM, observables in GSM-CC. They are corrected.

. Error found in GSM-2D with proton-neutron one-jumps put to full or partial storage. As it can occur only with Hamiltonian calculated on-the-fly, where proton-neutron one-jumps are also put to on-the-fly in practice, this bug was invisible. Added to that, it was inactive when all proton and neutron shells have the same parity, as in test files.

. A bug was found in a+ a~ matrix elements : some values were missing in the output files and a+[p].a~[p] was not appearing on screen. It has been corrected.

. There was a bug when copying TBMEs to a file. Reading TBMEs was correct. The bug has been fixed and input file slightly reworked. 

. A few almost never used array routine members were not correct when using many-dimensional arrays. It is corrected.

_ A wrapper to call Coulomb wave functions from a FORTRAN code has been added.

_ Rms radius and rms-radius one-body strength can now be calculated in no-core GSM using realistic interactions.

_ Added tests when reading the input file and removed useless input occurring in some rare cases.

_ Slight changes in input files with overlap function only.

_ Added test files in "test_files" directories. A few of them were not working properly. It is corrected.

_ A few misprints found and corrected in the user's manual.

_ He3 is now written 3He.

_ The name of the file containing phases shifts no longer contains useless vector indices.

_ The normalization of spherical harmonics was not standard. It is corrected and comments have been updated. The test file has been changed as well.

_ Output of the particle-rotor code has been slightly reworked. Results have not changed.

_ The calculation of multipoles has been added in EM transitions, i.e. when Psi[in] = Psi[out].

_ Allocation and deallocation of arrays, arrays of arrays, etc, has been automatized.

_ Pivots for many-body eigenstates can now be used in GSM-CC.

_ Truncation scheme generalized in GSM-CC : the number of occupied one-body scattering states in GSM-CC many-body states now depends on parity and total angular momentum.

_ Comments added in the GSM-CC code.

_ Transition densities added between eigenstates of same angular momentum and parity.

_ A bug was found in the calculation of GSM-CC eigenstates. Observables related to GSM-CC eigenstates except energy were not correct. In particular, radiative capture cross sections have to be recalculated in Exercise XI of Chapter 9 with different effective charges (see below).

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Exercises
---------

In Exercise VIII of Chapter 3, $x^{-4} e^{i \theta}$ must be replaced by $(x^{-4} - R) e^{i \theta}$ in Eq.(3.62). Everything else is correct, including the code associated to the exercise.

The results of Exercise X of Chapter 9 had to be refitted and recalculated.

Conclusions are the same, but percentages given in the solution changed:

85% -> 90%

75% -> 82%

69% -> 81%

23% -> 13%

22% -> 13%.
  
The cross sections of Exercise XI of Chapter 9 had to be recalculated due to a bug inducing wrong effective charges in particular.
The last paragraph of the exercise solution in the book must be replaced by :
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The proton and neutron effective charge for E1 transitions arising from target recoil only
is 0.375 in absolute value, as $e_p$ and $e_n$ play no role in the used model for $^7$Li(n, $\gamma$) and $^7$Be(p, $\gamma$)
reactions, respectively. 
The proton and neutrons effective charges allowing to reproduce experimental data is 1.6 times larger than the theoretical effective charges, 
which is acceptable as effective charge can vary by up to one unit compared to its bare value [2]. 
Effective charges $e_p$ and $e_n$ can be as large as 1.5 and 0.95, respectively, for example [105]. 
In our calculation, the proton and neutron effective charges for E1 transitions are then : 
$e_n$ = 0.6 for the $^7$Li(n, $\gamma$) reaction and $e_p$ = 0.6 for the $^7$Be(p, $\gamma$) reaction.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------


