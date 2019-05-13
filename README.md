# mslurm

## What 

`mslurm` is a wrapper over slurm commands to store the mapping of the command with the output in a database file.

## Why

I use `slurm` for running jobs over a cluster. It is hard for me to keep track of which job corresponds to which config just by looking at the job id. This provides an easy way to store this mapping.

## How

* Run `pip3 install -r requirements.txt`.
* Update the path (where the db file is stored) in `mslurm/mslurm_db`. 
* Add the directory `mslurm` to the `$PATH` variable.
* run `mslurm "<slurm-command">`. eg if the slurm command is `sbatch --mem=60000 --gres=gpu:1 -c 2 --time=2-23:35:00 -o slurm/%j.out script.sh`, run `mslurm "sbatch --mem=60000 --gres=gpu:1 -c 2 --time=2-23:35:00 -o slurm/%j.out script.sh".`
