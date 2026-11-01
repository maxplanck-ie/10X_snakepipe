A snakemake pipeline for running cellranger from 10X genomics. This is not intended to be run outside of the MPI-IE, so if you happen to use it don't bother posting feature requests.

scRNA: The usage is `10XscRNA input_directory output_directory genome`, where `input_directory` contains fastq files ending in `*_A_R1.fastq.gz`, `*_B.fastq.gz` and so on.
scATAC: The usage is `10xscATAC -i /path/to/bcl/files -ip /path/to/iterop -o output/directory genome `.

Note that there are only ~4 threads used per step by default, so a large number of chunks can be run in parallel.
Multiome (GEX + ATAC): The usage is `10x_ARC -o output_directory --gex-indir dir --atac-indir dir --pair ID:GEX_SAMPLE:ATAC_SAMPLE [--pair ...] genome`. FASTQs are searched recursively as `<sample>_R1/_R2.fastq.gz` (GEX) and `<sample>_R1/_R2/_I1/_I2.fastq.gz` (ATAC); `*_optical_duplicates*` files are ignored. It runs `cellranger-arc count` (2.0.2) once per `--pair`, so the GEX and ATAC FASTQs can live in different directories, e.g. one per lane.
