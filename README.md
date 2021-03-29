# DicksonLabSeqRepo
Sequencing repository for the Dickson Lab

This repository stores information about metagenomic sequencing runs that were sequenced for an experiment in the Dickson lab in the Pulmonary and Critical Care Division of Internal Medicine at the UM.  
Sequencing runs are stored on [Data Den storage archive](https://arc.umich.edu/data-den/) and the [Turbo]https://arc.umich.edu/turbo/) storage drive from [Advanced Research Computing (ARC)](https://arc.umich.edu/) at UM.  


## Description of run metadata

File: `seqMetadata.txt`  
This file in this repository stores sequencing run metadata in a tab separated format for easy access via Linux commandline, R, Python and Excel. Following is a description of the data elements that are stored with a description of their contents. Users who are making a submission to the sequencing repository are recommended to consult these descriptions for data management. Users who are collaborators in this GitHub repository can add new data fields to the `seqMetadata.txt` as needed. Whenever a new column is established in the metadata file, we ask to include a description of the column in this document.  

|#|Column name|Data type|Possible values|Description|
|---|---|---|---|---|
|1|#RunID|str||ID for the sequencing run as provided by the sequencing instrument. Always required.|
|2|#SampleType|str|lung-microbiome, gut-microbiome, metagenome, isolate, mixed|Type of sample used for sequencing. Mixed type is only possible for a barcoded run where the metadata will have this information.|
|3|#ExtractSrc|str|feces, BAL, gut-swab, OP-swab, nasal-swab|Sample type from which extraction was performed. OP = oropharyngeal|
|4|#AssayType|str|WGS|Type of sequencing reaction that was performed. Currently only whole genome shotgun is used.|
|5|#LibSource|str|genomic|Source material for the library - DNA or RNA.|
|6|#LibSelection|str|random, PCR|Library selection method. Fragments radomly selected or amplified.|
|7|#LibKit|str|RAD004, RBK004|Library prep kit used.|
|8|#LibLayout|str|single, paired, 1d2|Library layout.|
|9|#SeqLoc|str|DL, AGC|Sequencing location. DL = Dickson lab, AGC = UM Advanced Genomics Core.|
|10|#SeqDate|date|yyyy-mm-dd|Sequencing date. Though discouraged, yyyy-mm can be used if a specific date is not known.|
|11|#SeqPlatform|str|Nanopore, Illumina|Sequencing platform or maker of the sequencing instrument.|
|12|#SeqInstrument|str|MinION, MiSeq, HiSeq1000|Exact model of the sequencing instrument.|
|13|#Barcode|int|0, 1:n|If the run was barcoded, parent run would recieve value 0 and all children would receive their barcode number. Leave blank if the run wasn't barcoded.|
|14|#PoreVer|str|9.4.1|Specific to Nanopore sequencing, pore version of the sequencing chemistry.|
|15|#BasecallVer|str|guppygpu-vX.X.X|Specific to Nanopore sequencing, program and version of the basecaller software.|
|16|#OrgGenus|str||If an isolate, genus name of the organism.|
|17|#OrgSpc|str||If an isolate, species name of the organism.|
|18|#OrgStr|str||If an isolate, strain name of the organism.|
|19|#OrgIsolate|str||If an isolate, isolate name of the organism.|
|20|#OrgSpcTaxID|int||If an isolate, NCBI species taxonomy ID of the organism.|
|21|#OrgTaxID|int||If an isolate, direct NCBI taxonomy ID of the organism.|
|22|#Host|str|Genus species|If a microbiome sample, genus and species name of the host organism.|
|23|#HostDisease|str||If a microbiome sample, brief disease condition of the host organism.|
|24|#RunSize|int||Size of the complete run tarball in bytes.|
|25|#FastqSize|int||Compressed fastq size in bytes. Only passed reads for Nanopore sequencing.|
|26|#ReadNum|int||Number of reads in the sequencing set. Only passed reads for Nanopore sequencing.|
|27|#ReadLenMin|int||Minimum read length in the sequencing set. Only passed reads for Nanopore sequencing.|
|28|#ReadLenMax|int||Maximum read length in the sequencing set. Only passed reads for Nanopore sequencing.|
|29|#ReadLenAvg|int||Average read length in the sequencing set. Only passed reads for Nanopore sequencing.|
|30|#ReadBases|int||Number of bases in the sequencing set. Only passed reads for Nanopore sequencing.|
|31|#Contact|str|uniqNames|A comma separated list of uniqnames who can be contacted for this run for more details.|

All column names are prefixed with a hash/pound (`#`) sign, so that, it's easier to manage column names even with basic Linux commands and utilities.
