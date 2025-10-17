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

---

## ⚙️ Bash Configuration (`~/.bashrc`)

> Keep all aliases and environment variables here.

```bash
# Example setup
alias ll='ls -lah --color=auto'
alias cfiles='find . -type f | wc -l'
export PATH=$PATH:/usr/local/cuda/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
