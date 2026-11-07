# Arch Linux 个人配置一键拉取与还原

本项目用于存放个人 Arch Linux（Nyarch + Niri + Fish）环境的一键克隆与部署脚本命令。无论在新设备或是重装系统后，打开终端运行一条命令即可完成拉取与部署。

---

## ⚡ 一键拉取与部署命令

打开终端（Terminal），直接复制并运行以下整行命令：

```bash
git clone https://github.com/shenchuchu91-hub/dotfiles.git ~/dotfiles && cd ~/dotfiles && chmod +x install.sh && ./install.sh
```

> **说明**：
> - 上述命令使用标准的 `HTTPS` 协议，任何新机器均可直接拉取，**无需提前配置 SSH 密钥**。
> - 如果本机已经配置好 GitHub SSH 密钥，也可以使用 SSH 链接拉取：
>   ```bash
>   git clone git@github.com:shenchuchu91-hub/dotfiles.git ~/dotfiles && cd ~/dotfiles && chmod +x install.sh && ./install.sh
>   ```

---

## 📋 执行过程与自动处理

运行该命令后，安装脚本（`install.sh`）会自动执行以下操作：

1. **安全备份**：
   - 自动检测 `~/.config` 下现有的同名配置目录；
   - 如有旧配置，会自动备份至 `~/.config_backup_当前时间/`，不会直接覆盖或删除任何原有数据。

2. **建立软链接**：
   - 自动将 `~/dotfiles/.config/` 下的各个模块（Niri、Fish、Starship、Fastfetch、Kitty、Foot、Btop 等）软链接至用户目录对应的 `~/.config/` 位置。

3. **可选安装依赖**：
   - 脚本会提示是否需要自动安装系统依赖软件包；
   - 若确认，会自动调用 `pacman` 和 `yay`/`paru` 补齐对应工具及中文字体。

---

## 🔗 相关配置仓库

- 配置文件与源码主体：[shenchuchu91-hub/dotfiles](https://github.com/shenchuchu91-hub/dotfiles)
