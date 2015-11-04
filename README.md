(Note: ProteinEvolver is hosted on Google Code, which is shutting down. A GitHub project was made for it, but it lacked any of the source code. I'm copying the code over until the authors can fix this -- Brian O'Meara, Nov 2, 2015.)

ProteinEvolver generates samples of protein-coding genes and protein sequences evolved along phylogenies under structure-based substitution models. These models consider the protein structure to evaluate candidate mutations, which can be accepted (substitutions) or rejected depending on the energy of the protein structure of the mutated sequence. The simulation of molecular evolution occurs along phylogenetic histories, which can be either user-specified or simulated by the coalescent modified with recombination (including recombination hotspots), migration, demographics and longitudinal sampling. The file ProteinEvolver1.2.0.manual.pdf includes detailed documentation, and the user is strongly advised to read it carefully before using the program.

Citation

Arenas, M.; Dos Santos, H.G.; Posada, D. and Bastolla, U. 2013. Protein Evolution along Phylogenetic Histories under Structurally Constrained Substitution Models. Bioinformatics, 29(23):3020-3028.

http://bioinformatics.oxfordjournals.org/content/29/23/3020.abstract


Please, do not hesitate to contact us (miguelmmmab@gmail.com) for any question. 


Download and Installation

You can download the zipped folder from GitHub.

Compilation

The program should compile without much problem in any Unix-like environment (Linux, MacOSX, etc.). A makefile is provided for the gcc compiler, but if you have cc instead, just change gcc for cc in the makefile. The default optimization level is set to -O3. To compile in macintosh with an intel processor, and probably in othe machines, you can enable the option -fast instead.
To compile the program move into the folder src inside the ProteinEvolver-1.2.0 folder and type:

```make all```
to compile the executable in the current folder (src) inside the ProteinEvolver-1.2.0 folder, or

```make install```
to clean, compile and install the new executable in the exe folder inside the ProteinEvolver-1.2.0 folder.

The program should compile without problems with a second makefile "Makefile_MPI" for a MPI version. This makefile might need some modifications for particular OS. To compile the program type:

```make -f Makefile_MPI```

Execution

 
The program runs in a command-line window. In MacOS X and Linux the user needs to open the Terminal application, and in Windows XP the user
should open the Command Prompt. To run the program move to the folder where the executable is located and type:

```./ProteinEvolver1.2.0```


For execute the parallel version, MPI libraries have to be installed in the host. The minimum number of processors is two. An example of execution in 3 processors is the next:

```mpirun -np 3 ProteinEvolver1.2.0```

Arguments can be entered in the command line or, more conveniently, from a text file called "parameters" that should be located in the same directory as the executable. See the documentation for further details.



Disclaimer

 
This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later 
version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307, USA.


Miguel Arenas  - marenas@cbm.uam.es - miguelmmmab@gmail.com

David Posada  - dposada@uvigo.es 

Ugo Bastolla  - ubastolla@cbm.uam.es 

