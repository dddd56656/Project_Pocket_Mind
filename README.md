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
docker exec -it ollama /bin/bash
ollama create qwen-q2k -f local_models/Modelfile

```

### 3. 开始对话
打开浏览器访问: [http://localhost:3000](http://localhost:3000)

1. 注册管理员账号（本地存储）。
2. 在设置中导入模型：
   - 基础模型路径填: `/root/local_models/unsloth.Q4_K_M.gguf`

ps: 如果有其它模型，直接在dockerfile挂载的文件夹中直接放入并修改Modelfile，进入容器执行create命令，之后到ui界面进行导入
---

<details>
<summary><strong>🤝 Open for Work / 寻求工作 / 求職中 (Click to expand)</strong></summary>

<br>

**🇨🇳 中文**
> 说实话，我已经失业一年了。这一年很难熬，但我没让自己闲着。
> 我现在的状态是：缺钱，但不缺技术。
> 我需要一份工作，无论是 远程 (Remote)、外包 (Contract) 还是 全职 (Full-time)。
> 只要能解决温饱，我就能干。如果您团队需要一个立刻就能上手干活的人，请联系我。

**🇺🇸 English**
> To be honest, I have been out of work for a year. It has been a challenging year, but I have used this time to keep my technical skills sharp.
> My current status: Short on funds, but solid on technology.
> I am looking for any employment opportunity: Remote, Contract, or Full-time.
> I am willing to accept any role that covers basic living expenses.
> If your team needs an immediate contributor who can start right away, please contact me.

**🇯🇵 日本語**
> 正直なところ、1年間失業しています。厳しい一年でしたが、その間も技術の研鑽は怠っていません。
> 現状は、資金不足ですが、技術力には自信があります。
> リモート、業務委託、正社員を問わず、仕事を探しています。
> 生活費が賄えるのであれば、どのような案件でも引き受けます。
> チームに即戦力を必要とされている方は、ぜひご連絡ください。

<br>
**📍 Location:** Yueyang, Hunan, China (中国 湖南岳阳)
**📧 Contact:** sww1248002362@163.com | **WeChat:** sww1248002362

</details>    

