# Vector template

A template to start all projects on Vector's HPC.

## Organization

Generate ``.slrm`` files using ``sbatch_generator.ipynb`` by customizing the writing loops there.

All files to be `sbatch`ed are stored in `slurm_scripts/`.

To schedule jobs, sweep every ``.slrm`` file in ``slurm_scripts/`` and ``sbatch`` them sequentially using:

```bash run.bash```


