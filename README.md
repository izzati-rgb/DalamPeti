[README.md](https://github.com/user-attachments/files/33174601/README.md)
# Masak Apa Hari Ni? 🍳

A friendly Telegram chatbot that helps you decide what Malaysian dish to cook
based on the ingredients you have at home.

---

## Features

- Suggests halal Malaysian recipes: Nasi Goreng Kampung, Sambal Telur, Ayam Masak Kicap, Tumis Kangkung Belacan, Telur Dadar Bawang
- Lists what you have and what you still need
- Gives full step-by-step instructions with heat levels and timing
- Suggests ingredient substitutes when you're missing something
- Replies in English, Bahasa Malaysia, or a mix — whatever you write

---

## Setup

### 1. Get a Telegram bot token

1. Open Telegram and search for `@BotFather`.
2. Send `/newbot` and follow the prompts.
3. Copy the token you receive.

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set your token

Copy `.env.example` to `.env`:

```bash
cp .env.example .env
```

Edit `.env` and paste your token:

```
TELEGRAM_BOT_TOKEN=your_token_here
```

### 4. Run the bot

```bash
# Load the .env file and run
export $(cat .env | xargs) && python bot.py
```

Or on Windows PowerShell:

```powershell
$env:TELEGRAM_BOT_TOKEN = "your_token_here"
python bot.py
```

---

## Files

| File | Purpose |
|---|---|
| `bot.py` | Bot logic, handlers, intent detection |
| `recipes.py` | All recipe and substitution data — edit this to add recipes |
| `requirements.txt` | Python dependencies |
| `.env.example` | Template for your environment variables |
| `.gitignore` | Excludes `.env` and other generated files |

---

## Editing recipes

Open `recipes.py`. Each recipe is a dict in `RECIPES`. Add a new key with the same fields.
Substitutions live in `SUBSTITUTIONS` — add an entry for any ingredient you want to support.

---

## Notes

- All recipes are for 2 servings, halal (no pork, no alcohol).
- The bot assumes salt, oil, sugar and water are always available.
- For food safety concerns, allergies or medical diets, the bot defers to a doctor or dietitian.
