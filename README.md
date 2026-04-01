# VPS面板安装配置教程 | aaPanel/宝塔/1Panel

[![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/CG-spring/vps-panel-tutorial.svg?style=flat-square)](https://github.com/CG-spring/vps-panel-tutorial/stargazers)

> VPS面板安装配置教程 - aaPanel、宝?BT.cn)?Panel一键安装与详细配置指南
> 
> 持续更新?| 最后更? 2026-03-31

**中文** | **[English](README_EN.md)**

---

## 目录

- [为什么使用面板？](#为什么使用面?
- [aaPanel 安装配置](#aapanel-安装配置)
- [宝塔面板安装配置](#宝塔面板安装配置)
- [1Panel 安装配置](#1panel-安装配置)
- [面板安全设置](#面板安全设置)
- [常用功能配置](#常用功能配置)
- [常见问题](#常见问题)

---

## 为什么使用面板？

### 面板优势

| 功能 | 手动配置 | 使用面板 |
|------|----------|----------|
| 安装网站 | 30分钟+ | 1分钟 |
| 配置SSL | 10分钟 | 30?|
| FTP管理 | 需要配?| 内置 |
| 数据库管?| 命令?| 可视?|
| 文件管理 | 命令?| 可视?|

### 主流面板对比

| 面板 | 特点 | 推荐?|
|------|------|--------|
| **aaPanel** | 免费，功能全，国际版 | ⭐⭐⭐⭐?|
| **宝塔** | 中文界面，国内用户多 | ⭐⭐⭐⭐ |
| **1Panel** | 新一代，开源免?| ⭐⭐⭐⭐?|

---

## aaPanel 安装配置

### 1. 一键安?aaPanel

```bash
# CentOS 系统
yum install -y wget && wget -O install.sh http://www.aapanel.com/install/install.sh && echo "y" | bash install.sh

# Ubuntu/Debian 系统
wget -O install.sh http://www.aapanel.com/install/install.sh && sudo bash install.sh
```

### 2. 安装过程中的选项

```
请选择安装目录 (默认 /www):
/www

请选择面板端口 (默认 8888):
8888

请设置管理员用户?
admin

请设置管理员密码:
your_password

安装完成后访?
http://your_vps_ip:8888
```

### 3. 安装 LNMP/LEMP 环境

```bash
# 登录面板后，在软件商店安?# 推荐安装:
# - Nginx (Web服务?
# - MySQL/MariaDB (数据?
# - PHP (运行环境)
# - phpMyAdmin (数据库管?
```

### 4. 创建网站

```
1. 登录 aaPanel
2. 点击 "Website" -> "Add site"
3. 填写域名和FTP信息
4. 选择 PHP 版本
5. 点击 "Submit"
```

### 5. 配置 SSL 证书

```
1. 点击网站 -> "SSL"
2. 选择 "Let's Encrypt"
3. 填写邮箱
4. 点击 "Apply"
5. 开?"Force HTTPS"
```

---

## 宝塔面板安装配置

### 1. 一键安装宝?
```bash
# CentOS 系统
yum install -y wget && wget -O install.sh https://download.bt.cn/install/install_6.0.sh && sh install.sh

# Ubuntu/Debian 系统
wget -O install.sh https://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh
```

### 2. 安装注意事项

```
⚠️ 安装前请确保:
- 系统干净 (新装系统)
- 端口 8888, 888, 80, 443 已开?- 内存建议 2GB 以上
```

### 3. 初始化配?
```bash
# 安装完成后显示以下信?
Bt-Panel: http://your_vps_ip:8888
Username: admin
Password: your_password

# 首次登录需?
1. 绑定宝塔账号 (可跳?
2. 选择安装套件 (LNMP/宝塔极速安?
3. 等待安装完成
```

### 4. 常用功能

| 功能 | 说明 |
|------|------|
| 网站管理 | 一键创?管理网站 |
| FTP | 创建FTP账户 |
| 数据?| MySQL管理 |
| 文件管理 | 可视化文件操?|
| SSL | 免费HTTPS证书 |
| 计划任务 | 备份/定时任务 |

---

## 1Panel 安装配置

### 1. 1Panel 介绍

| 特点 | 说明 |
|------|------|
| 开源免?| GitHub开?|
| 现代UI | 界面美观 |
| Docker支持 | 容器管理 |
| 命令?| 提供1pctl命令 |

### 2. 一键安?1Panel

```bash
# CentOS
curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && bash quick_start.sh

# Ubuntu
curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sudo bash quick_start.sh
```

### 3. 安装选项

```
选择安装目录 (/opt/1panel):
/opt/1panel

设置面板端口 (随机):
(随机端口，请记录)

设置管理员用户名:
admin

设置管理员密?
your_password

安装完成?
1Panel 控制? http://your_vps_ip:随机端口
```

### 4. 使用 1Panel

```bash
# 命令行管?1pctl user-info    # 用户信息
1pctl restart     # 重启面板
1pctl stop        # 停止面板
1pctl update      # 更新面板

# Web界面功能
- 应用商店 - 一键安装应?- 网站 - 创建管理网站
- 数据?- MySQL/PostgreSQL
- 容器 - Docker管理
- 备份 - 定时备份
```

---

## 面板安全设置

### 1. 修改默认端口

```bash
# aaPanel
# 面板设置 -> 修改面板端口

# 宝塔
# 面板设置 -> 修改面板端口

# 1Panel
1pctl reset panel-port 22222
```

### 2. 绑定域名访问

```bash
# 建议只绑定域名访?# 宝塔: 面板设置 -> 域名绑定
# aaPanel: 面板设置 -> Domain Binding
```

### 3. 开启面板SSL

```bash
# 宝塔: 面板设置 -> 面板SSL -> Let's Encrypt
# aaPanel: 面板设置 -> Panel SSL
# 1Panel: 面板设置 -> SSL证书
```

### 4. IP白名?
```bash
# 宝塔: 面板设置 -> IP白名?# aaPanel: 面板设置 -> IP Whitelist
```

### 5. 禁用密码登录 (推荐使用密钥)

```bash
# 宝塔: 面板设置 -> SSH管理 -> 关闭密码登录
```

---

## 常用功能配置

### 1. 配置 PHP

```bash
# 调整 PHP 上传限制
# 宝塔/aaPanel: PHP管理 -> 上传限制 -> 100MB

# 调整 PHP 内存限制
# PHP管理 -> memory_limit -> 256M

# 开?PHP 扩展
# PHP管理 -> 扩展 -> 勾选需要的扩展
```

### 2. 配置 Nginx

```nginx
# 宝塔/aaPanel: 配置文件
# 添加以下内容优化性能

# Gzip压缩
gzip on;
gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

# 缓冲?client_body_buffer_size 10k;
client_header_buffer_size 1k;
client_max_body_size 100m;
large_client_header_buffers 4 16k;
```

### 3. 配置 MySQL

```sql
-- 优化 MySQL 配置
-- 宝塔/aaPanel: 数据?-> phpMyAdmin -> my.ini

[mysqld]
max_connections = 200
key_buffer_size = 64M
max_allowed_packet = 64M
table_open_cache = 256
sort_buffer_size = 2M
read_buffer_size = 2M
read_rnd_buffer_size = 4M
myisam_sort_buffer_size = 32M
```

### 4. 配置计划任务

```
# 宝塔/aaPanel: 计划任务

# 备份网站 (每天凌晨3?
任务类型: 备份网站
执行周期: 每天 3:00
保留: 3?
# 备份数据?(每天凌晨4?
任务类型: 备份数据?执行周期: 每天 4:00
保留: 7?```

---

## 常见问题

### Q1: 面板无法访问?
| 原因 | 解决方法 |
|------|----------|
| 端口未开?| 检查防火墙 |
| 服务未启?| 重启面板服务 |
| 内存不足 | 交换分区或重?|

```bash
# 重启面板服务
# 宝塔
bt restart

# aaPanel
btnginx restart

# 1Panel
1pctl restart
```

### Q2: 忘记面板密码?
```bash
# 宝塔: 宝塔终端输入
bt 5

# aaPanel
btapi

# 1Panel
1pctl reset panel-password
```

### Q3: 如何迁移网站?
```
1. 打包原网站文?2. 导出数据?3. 上传到新服务?4. 导入数据?5. 修改网站配置
6. 配置域名解析
```

---

## 推荐 VPS

| 名称 | 特点 | 价格 | 链接 |
|------|------|------|------|
| **VPSVIP** | VPS主机测评 | 服务器评测与推荐 | [官网](https://vpsvip.net) |
| **Vultr** | 按小时计费，全球节点 | $3.5/月起 | [官网](https://vultr.com) |
| **BandwagonHost** | 性价比高 | $49.99/?| [官网](https://bandwagonhost.com) |

---

## License

[CC BY-NC-SA 4.0](LICENSE) - 2026

---

<p align="center">
  <a href="https://vpsvip.net">VPSVIP</a> |
  <a href="https://clashvip.net">ClashVIP</a> |
  <a href="https://clashhub.net">ClashHub</a>
</p>

---

> 更多 VPS & Clash 工具，请查看 [Awesome VPS & Clash Tools](https://github.com/CG-spring/awesome-vps-clash-tools) 精选合集
