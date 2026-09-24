# PHP 代码审计学习笔记

## 📌 项目简介

本仓库用于记录我学习 **PHP 代码审计** 的完整历程。包含从零搭建 Web 环境、部署 CMS 靶场、使用自动化工具扫描、到最后人工追踪数据流并验证漏洞的详细实战笔记。

## 🛠 环境与工具

- **运行环境**：Windows 11 + phpStudy（Nginx + MySQL + PHP 7.3.4）
- **靶场源码**：MacCMS（苹果CMS v10）
- **审计工具**：Seay 源代码审计系统
- **编辑工具**：Visual Studio Code
- **辅助工具**：CMD 命令行（`findstr` 全局代码检索）

## 📂 目录结构

```text
php-code-audit-notes/
├── README.md                      # 项目说明文件
├── day1-php-audit.md              # Day 1: 环境搭建与 HTTP_REFERER 漏洞追踪
└── screenshots/                   # 实验过程截图
    ├── 01-seay-scan.png           # 图 1：Seay 扫描结果
    ├── 02-vulnerable-code.png     # 图 2：All.php 函数调用点
    └── 03-vulnerable-function.png # 图 3：common.php 函数定义点（漏洞根源）
```

## 📅 学习进度

- ☑ **Day 1（2026-09-24）**：搭建 PHP 环境、部署 MacCMS、安装 Seay，完成第一个漏洞（`HTTP_REFERER` 伪造）的追踪与研判。
- ☐ **Day 2**：待更新。

## 🎯 学习目标

1. 掌握 PHP 常见高危漏洞（SQL 注入、文件上传、命令执行、文件包含等）的审计方法。
2. 能够从「自动化工具扫描告警」进阶到「人工精准验证数据流」。
3. 积累真实 CMS 源码的审计实战经验。

## 🧠 核心收获记录

- **环境搭建**：学会了使用 phpStudy 快速部署 Nginx + MySQL + PHP 环境，并成功安装 MacCMS 靶场。
- **安全加固**：在部署完成后，通过重命名 `admin.php`（后台入口）来降低被扫描器批量识别的风险。
- **杀软对抗**：解决了 Windows Defender 对安全审计工具（Seay）的误报拦截，掌握了添加文件夹白名单的操作。
- **数据流追踪**：利用 `findstr` 命令行工具，成功追踪 `mac_get_refer()` 函数至 `All.php` 和 `Collect.php`，理解了自动化工具报「误报」的原理，并精准定位到了潜在的注入点。

## 📖 笔记索引

| 日期 | 笔记 | 主题 |
| --- | --- | --- |
| Day 1 | [day1-php-audit.md](day1-php-audit.md) | 环境搭建与 `HTTP_REFERER` 漏洞追踪 |

## ⚠️ 免责声明

本仓库中涉及的所有安全技术、Payload 及漏洞分析内容，仅供网络安全学习和研究使用。

**严禁**利用本仓库中的技术对互联网上未经授权的任何真实网站或系统进行测试！任何非法使用造成的后果均由使用者自行承担。维护网络安全，人人有责。
