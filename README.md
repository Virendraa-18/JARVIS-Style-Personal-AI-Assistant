# JARVIS Personal AI Assistant

![HireFlow Dashboard](screenshots/dashboard.png)

> **A real-time AI assistant that can hear, see, understand, remember, and control your computer.**

JARVIS is a **cross-platform personal AI assistant** built with Python and the **Google Gemini Live API**. It combines real-time voice interaction, computer control, visual awareness, persistent memory, web search, proactive assistance, automation, and developer tools into a single JARVIS-style assistant.

The goal is simple: **build an AI assistant that feels like a persistent digital presence rather than a simple chatbot.**

---

##  Features

###  Real-Time AI Interaction

* Real-time voice conversations
* Speech-to-text and text-to-speech
* Multi-language interaction
* Hybrid voice + keyboard input
* Gemini-powered reasoning and responses

###  Computer Control

* Launch applications
* Control volume and brightness
* Wi-Fi controls
* Keyboard shortcuts
* Mouse and window control
* Desktop and taskbar operations
* Power controls

###  Vision & Screen Awareness

* Screen capture and analysis
* Webcam vision
* Visual understanding through Gemini
* Ask the assistant what is happening on your screen

###  Persistent Memory

* Stores important user preferences
* Remembers projects and context
* Session summaries
* Identity and language memory
* Remembers monitored topics
* Uses previous context to make interactions more natural

###  Proactive AI

JARVIS doesn't always wait for a command.

The proactive system can:

* Understand the current time of day
* Reference active projects
* Use recent conversation context
* Provide contextual check-ins
* Rotate conversation topics
* Avoid repetitive interactions

###  Morning Briefing

On startup, JARVIS can provide:

* Current time
* Previous session summary
* Relevant context
* Current news
* Personalized briefing

###  Web Search

Multiple search modes are supported:

```text
news
research
price
compare
search
```

Search can use Gemini Grounded Search with DuckDuckGo as a fallback.

###  Background Monitoring

Users can explicitly ask JARVIS to monitor a topic.

The assistant can:

* Check monitored topics
* Search for new developments
* Detect changed headlines
* Notify the user naturally
* Avoid repeating the same headline

###  Developer Assistant

* Code generation
* Code explanation
* Debugging assistance
* Code review
* Developer task agent

###  File Intelligence

* Read local files
* Process documents
* Summarize content
* Answer questions about files

###  Browser Control

* Open URLs
* Navigate browser tabs
* Interact with websites using voice commands

###  YouTube Control

* Search YouTube
* Play videos
* Control playback
* Use voice commands for YouTube

###  Smart Reminders

OS-native reminders using platform-specific scheduling systems.

Supported platforms include:

* Windows Task Scheduler
* macOS LaunchAgent
* Linux systemd

###  Weather

* Live weather information
* City-based weather reports
* Personalized weather responses

###  Flight Finder

* Search flight availability
* Find flight pricing information

###  Game Updater

Supports game update checks for platforms such as:

* Steam
* Epic Games

###  System Monitoring

Real-time hardware monitoring including:

* CPU usage
* RAM usage
* GPU information
* Temperature telemetry

The assistant can provide localized voice alerts when system conditions require attention.

### Messaging

Messaging functionality can be used to compose and send messages through supported platforms.

### Remote Dashboard

JARVIS includes a web-based remote dashboard that allows the assistant to be controlled remotely from another device.

QR-code pairing is supported.

### 📋 Clipboard Intelligence

Copy text and access AI-powered actions such as:

* Translate
* Summarize
* Explain
* Fix

###  Assistant Customization

The assistant name and user's name can be customized through the interface.

###  Auto Start

JARVIS can register itself with the operating system startup mechanism.

---

##  Architecture

