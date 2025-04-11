# PICRUSt installation - For Mac (M1/M2)

> During isntallation, a common issue on Apple Silicon (M1/M2) systems due to missing dependencies like epa-ng, which isn’t available for osx-arm64.
We can bypass this easily by creating a conda environment using the Intel (x86_64) platform via Rosetta 2, which allows you to install and run software made for Intel Macs. <br>

✅ **Solution: Create an Intel-based PICRUSt2 environment using osx-64**
````
softwareupdate --install-rosetta   
````
> This tells conda: "Pretend I'm on an Intel Mac (osx-64), and install picrust2 from bioconda/conda-forge."
<br>


**Step 1: Create a new Intel-based conda environment**

````
CONDA_SUBDIR=osx-64 conda create -n picrust2_env -c conda-forge -c bioconda picrust2
````
**Step 2: Activate the environment**
````
conda activate picrust2_env
````

**Then set the CONDA_SUBDIR for the environment so it keeps using the right architecture:**
````
conda config --env --set subdir osx-64
````

🔎 **Verify It Works**
````
picrust2_pipeline.py -h
````







