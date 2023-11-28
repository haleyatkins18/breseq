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

#in general, the command looks something like this:
breseq -r reference1.gbk [-r reference2.gbk ...] reads1.fastq [reads2.fastq, reads3.fastq...]

#if you have multiple reference genomes, remember to put -r before each one


Required options:
-r


Commonly used options:
-n <string> --name <string> 
human-readable name of the analysis run for output

-j <int> --num-processors <int>
number of processors to use in multithreaded steps

--no-junction-prediction
do not predict new sequence junctions

-p --predict-polymorphisms
predict polymorphic (mixed) mutations

Additional commands to interpret the output files

Command: bam2aln
breseq BAM2ALN [-b reference.bam -f reference.fasta -o alignment.html -n 200] region1 [region2 region3 ...]
display reads aligned to the specified region or regions
Command: bam2cov
breseq BAM2COV [-b reference.bam -f reference.fasta --format PNG -o output.png] region1 [region2 region3 ...]
create a coverage plot or table for the specified region or regions 
