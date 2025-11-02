# 🛡️ Personal Secure File Bot (aiogram)  
[中文说明](README_cn.md)

A private **Telegram file storage bot** built with **[aiogram 3.x](https://docs.aiogram.dev/)**.  
It securely accepts messages, pictures, videos, and documents **only from a specific Telegram user**,  
then saves them to a local storage folder.  

You can search, retrieve, delete, and summarize your stored files — all via Telegram commands.

[How to create a telegram bot](https://core.telegram.org/bots/tutorial)

---

## ✨ Features

✅ **Access Control** — Only a pre-defined `user_id` can use the bot.  
✅ **Auto Storage** — Automatically saves text, pictures, videos, and documents locally.  
✅ **Supports All Formats** — JPG, PNG, WEBP, MP4, AVI, MOV, and more.  
✅ **Search & Retrieve** — Quickly find and fetch any stored file.  
✅ **Delete Command** — Remove specific files from storage.  
✅ **Overview Command** — View all saved files, sizes, and timestamps.  
✅ **Future-Ready** — Easily extendable for OpenAI or 3rd-party API integration.

---

## 🧰 Installation

### 1. Clone this repo

```bash
git clone https://github.com/yourusername/secure-file-bot.git
cd secure-file-bot
```
### 2. Install dependencies
```
pip install aiogram==3.13
```

### 3. Set up configuration
Open the Python script (secure_file_bot_aiogram.py) and update these constants:
```
BOT_TOKEN = "YOUR_BOT_TOKEN_HERE"      # Get it from @BotFather
AUTHORIZED_USER_ID = 123456789         # Your personal Telegram user ID
STORAGE_DIR = "local_storage"          # Folder where files are saved
```

## 🚀 Run the Bot
```
python bot.py
```
Once running, open your bot in Telegram and type:
```
/start
```
## 💬 Commands
Command	Description

| Command                            | Description                              |
| ---------------------------------- | ---------------------------------------- |
| `/start`                           | Initialize bot and create storage folder |
| `/overview`                        | Show summary of all stored files         |
| `/search <keyword>`                | Search for a file by name                |
| `/get <number>`                    | Retrieve a file from search results      |
| `/delete <filename>`               | Delete matching file(s)                  |
| *(Send any text, image, or video)* | Automatically saved to local storage     |

## 🧠 How It Works

* When you send text → stored as .txt
* When you send a picture → auto-detects MIME type (JPG, PNG, WEBP, etc.)
* When you send a video → auto-detects format (MP4, AVI, MOV, etc.)
* When you send a document → saved using its original name and MIME extension
* Everything is organized in your local_storage/ folder

## 🧩 Example Folder Structure
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

