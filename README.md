# gff2fasta
#### Author: Ian Hu, Department of Biochemistry, University of Cambridge #### 
# This program produces a fasta file of gff3 features and sequences when supplied with genomic file, 
# gff file to extract features from, requested features, and a output name,
# e.g. you want to extract all the CDS or intron sequences from a gff and a separate fasta files.
# The program uses only bash and ancient awk script, so presumably runs pretty fast,
# but if you have an older version of awk this will not work as the size of string is limited.
# Output sequence name rule is >scaffoldname_start_end_feature
# gff2fasta would try to load the whole genome to memory at once, so if your genome is big, turn off chrome.
# WARNING: the output will not be sorted as this will take too much memory and time.
#
# NOTE1: in version 2 (this version) an optional argument is supplied for collecting up- and downstream 
# sequences. Add [-ud] and [up- downstream nubmer of nucleotides] after the fourth arguement.
#
# NOTE2: if there's any ambiguous nucleotides in the sequence, after the reverse compliment function
# they will show as "N". Deal with it.
#
# The author claims no copyright for this. however if you wish to buy the author a beer or have any problems, 
# contact the author at iih20@cam.ac.uk
##############################################################################################################
USAGE: ./gff2fasta fasta_location gff_location features separated by comma[,] outfile_name 
ex: ./gff2fasta path_to_genome.fasta path_to_mRNA.gff CDS,exon output_features.fasta
