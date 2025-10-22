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
## ⚙️ Terminal Multiplexer (TMUX)

```bash
## 开启鼠标支持（滚轮、窗口点击等）
# 进入命令行模式：Ctrl + b 然后按 ":"
set -g mouse on

## 新建会话
tmux new -s <session-name>

## 连接到已有会话
tmux attach -t <session-name>

## 切换到其他会话
tmux switch -t <session-name>

## 从当前会话分离（保持后台运行）
tmux detach

## 查看所有会话
tmux ls
# 或
tmux list-sessions

## 关闭（终止）指定会话
tmux kill-session -t <session-name>

```

- **More commmon commmands:** [Common commands](https://www.ruanyifeng.com/blog/2019/10/tmux.html)


---

## ⚙️ Bash Configuration (`~/.bashrc`)

```bash
# Aliases
## 仅文件：当前层 / 递归
alias cfiles='find . -maxdepth 1 -type f | wc -l'
alias cfiles_r='find . -type f | wc -l'

## 仅目录：当前层 / 递归
alias cdirs='find . -maxdepth 1 -type d | wc -l'
alias cdirs_r='find . -type d | wc -l'   # 注意包含当前目录“.”

# Conda
export TMPDIR=/media/NAS_R02/USER_PATH/liwei/pip_tmp
export PIP_CACHE_DIR=/media/NAS_R02/USER_PATH/liwei/pip_cache

# Pip
export XDG_CACHE_HOME=/media/NAS_R02/USER_PATH/liexport 
export CONDA_ENVS_PATH=/media/NAS_R02/USER_PATH/liwei/conda/envs
export CONDA_PKGS_DIRS=/media/NAS_R02/USER_PATH/liwei/conda/pkgswei/pip_cache
```



