# 🔧 Configuration Notes

> Quick reference for SSH, environment setup, and frequently used configs.

---

## 🖥️ SSH

### Local Computing Resources
- **Server:** `yanglab12.bg.ic.ac.uk`  
- **User:** `liwei`  
- **Password:** *(if forget, ask @zhenxuan)*

### Imperial-X HPC
- **Login URL:** [https://login-node.ixhpc.ic.ac.uk/](https://login-node.ixhpc.ic.ac.uk/)
- **User:** *(Imperial login, part before @ic.ac.uk)*  
- **Password:** *(if forget, ask @fanwen)*

### Imperial HPC Docs
- **Tutorial:** [Getting Started Guide](https://icl-rcs-user-guide.readthedocs.io/en/latest/hpc/getting-started/)

### Isambard-AI HPC
- **Tutorial:** [Getting Started Guide](https://portal.isambard.ac.uk/profile/)

---

## ⚙️ Bash Configuration (`~/.bashrc`)

```bash
# Aliases
alias cfiles='find . -maxdepth 1 -type f | wc -l'

# Conda
export TMPDIR=/media/NAS_R02/USER_PATH/liwei/pip_tmp
export PIP_CACHE_DIR=/media/NAS_R02/USER_PATH/liwei/pip_cache

# Pip
export XDG_CACHE_HOME=/media/NAS_R02/USER_PATH/liexport 
export CONDA_ENVS_PATH=/media/NAS_R02/USER_PATH/liwei/conda/envs
export CONDA_PKGS_DIRS=/media/NAS_R02/USER_PATH/liwei/conda/pkgswei/pip_cache