A snakemake pipeline for running cellranger from 10X genomics. This is not intended to be run outside of the MPI-IE, so if you happen to use it don't bother posting feature requests.

scRNA: The usage is `10XscRNA input_directory output_directory genome`, where `input_directory` contains fastq files ending in `*_A_R1.fastq.gz`, `*_B.fastq.gz` and so on.
scATAC: The usage is `10xscATAC -i /path/to/bcl/files -ip /path/to/iterop -o output/directory genome `.

Note that there are only ~4 threads used per step by default, so a large number of chunks can be run in parallel.
