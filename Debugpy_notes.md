
# 🐞 Debugpy Configuration Notes

> Quick reference for enabling VSCode remote debugging with `debugpy` during single- or multi-GPU training.

---

## 🧩 Installation

```bash
pip install debugpy -U
```

---

## ⚙️ Python Debug Setup

在你的 Python 脚本最前面添加以下代码：

```python
import debugpy
try:
    # 9501 is the default attach port in the VS Code debug configuration
    debugpy.listen(("localhost", 9501))
    print("Waiting for debugger attach")
    debugpy.wait_for_client()
except Exception as e:
    pass
```

> 🚨 注意：端口号需与 VSCode 配置一致，建议统一使用 `9501`。

---

## 🐚 Launch Script

通常使用 `sh xxx.sh` 启动训练脚本（如 `deepspeed` 或 `torchrun`），无需额外修改启动方式。

---

## 🧠 VSCode Configuration (`launch.json`)

在 `.vscode/launch.json` 中添加以下配置：

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Attach",
            "type": "debugpy",
            "request": "attach",
           "connect": {
            "host": "localhost",
            "port":9501
           },
           "justMyCode": true
        }
    ]
}
```

---

## 🚀 Debug Workflow

1. 正常运行训练脚本：`sh xxx.sh`
2. 在需要调试的 Python 文件中打断点。
3. 等待终端输出 `Waiting for debugger attach`。
4. 在 VSCode 中选择 `sh_file_debug` 启动调试。
5. 开始调试！

---

## 🧼 Cleanup Reminder

调试完成后，请记得 **注释或删除调试代码**，避免影响后续运行。
