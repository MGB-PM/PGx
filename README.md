# lmPGX Pipeline
Performs genotyping, diplotype identification, phenoptying, and reporting

## Setup
### Create a virtual environment
From the src directory:<br/> 
`python3 -m venv env`<br/>
`source env/bin/activate`<br/>
`python3 -m pip install -r requirements.txt`

### Download dependencies and update config file
lmPGX requires the following:
* python3
* GATK4 (tested with GATK4.0.3.0)
* dbsnp VCF file
* java (tested with 1.8.0
* picard (tested with 2.18.3
Update the paths to these tools/resources in lib/config.yml, as well as the other paths specified by lib/config.yml (reference FASTA file and GATK temp out directory). It's best to update all paths in lib/config.yml to be absolute paths

### Example Usage
* activate Python venv
source env/bin/activate
 
`python3 src/pgx.py -b BAM/CRAM -s SAMPLE_ID  -o OUTDIR -c lib/config.yml`
  
#Alternatively, the pipeline can accept a VCF instead of bam. Note though that this has been tested less thoroughly, and the VCF must look like the allbases VCF produced by the variant calling portion of lmPGX

`python3 src/pgx.py -v VCF -s SAMPLE_ID  -o OUTDIR -c lib/config.yml`

