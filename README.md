<h1 align="center">Welcome to arcStar: a friendly Music Bot for Discord 👋</h1>
<p>
  <img alt="Version" src="https://img-shields.io/badge/version-1.0-blue.svg?cacheSeconds=2592000" />
</p>

## Description
arcStar 🤖 is a feature-rich and reliable Discord music bot built with Python and discord.py. It allows users to stream and listen to their favorite music from YouTube directly within a voice channel on their Discord server 🎶. The bot is designed for easy deployment and continuous uptime, containerized with Docker and featuring a lightweight Flask server to stay active on free hosting platforms like Render.

## Features ✨
- Seamless YouTube Streaming 📺: Play any song from YouTube by simply using a search query with the /play command.
- Robust Queueing System 🎵: Add multiple songs to the queue to keep the music going without interruption.
- Full Playback Control ⏯️: Manage your listening session with intuitive slash commands, including /pause, /resume, /skip, and /stop.
- Asynchronous & Efficient ⚡: Built on asyncio to handle multiple requests efficiently without blocking.
- Always-On Design 💡: Includes a simple web server to integrate with uptime monitoring services (like UptimeRobot), preventing the bot from sleeping on free hosting tiers.

## Installation and Local Setup 🚀

To get a local copy of arcStar up and running, follow these steps.

### **Prerequisites**

* **Discord Account:** You'll need a Discord account to create a bot.
* **Git:** You'll need Git to clone the repository.
* **Docker:** You must have Docker installed and running on your machine. You can download it from the [official Docker website](https://www.docker.com/products/docker-desktop/).

### **Step-by-Step Guide**

1.  **Create a Discord Bot** 🤖
    Before you can run the bot, you need to create it on Discord's Developer Portal.

    * Go to the [Discord Developer Portal](https://discord.com/developers/applications) and log in.
    * Click **"New Application"** and give it a name (e.g., "arcStar").
    * Navigate to the **"Bot"** tab on the left.
    * Click **"Add Bot,"** then **"Yes, do it!"**
    * Under the bot's username, click **"Reset Token"** to reveal your bot's token. **Copy this token** and keep it safe; you'll need it for your `.env` file.
    * Enable the **"Message Content Intent"** under the "Privileged Gateway Intents" section. This is required for the bot to function correctly.
    
2.  **Invite the Bot to Your Server** ✉️
    * Go to the **"OAuth2"** tab and then **"URL Generator."**
    * Select the `bot` and `applications.commands` scopes.
    * In the "Bot Permissions" box that appears, select the following permissions: **"Send Messages," "Connect,"** and **"Speak."**
    * Copy the generated URL at the bottom, paste it into your browser, and invite the bot to your desired server.

3.  **Clone the Repository** 📂
    ```bash
    git clone [https://github.com/alan-leal/arcStar.git](https://github.com/alan-leal/arcStar.git)
    cd arcStar
    ```

4.  **Create Environment File** 🔑
    Create a file named `.env` in the root of the project directory. This file will store your secret credentials. Add the variables you just obtained:
    ```ini
    DISCORD_TOKEN=your_discord_bot_token_here
    USER_AGENT=your_browser_user_agent_string_here
    ```

5.  **Add Cookies File** 🍪
    Place your `cookies.txt` file (exported from your browser) in the root of the project directory. Remember to add `cookies.txt` to your `.gitignore` file to keep it private!

6.  **Build the Docker Image** 🛠️
    This command packages the bot and its dependencies. The `-t arcstar-bot` part gives your image a memorable name.
    ```bash
    # Build the image from the Dockerfile
    docker build -t arcstar-bot .
    ```

7.  **Run the Bot** ▶️
    This command starts a container from the image you just built.
    ```bash
    # Run the container in the background
    docker run --env-file .env -d --name arcstar-container arcstar-bot
    ```
    * `--env-file .env` securely passes your credentials from the `.env` file to the bot.
    * `-d` runs the bot in the background.
    * `--name arcstar-container` gives the running container a name for easy management.

## Author

👤 **Alan Leal**

* Github: [@alan-leal](https://github.com/alan-leal)
* LinkedIn: [@leal-alanj](https://linkedin.com/in/leal-alanj)