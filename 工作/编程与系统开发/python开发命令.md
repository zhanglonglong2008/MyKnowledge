
# 使用pyenv
   是的，**pyenv 可以轻松查询本地已安装的 Python 版本**。以下是具体操作步骤和解释：

---

### 一、查看本地已安装的 Python 版本
1. **直接列出所有已安装的版本**  
   在终端输入以下命令：
   ```bash
   pyenv versions
   ```
   - **输出示例**：
     ```
       system
     * 3.8.12 (set by /Users/你的用户名/.pyenv/version)
       3.9.7
       3.10.2
     ```
   - **`*` 符号**：表示当前激活的 Python 版本。
   - **`system`**：表示系统自带的 Python（通常是 macOS 预装的旧版本，如 Python 2.7）。

---

### 二、其他相关命令
1. **查看当前使用的 Python 路径**  
   ```bash
   pyenv which python
   ```
   - 输出示例：`/Users/你的用户名/.pyenv/versions/3.8.12/bin/python`

2. **查看所有可安装的 Python 版本（包括远程仓库）**  
   ```bash
   pyenv install --list
   ```
   - 这会列出 pyenv 支持的所有 Python 版本（如 `3.11.4`、`3.12.0` 等）。

---

### 三、常见问题解决
1. **如果提示 `pyenv: command not found`**  
   - **原因**：pyenv 未正确安装或环境变量未配置。  
   - **解决步骤**：
     1. 确保已安装 pyenv（安装方法参考之前的回答）。  
     2. 将以下内容添加到 shell 配置文件（如 `~/.zshrc` 或 `~/.bashrc`）：
        ```bash
        export PATH="$HOME/.pyenv/bin:$PATH"
        eval "$(pyenv init --path)"
        eval "$(pyenv virtualenv-init -)"
        ```
     3. 重启终端或执行 `source ~/.zshrc`（根据你的 shell 类型调整）。

2. **如何切换 Python 版本？**  
   - 临时切换（仅在当前终端生效）：
     ```bash
     pyenv shell 3.9.7
     ```
   - 全局切换（所有终端生效）：
     ```bash
     pyenv global 3.9.7
     ```

---

### 四、总结
- **核心命令**：`pyenv versions` 快速查看本地已安装版本。  
- **灵活管理**：pyenv 可安装、切换、隔离不同 Python 版本，适合开发多项目需求。  
- **推荐场景**：需要同时维护多个项目（如 Django 2.x 需 Python 3.6，新项目需 Python 3.11）。

如有其他问题（如安装失败或版本冲突），可提供具体错误信息进一步排查。
> Written with [StackEdit中文版](https://stackedit.cn/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcwNDQyMzc5MF19
-->