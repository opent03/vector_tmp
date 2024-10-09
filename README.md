# Vector template

A template to start all projects on Vector's HPC.


## Run interactive jobs

For an interactive session, run:

```srun -q normal -p t4v1,t4v2,rtx6000,a40 -c 16 --gres=gpu:1 --mem=64G --time=16:00:00 --pty bash```

and edit the ``srun`` config as will. Most importantly, the ``--pty bash`` flag needs to be at the end.

## ``SBATCH``-ing multiple jobs

Generate ``.slrm`` files using ``sbatch_generator.ipynb`` by customizing the writing loops there.

All files to be `sbatch`ed are stored in `slurm_scripts/`.

To schedule jobs, sweep every ``.slrm`` file in ``slurm_scripts/`` and ``sbatch`` them sequentially using:

```bash run.bash```

## Jupyter Notebook hosted on a node

Edit node configurations in ``jupyter_templates/``. Then, from ``vector_tmp/``, ``sbatch`` them:

```sbatch jupyter_templates/[cpu-gpu].slrm```

Then, run ``tail -f notebook.out``, copy the line that says ``https://gpuXXX:8372/tree?token=XXXXX`` into "existing kernel" in the Jupyter file on your VSCode notebook.


