
# ncbi-compress-experiments
This repo contains the scripts used for experimenting with NCBI database compression for mNGS applications.


## Abstract

The exponential growth of the NCBI GenBank database presents significant challenges for metagenomic analysis, particularly in pathogen detection. This paper introduces a novel compression approach to address these challenges, aiming to reduce the database size while maintaining sequence diversity. Our method, utilizing sourmash with MinHash techniques, compresses both nucleotide and protein sequences in the NCBI databases through efficient kmer hashing, ensuring minimized redundancy. This approach is validated across various benchmark datasets, highlighting its utility in accurately identifying both known and novel pathogens with increased computational efficiency. We demonstrate that the compression technique retains the ability to detect pathogens post-compression while managing the increasing database sizes, crucial for keeping metagenomic tools up-to-date. 


## Repository Details


**Experiment 8 provides the data and scripts for all analyses presented in this manuscript:**
* **/experiment-8** - this is the main directory containing sample reports and scripts for analysis comparing mNGS results obtained from compressed database(s) to uncompressed databases.
	* check-initial-benchmarks.ipynb - comparison of single sample reports in one-off fashion
	* **check-initial-benchmarks-bulk-analysis.ipynb** - bulk comparison of Illumina sample reports; the main script!
	* check-initial-benchmarks-bulk-analysis-Nanopore.ipynb - bulk comparison of Nanopore sample reports
	* evaluate-simulation-benchmarks-bulk.ipynb - bulk comparison of viral simulation datasets
* **/experiment-8/data/** - contains sample reports obtained from mNGS pipeline runs conducted on the standard NCBI database(s) as compared to the compressed database(s). 
	* BASELINE - baseline sample reports for UnambiguouslyMapped, and virus simulation datasets
	* BASELINE_MD - baseline sample reports for Medical Detectives cases
	* NEW - sample reports obtained from mNGS pipeline runs on compressed data (for 2021 indexes)
	* NEW_MD - sample reports for Medical Detectives samples obtained from mNGS pipeline runs on compressed data (for 2021 indexes)
	* petshop - sample report for single petshop sample 

Experiments 1 through 7 provided supporting information guiding the implementation of the compression approach:
* /experiment-1 - initial evaluation of sourmash containment threshold for recovering genome similarity, applied to nucleotide sequences
* /experiment-1-protein - initial evaluation of sourmash containment threshold for recovering genome similarity, applied to protein sequences
* /experiment-2 - at what similarity thresholds does minimap2 begin to fail to align nucleotide sequences?
* /experiment-2-protein - at what similarity thresholds does DIAMOND begin to fail to align protein sequences?
* /experiment-3 - initial prototyping for a greedy approach to compression
* /experiment-4 - testing the prototype approach on real data
* /experiment-5 - testing how much time is saved by using the prototype mini clustered database
* /experiment-6 - testing scalability on larger compute
* /experiment-7 - based on engineering work to scale clustering approach, examine the resulting clusters to assess validity

Between experiments 7 and 8, CZ ID engineering team scaled the approach to work with full NCBI databases; ultimately, the approach implemented in the final compression differs in implementation from the prototype approach implemented here. 


## Relevant links
* CZ ID:  [https://czid.org/](https://czid.org/)
* CZ ID help center:  [https://help.czid.org/](https://help.czid.org/)
* CZ ID workflow code: [https://github.com/chanzuckerberg/czid-workflows](https://github.com/chanzuckerberg/czid-workflows)