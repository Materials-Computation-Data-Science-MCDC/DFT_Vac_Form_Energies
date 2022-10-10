# DFT_Vac_Form_Energies
This repository contains the Excel sheets used in the machine learning (ML) models for predicting the vacancy formation energies in the Ni-Cu-Au-Pd-Pt system. Each structure that was made for this project was a face-centered cubic (FCC) structure consisting of 108 atoms total. One by one, each atom was removed from the structure and the energy was calculated using density functional theory (DFT) VASP codes. Once the energy was found the atom was replaced and the next atom would be removed and the process would be repeated for all 108 atoms. The Excel sheets within the subsequent folders contain the vacancy formation energy for each atom in each of the structures created.



Found in this repository are four different folders named: "binary_alloys" and "ternary_alloys". Each folder within these folders will contain an Excel file with multiple sheets specifying the composition of that alloy. 

	In the "binary_alloys" folder, there are 10 Excel files containing sheets for each of the binary alloys for this project, so AuCu, AuNi, AuPd, CuNi, CuPd, and NiPd. In the case of the "binary_alloys" file, there is a Description sheet which contains the compositions used within these sheets. Each binary only hase three different structures, with an atomic percentage split of 25-75, 50-50, and 75-25. 
	
	In the "ternary_alloys" folder, there are 3 Excel files with multiple compositions for the AuCuNi ternary alloy and one composition for the AuCuPd and AuNiPd alloys. Furthermore, the latter two only contain data from strucutures containing only 32 atoms.
	
	
Each Excel sheet will have the same header consisting of: 
	"atom" or "Atom No" which is the atom id in the structures that we created and is not a descriptor for our model. 
	
	Descriptors:
		"Au", "Cu", "Ni", "Pd", and "Pt" in that order with a 1 or a 0 in that column, signifying which type of vacancy it is (i.e., if the order of the values in those columns were 1 0 0 0 0, this would specify that the vacancy was from an Au atom). 
		
		The "dist-#", where # is from 1 to 12, headers specify the bond length from the vacancy atom to its surrounding nearest neighbours (in this case 12 for an FCC structure). 
		
		The next set of headers are "Au-#", "Cu-#", "Ni-#", "Pd-#", and "Pt-#", where # is from 1 to 12, with a 1 or a 0 in the columns. These are used to specify what type of atom the first nearest neighbour is. For example if under the 12 "Ni-#" columns the order was 0 1 0 0 0 0 1 0 0 0 0 1 0, this would mean that the second, seventh, and eleventh atoms surrounding the vacancy were Ni atoms. The order used to specify which atom number is which is explained in the paper.
		
		The next set of headers are "dist_2NN_#", where # is from 1 to 6, with the second nearest neighbour bond length to the vacancy is given (in this case 6 for an FCC structure).
		
		"Vac_vol", which is the Voronoi atomic volume computed in Ovito. 
		
	Target:
		"E-form" is the vacancy formation energy for the atom specified in the first set of descriptors in eV
