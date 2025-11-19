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
## 打开鼠标滚轮功能
ctrl+b，然后按":"，进入命令行模式
输入set -g mouse on
设置成鼠标模式，能直接鼠标点窗口切换

## 新建会话
tmux new -s <session-name/number>

## 接入会话
tmux attach -t <session-name/number>

## 切换会话
tmux switch -t <session-name/number>

## 分离会话
tmux detach

## 列出会话
tmux ls
tmux list-session

## 杀死会话
tmux kill-session -t <session-name/number>

## 清空所有会话且编号重置
tmux kill-server
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

---
# ⚙️ Linux adduser script

```bash
#!/bin/bash
USER=$1

adduser --gecos "" "$USER"
usermod -s /bin/bash "$USER"
passwd "$USER"
usermod -aG ssh "$USER"
usermod -aG sudo "$USER"

echo ">>> User $USER created successfully with SSH + sudo enabled."
```

运行：

```bash
sudo bash create_user.sh liwei2
```
