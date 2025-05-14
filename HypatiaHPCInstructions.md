# Connecting to Hypatia

If you have not done so already, please request access through the [official form](https://www.st-andrews.ac.uk/high-performance-computing/).

Connect via SSH using your username:

```bash
ssh username@138.251.14.231
```

- Replace `username` with your assigned username.
- Enter your initial password (provided via email). You will be prompted to set a new ten character long password immediately.
  - Password connections will eventually be discontinued in favour of SSH keys. More info on SSH can be found on the [CS wiki](https://wiki.cs.st-andrews.ac.uk/index.php?title=Using_SSH).
- If this prompt does not appear, reset your password manually using:

```bash
passwd
```

- Contact IT Services (itservicedesk@st-andrews.ac.uk) if you encounter issues.

---

# File Management

**Home Directory (scripts, environments, logs, outputs):**

```bash
/home/username
```

**Shared Scratch Space (datasets):**

```bash
/sharedscratch/username
```

- Replace `username` with your assigned username.

You can create a convenient link once:

```bash
ln -s /sharedscratch/$USER ~/scratch
```

Afterwards simply run `cd ~/scratch` from anywhere.

---

# Transferring Files

You can transfer files using `rsync`, `scp`, or graphical tools like [FileZilla](https://filezilla-project.org/).

**Using `rsync`:**

*Upload files to Hypatia:*

```bash
rsync -avz /path/to/local/files username@138.251.14.231:/sharedscratch/username/path/on/hypatia
```

*Download files from Hypatia:*

```bash
rsync -avz username@138.251.14.231:/sharedscratch/username/path/on/hypatia /path/to/local/destination
```

- Replace `username` and paths accordingly.

---

# Using SLURM

[SLURM](https://slurm.schedmd.com/documentation.html) manages job submissions and monitoring:

- Check job queue status:

```bash
squeue
```

- Submit a job:

```bash
sbatch some_script.sh
```

- Cancel a running job (replace `job_id` with the actual ID):

```bash
scancel job_id
```

- Please be conservative when requesting resources. Benchmark first - more compute does not always mean faster results. As a rule of thumb, request no more than one-eighth of the resources on a GPU node to allow fair usage, since each node has 8 GPUs.

---

# Python Environment Setup

### Conda

A shared installer is provided. **Do not install Conda in your home directory**, as that impedes nightly back‑ups.

```bash
install-conda
```

This places Conda in your scratch space and initialises your shell. Activate an environment with

```bash
conda activate <env_name>
```

### Containers (Apptainer)

Apptainer is available system‑wide:

```bash
module load apptainer
```

Use containers when reproducibility or complex dependencies are required. Seek out documentation and video-guides where appropriate.

- Once set up, you can activate the environment in SLURM job scripts.

---

# Job Submission Script Example

Example SLURM script (`some_script.sh`):

```bash
#!/bin/bash
#SBATCH --job-name=python_train_script
#SBATCH --output=logs/my_job_%j.out
#SBATCH --error=logs/my_job_%j.err
#SBATCH --partition=gpu
#SBATCH --gres=gpu:1
#SBATCH --time=12:00:00
#SBATCH --mem=48G
#SBATCH --cpus-per-task=21

# Load and activate Conda environment
source ~/.bashrc
conda activate your_environment_name

# Navigate to project directory
cd /home/username/project_directory/

# Execute training script
CUDA_VISIBLE_DEVICES=0 python train.py \
    --batch_size 1 \
    --data_dir=/sharedscratch/username/data/path \
    --lr 0.00001 \
    --max_epochs 100 \
    --output_dir ./outputs \
    --seed 0 \
    --task task_name

# Confirmation message
echo "Job complete"
```

- Replace `your_environment_name`, `username`, and paths appropriately.
- Adjust resource allocation as required by your tasks.

**Note:** Including `CUDA_VISIBLE_DEVICES=0` ensures GPU usage.

---

# Monitoring Jobs

- Submit the job:

```bash
sbatch some_script.sh
```

- Check running jobs:

```bash
squeue
```

- Check specific job:

```bash
squeue | grep job_id
```

- List jobs submitted by your user
```bash
squeue -u $USER
```

- View logs/output:

```bash
cat ~/logs/my_job_jobid.out
cat ~/logs/my_job_jobid.err
```

Replace `jobid` with the actual ID from SLURM.

---

# Remote Connection (Outside University Network)

When connecting remotely, use the Cisco AnyConnect VPN provided by the university.

- Download from [St Andrews AppsAnywhere](https://www.st-andrews.ac.uk/it-support/services/wifi/vpn/).

---

# Important Notes

- The login node (`login01`) should **not** be used for strenuous tasks such as moving, compressing, or transferring large files. If unsure, please contact IT Services (itservicedesk@st-andrews.ac.uk).

---

# Additional Resources

- [University HPC resources](https://www.st-andrews.ac.uk/high-performance-computing/help-and-contact/using/)
- [Computer Science Wiki](https://wiki.cs.st-andrews.ac.uk/)

# Disclaimer

This guide is provided for informational purposes only. While every effort has been made to ensure accuracy and completeness, the instructions and advice contained within this document are provided without warranty of any kind. The University of St Andrews, the authors, and contributors shall not be held liable for any direct or indirect damages or issues arising from the use of this guide. Users should follow these instructions at their own risk and are encouraged to verify the steps and adapt them as necessary for their specific needs and environments. Please read https://wiki.cs.st-andrews.ac.uk/ for more information.
