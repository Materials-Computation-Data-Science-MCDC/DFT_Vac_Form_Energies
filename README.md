# DFT_Vac_Form_Energies
This repository contains the Excel sheets used in the machine learning (ML) models for predicting the vacancy formation energies in the Ni-Cu-Au-Pd-Pt system. Each structure that was made for this project was a face-centered cubic (FCC) structure consisting of 108 atoms total. One by one, each atom was removed from the structure and the energy was calculated using density functional theory (DFT) VASP codes. Once the energy was found the atom was replaced and the next atom would be removed and the process would be repeated for all 108 atoms. The Excel sheets within the subsequent folders contain the vacancy formation energy for each atom in each of the structures created.



Found in this repository are four different folders named: "binary_alloys" and "ternary_alloys". Each folder within these folders will contain an Excel file with multiple sheets specifying the composition of that alloy. 

	In the "binary_alloys" folder, there are 10 Excel files containing sheets for each of the binary alloys for this project, so NiCu, NiCr, NiCo, FeNi, FeCu, FeCr, FeCo, CrCu, CrCo, and CoCu. In the case of the "binary_alloys" file, there is a Description sheet which contains the compositions used within these sheets. Each binary only hase four different structures, with an atomic percentage split of 20-80, 40-60, 60-40, and 80-20. 
	
	In the "ternary_alloys" folder, there are 8 folders containg one Excel file with multiple compositions for each of the ternary alloys. There is also an Excel file containing the equiatomic ternary alloy data for each of the ternary alloys.
	
	In the "quaternary_alloys" folder, there are 5 folders containing one Excel file with multiple compositions for each of the quaternary alloys.
	
	In the "quinary_alloys" folder, there is one sub folder containing an Excel file with the compositions the vacancy formation energies were calculated for.
	
	
	
Each Excel sheet will have the same header consisting of: 
	"atom" or "Atom No" which is the atom id in the structures that we created and is not a descriptor for our model. 
	
	Descriptors:
		"Fe", "Ni", "Cr", "Co", and "Cu" in that order with a 1 or a 0 in that column, signifying which type of vacancy it is (i.e., if the order of the values in those columns were 1 0 0 0 0, this would specify that the vacancy was from an Fe atom). 
		
		The "dist-#", where # is from 1 to 12, headers specify the bond length from the vacancy atom to its surrounding nearest neighbours (in this case 12 for an FCC structure). 
		
		The next set of headers are "Fe-#", "Ni-#", "Cr-#", "Co-#", and "Cu-#", where # is from 1 to 12, with a 1 or a 0 in the columns. These are used to specify what type of atom the first nearest neighbour is. For example if under the 12 "Ni-#" columns the order was 0 1 0 0 0 0 1 0 0 0 0 1 0, this would mean that the second, seventh, and eleventh atoms surrounding the vacancy were Ni atoms. The order used to specify which atom number is which is explained in the paper.
		
		The next set of headers are "dist_2NN_#", where # is from 1 to 6, with the second nearest neighbour bond length to the vacancy is given (in this case 6 for an FCC structure).
		
	Target:
		"E-form" is the vacancy formation energy for the atom specified in the first set of descriptors in eV
