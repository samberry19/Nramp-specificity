# Barcode-variant mapping analysis

This directory contains information relevant for replicating the barcode-variant mapping analysis done on 3 separate Nanopore runs in Berry et al. (2025). It is also my hope that it would allow another researcher to perform a similar analysis.

### Input data 
The original data used here is too large to include directly in this repository. You can download it from [...] and add it directly to this folder. Note that all code in this directory should be run on a supercomputing cluster. Approximate time and memory usage requirements will be laid out below.

### External tools
This code relies on several external pieces of software. The first is minimap2, which can be downloaded from here: https://github.com/lh3/minimap2. The version of minimap2 used in Berry et al. (2025) is . Example code to run minimap2 is:

../minimap2-2.26_x64-linux/minimap2 -a -x map-ont library_2_wt.fa NW72DZ_1_sample_1.fastq.gz -o lib2_alignment.sam

The alignmed .bam files for the nanopore reads are included along with the original .fastq files.

medaka
Oxford Nanopore's medaka neural network is used for consensus calling. Install it into a python environment from here: https://github.com/nanoporetech/medaka. Note: it is my impression that medaka requires python 3.10 or less, so you may need to downgrade the python version in your alignment.

CONTENTS
	protocol.docx: gives a general protocol for performing barcode-variant mapping on this kind of data
