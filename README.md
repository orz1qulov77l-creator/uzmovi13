# Tamosho Kino Bot

This project is a Telegram movie bot built with Python and aiogram.

## Local setup

1. Create a virtual environment:
   ```bash
   python -m venv .venv
   . .venv/bin/activate  # Windows: .venv\Scripts\activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file from the example:
   ```bash
   copy .env.example .env
   ```
4. Fill in your Telegram bot token and admin IDs.
5. Run the bot:
   ```bash
   python bot.py
   ```

## Render deployment

1. Push this project to GitHub.
2. In Render, create a new Python Worker service.
3. Connect the GitHub repository.
4. Set the start command:
   ```bash
   python bot.py
   ```
5. Add environment variables in Render:
   - `BOT_TOKEN`
   - `ADMIN_IDS`
   - `DB_PATH=/tmp/tamosho.sqlite3`
   - `LOG_LEVEL=INFO`

The included `render.yaml` file can also be used to deploy the service automatically.

## Notes

- `.env` is ignored by git and should never be committed.
- The SQLite database is created automatically on first run.
