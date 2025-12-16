# 🧠 Project Pocket Mind (口袋思维)

> **One-Stop Solution:** From Raw Data to Local Chatbot.
> 这是一个基于 Llama-3 的全流程私有化微调与本地部署方案。

![License](https://img.shields.io/badge/license-Apache%202.0-blue)
![Model](https://img.shields.io/badge/Model-Llama--3-green)
![Tech](https://img.shields.io/badge/Tech-Unsloth%20%7C%20Ollama%20%7C%20Docker-orange)

## 📖 项目简介

本项目演示了如何在有限算力（T4）下，通过 **Unsloth** 对 Llama-3 进行极速微调，注入私有知识，并最终在本地 Windows/Linux 环境通过 **Docker + Ollama** 进行离线部署。

## 📂 目录结构

```text
├── deploy/
│   ├── docker-compose.yml  # 一键部署脚本
│   └── local_models/       # [关键] 在这里放入你的 GGUF 模型文件
├── src/
│   └── Pocket-Mind.ipynb   # 训练笔记本
└── requirements.txt
```

## 🚀 快速开始 (本地部署)

### 1. 准备模型
下载训练好的 `unsloth.Q4_K_M.gguf`，将其放入 `deploy/local_models/` 文件夹。

### 2. 启动服务
确保已安装 Docker Desktop (Windows 需开启 WSL2)。

```bash
cd deploy
docker-compose up -d
```

### 3. 开始对话
打开浏览器访问: [http://localhost:3000](http://localhost:3000)

1. 注册管理员账号（本地存储）。
2. 在设置中导入模型：
   - 基础模型路径填: `/root/local_models/unsloth.Q4_K_M.gguf`

ps: 如果有其它模型，直接在dockerfile挂载的文件夹中直接放入即可，放入后到ui界面进行导入
---
