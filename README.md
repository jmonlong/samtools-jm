This is a **modified version** of samtools. 
I added an option to `samtools view` to subset reads by read names when viewing CRAM files.
With this version CRAM conversion (e.g. to FASTQ) can be split in smaller jobs.
Smaller jobs can be cheaper on the cloud when using pre-emptible jobs and the like.
Because it's based on the read names (minus the last character, just in case), both reads in a pair will be in the same subset.

The new arguments to `samtools view` are `-N` for the number of chunks to consider, and `-n` to specify which of the N chunks to output.
