# 🔧 Configuration Notes

## 🖥️ SSH
- **Server:** `yanglab12.bg.ic.ac.uk`
- **User:** `liwei`
- **Password:** `123456`

## 📂 Configuration in bashrc.sh

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