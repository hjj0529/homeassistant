# Home Assistant Image Transcoder (zstd to gzip)

[English](#english) | [中文说明](#中文说明)

---

<div id="english"></div>

## English Description

### Project Background
Since version **2026.3.0**, the official Home Assistant image has switched to the **zstd** compression algorithm. Older Docker engines (such as Synology DSM 6.2) do not support this format, resulting in `unexpected EOF` errors during image pulls.

This project uses GitHub Actions to automatically monitor official releases and transcode images in real-time back to the traditional **gzip** format, ensuring older devices can stay up-to-date.

### Core Features
- **Fully Automated Sync**: Daily scheduled checks for official `latest` and specific version tags.
- **Lossless Transcoding**: Rebuilds the compression format to `gzip` to solve compatibility gaps.
- **Standardized Naming**: Keeps image tags perfectly consistent with the official repository.

### Quick Start
Replace the image address in your `docker-compose.yml`:

`image: ghcr.io/hjj0529/home-assistant:latest`

---

<div id="中文说明"></div>

## 中文说明

### 项目背景
自 2026.3.0 版本起，Home Assistant 官方镜像改用 zstd 压缩算法。由于旧版 Docker 引擎（如群晖 DSM 6.2 等）不支持该格式，导致拉取更新时报 unexpected EOF 错误。

本项目通过 GitHub Actions 自动监控官方发布，并将镜像实时转码回传统的 gzip 格式，确保老旧设备能够同步最新的官方版本。

### 核心功能
* 全自动同步：每日定时检查官方 latest 及具体版本号。
* 无损转码：强制将压缩格式重构为 gzip，解决兼容性断层。
* 规范命名：保持与官方镜像标签 (Tags) 完全一致。

### 快速使用
在群晖的 docker-compose.yml 中替换镜像地址：

`image: ghcr.io/hjj0529/home-assistant:latest`

---

声明 / License 本项目仅用于技术兼容性研究与个人学习使用，镜像内容归 Home Assistant 官方所有。 This project is for technical compatibility research and personal use only. All image content belongs to the official Home Assistant team.
