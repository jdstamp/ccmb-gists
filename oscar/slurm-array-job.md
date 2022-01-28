# Parallelize Computation with Slurm Array Jobs

## R example
Slurm array jobs can submit multiple identical jobs with different task ID's.
This task ID can be passed as argument to an R script and used e.g. to run a script on a different file.
The following code snippets show a basic setup to make use of Slurm Array Jobs in this context.

### slurm-job.sh
```bash
#!/bin/bash
#SBATCH --time=0-01:00 # Runtime in D-HH:MM
#SBATCH --job-name="arrayJob"
#SBATCH --account=ccmb-condo
#SBATCH --mem-per-cpu=1G # Different units can be specified using the suffix [K|M|G|T]
#SBATCH --cpus-per-task=32
#SBATCH -n 1
#SBATCH --array=1-8

module load R/4.0.5

Rscript --vanilla "path/to/script.R" "${SLURM_ARRAY_TASK_ID}"
```
### script.R
```R
args = commandArgs(trailingOnly=TRUE)
task_id <- as.integer(args[1])
data_files <- list.files(path = file.path("data/dir"), pattern = "regex file pattern")
f <- data_files[task_id]
```
