# 🛡️ 个人专属文件机器人 (aiogram)

一个基于 **[aiogram 3.x](https://docs.aiogram.dev/)** 构建的 **私有 Telegram 文件存储机器人**。  
它只允许指定的 Telegram 用户发送消息、图片、视频和文件，并自动保存到本地文件夹中。  

你可以通过 Telegram 命令来 **搜索、获取、删除、概览** 文件，未来还可集成 OpenAI 或第三方 API。

[如何申请Telegram机器人](https://core.telegram.org/bots/tutorial)

---

## ✨ 功能特点

✅ **访问控制** — 只有配置的 `user_id` 才能使用机器人。  
✅ **自动存储** — 自动保存文本、图片、视频和文件到本地。  
✅ **支持所有格式** — JPG、PNG、WEBP、MP4、AVI、MOV 等都能识别。  
✅ **搜索与获取** — 支持关键字搜索与快速取回文件。  
✅ **删除功能** — 可通过命令删除指定文件。  
✅ **概览功能** — 查看所有文件、大小、保存时间。  
✅ **可扩展性强** — 方便未来对接 OpenAI 或其他 API。

---

## 🧰 安装步骤

### 1. 克隆项目

```bash
git clone https://github.com/yourusername/secure-file-bot.git
cd secure-file-bot
```
### 2. 安装依赖
```
pip install aiogram==3.13
```
### 3. 配置参数

打开 Python 脚本 secure_file_bot_aiogram.py，修改以下变量：
```
BOT_TOKEN = "YOUR_BOT_TOKEN_HERE"      # 从 @BotFather 获取的机器人 Token
AUTHORIZED_USER_ID = 123456789         # 你的 Telegram 用户 ID
STORAGE_DIR = "local_storage"          # 本地文件存储目录
```

## 🚀 启动机器人
```
python bot.py
```

启动后，在 Telegram 中向机器人发送：
```
/start
```

## 💬 指令说明

| 命令                | 功能                 |
| ----------------- | ------------------ |
| `/start`          | 初始化机器人并创建存储目录      |
| `/overview`       | 查看所有已保存文件的列表、大小与时间 |
| `/search <关键词>`   | 按名称搜索文件            |
| `/get <编号>`       | 从搜索结果中取回文件         |
| `/delete <文件名>`   | 删除匹配的文件            |
| *(发送文本、图片、视频或文档)* | 自动保存到本地            |


## 🧠 工作原理

* 发送文本 → 自动保存为 .txt
* 发送图片 → 自动识别并保存为正确格式（JPG、PNG、WEBP...）
* 发送视频 → 自动识别并保存为正确格式（MP4、AVI、MOV...）
* 发送文件 → 使用原文件名与 MIME 类型保存
* 所有内容都会存放在 local_storage/ 文件夹中

## 🧩 项目结构示例
```
secure_file_bot_aiogram/
├── bot.py
├── requirements.txt
├── README.md
└── local_storage/
    ├── 20251103_140501.txt
    ├── 20251103_141012.jpg
    ├── 20251103_141223.mp4
    └── ...
```
