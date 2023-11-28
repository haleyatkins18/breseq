# breseq
#breseq tutorial for BIOI 494
#for downloading breseq
#make sure bowtie2 and R are downloaded and can be recognized in your envioronment

conda install -c bioconda breseq

#if this takes too long or doesn't work, download mamba
mamba install breseq

#download the reference genome from https://www.ncbi.nlm.nih.gov/nuccore/NC_012967
#download the read files from https://www.ebi.ac.uk/ 
#accession number is: SRR030257
 
#run breseq, this example includes the sample data you downloaded from above. 
breseq -r NC_012967.gbk SRR030257_1.fastq SRR030257_2.fastq