```text
                    ┌─────────────────────┐
                    │     User Input      │
                    │ Voice / Keyboard    │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │   Gemini Live API   │
                    │  AI Conversation    │
                    └──────────┬──────────┘
                               ↓
                    ┌─────────────────────┐
                    │   Tool Dispatcher   │
                    └──────────┬──────────┘
                               ↓
       ┌───────────────┬───────┼────────┬───────────────┐
       ↓               ↓       ↓        ↓               ↓
   Computer         Vision   Memory   Web Search    Developer
    Control         Tools    System      Tools        Tools
       ↓               ↓       ↓        ↓               ↓
       └───────────────┴───────┼────────┴───────────────┘
                               ↓
                    ┌─────────────────────┐
                    │   AI Response /     │
                    │   Action Execution  │
                    └─────────────────────┘
```

---

##  Technology Stack

### Programming

* Python 3.11 / 3.12

### AI

* Google Gemini Live API
* Google Generative AI
* Real-time multimodal interaction

### Desktop / UI

* PyQt6
* PyAutoGUI
* PyGetWindow
* PyWin32
* PyCaw

### Computer Vision

* OpenCV
* MSS
* Pillow
* NumPy

### Web

* FastAPI
* Uvicorn
* Playwright
* BeautifulSoup
* DuckDuckGo Search

### Audio

* SoundDevice
* Speech-to-Text
* Text-to-Speech

### Utilities

* PSUtil
* Pyperclip
* Send2Trash
* QRCode

---

##  Project Structure

```text
JARVIS/
│
├── actions/
│   ├── background_monitor.py
│   ├── browser_control.py
│   ├── code_helper.py
│   ├── computer_control.py
│   ├── computer_settings.py
│   ├── desktop.py
│   ├── dev_agent.py
│   ├── file_controller.py
│   ├── file_processor.py
│   ├── flight_finder.py
│   ├── game_updater.py
│   ├── open_app.py
│   ├── proactive.py
│   ├── reminder.py
│   ├── screen_processor.py
│   ├── send_message.py
│   ├── system_monitor.py
│   ├── weather_report.py
│   ├── web_search.py
│   └── youtube_video.py
│
├── core/
│   ├── installer.py
│   ├── llm_client.py
│   ├── prompt.txt
│   ├── stt.py
│   └── tts.py
│
├── dashboard/
│   ├── server.py
│   └── static/
│
├── memory/
│   ├── config_manager.py
│   └── memory_manager.py
│
├── config/
│   └── ...
│
├── main.py
├── ui.py
├── setup.py
├── requirements.txt
└── readme.md
```

---

##  Installation

###  Install dependencies

```bash
pip install -r requirements.txt
```

###  Install Playwright browsers

```bash
python -m playwright install
```

### Configure your Gemini API key

Add your Gemini API configuration according to the project's configuration system.

**Never commit API keys or private credentials to GitHub.**

### Start MARK L

```bash
python main.py
```

---

##  Supported Operating Systems

JARVIS is designed for:

*  Windows 10 / 11
*  macOS
*  Linux

Some computer-control capabilities are platform-specific.

---

##  Example Commands

```text
"Open Chrome"

"What's happening on my screen?"

"Search the latest AI news"

"Increase the volume"

"What is my CPU usage?"

"Find flights to Delhi"

"Play some music on YouTube"

"Remind me tomorrow at 9 AM"

"Explain this code"

"Summarize this file"

"Monitor AI news for me"
```

---

##  Privacy & Security

JARVIS is designed as a local personal assistant, with sensitive configuration kept outside the public repository.

**Do not commit:**

```text
API keys
Passwords
Private certificates
Personal memory files
Private configuration
```

Use environment variables or local configuration files for secrets.

---

##  Roadmap

Planned improvements include:

*  Plugin system
*  Email integration
*  Calendar integration
*  More advanced memory
*  Improved autonomous task execution
*  Additional application integrations
*  Enhanced remote dashboard
*  More advanced voice interaction
*  Additional developer tools

---

##  Project Status

**Active Development / Experimental MVP**

JARVIS is a personal AI assistant project focused on exploring:

* Multimodal AI
* Voice agents
* Computer-use agents
* AI memory systems
* Autonomous task execution
* Desktop automation
* Proactive AI assistants

Some features may require additional OS-specific configuration or third-party services.

---

##  Author

**Virendra Ray**

B.Tech CSE — Artificial Intelligence & Machine Learning

---

**JARVIS Your AI assistant for the digital world.**
