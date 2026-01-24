这份手册涵盖了你安装的三个工具，旨在让你以最快速度完成配置并投入使用。

### 1. 终端初始化 (Shell Configuration)

安装完成后，必须将工具关联到你的 Shell 配置文件（macOS 默认为 `~/.zshrc`）。

**执行以下命令：**

```bash
# 将 Starship 关联到 Zsh
echo 'eval "$(starship init zsh)"' >> ~/.zshrc

# 为 eza 设置别名（替代 ls），增加图标显示
echo 'alias ls="eza --icons"' >> ~/.zshrc
echo 'alias ll="eza -lh --icons"' >> ~/.zshrc

# 生效配置
source ~/.zshrc

```

---

### 2. 字体激活 (Font Setup)

由于你安装了 `font-fira-code-nerd-font`，必须手动在应用中指定才能看到图标和连字。

* **iTerm2 / 系统终端**：
* 进入 **Settings -> Profiles -> Text**。
* **Font**：选择 `FiraCode Nerd Font`。
* 勾选 **Use Ligatures** (使用连字)。


* **VS Code**：见下文。

---

### 3. VS Code 极简配置手册

按 `Cmd + Shift + P`，输入 `user settings json` 并回车，在 `settings.json` 中加入或修改以下核心项：

```json
{
  // 1. 设置编辑器字体（优先 FiraCode，开启连字）
  "editor.fontFamily": "'FiraCode Nerd Font', 'JetBrainsMono Nerd Font', monospace",
  "editor.fontLigatures": true,

  // 2. 设置集成终端字体（确保 Starship 图标不乱码）
  "terminal.integrated.fontFamily": "'FiraCode Nerd Font'",
  
  // 3. 建议：开启终端图标颜色支持
  "terminal.integrated.gpuAcceleration": "on"
}

```

---

### 4. 常用指令速查

* **Starship**: 默认即刻生效。如需自定义样式，创建配置文件：`touch ~/.config/starship.toml`。
* **eza**:
* `ls`: 查看当前目录（带图标）。
* `ll`: 查看详细列表（带权限、大小、修改时间）。
* `ls --tree`: 树状展示目录结构。



### 5. 维护命令

```bash
brew update              # 更新 Homebrew 索引
brew upgrade starship eza # 升级工具到最新版本

```
