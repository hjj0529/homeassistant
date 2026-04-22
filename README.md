Home Assistant Image Transcoder (zstd to gzip)English | 中文说明<div id="english"></div>English DescriptionProject BackgroundStarting from version 2026.3.0, the official Home Assistant image transitioned to the zstd compression algorithm. Older Docker engines (such as Synology DSM 6.2) do not support this format, which causes an unexpected EOF error during image pulls.This project uses GitHub Actions to monitor official releases and transcode the images back to the traditional gzip format in real-time. This ensures that legacy devices can continue to sync with the latest official versions.Core FeaturesFull Auto-Sync: Regularly checks for the official latest and specific version tags daily.Lossless Transcoding: Rebuilds the compression layers into gzip to bridge the compatibility gap.Standardized Naming: Maintains complete consistency with official image tags.Quick StartReplace the image source in your Synology docker-compose.yml:services:
  homeassistant:
    container_name: homeassistant
    image: ghcr.io/hjj0529/home-assistant:latest
    # ... other configurations
<div id="中文说明"></div>中文说明项目背景自 2026.3.0 版本起，Home Assistant 官方镜像改用 zstd 压缩算法。由于旧版 Docker 引擎（如群晖 DSM 6.2 等）不支持该格式，导致拉取更新时报 unexpected EOF 错误。本项目通过 GitHub Actions 自动监控官方发布，并将镜像实时转码回传统的 gzip 格式，确保老旧设备能够同步最新的官方版本。核心功能全自动同步：每日定时检查官方 latest 及具体版本号。无损转码：强制将压缩格式重构为 gzip，解决兼容性断层。规范命名：保持与官方镜像标签 (Tags) 完全一致。快速使用在群晖的 docker-compose.yml 中替换镜像地址：services:
  homeassistant:
    container_name: homeassistant
    image: ghcr.io/hjj0529/home-assistant:latest
    # ... 其他配置
Disclaimer / 声明本项目仅用于技术兼容性研究与个人学习使用，镜像内容归 Home Assistant 官方所有。This project is for technical compatibility research and personal use only. All image content belongs to the official Home Assistant team.
