# 🚀 Privy.AI – Your Local, Private AI Companion

![AI Companion Logo Placeholder](https://img.shields.io/badge/Status-In_Development-orange)
![License](https://img.shields.io/badge/License-MIT-blue)
![Ollama](https://img.shields.io/badge/LLM-Ollama_Mistral-informational)
![Privacy](https://imgshields.io/badge/Data-Local_Only-red)

Privy.AI is a fully **local, private, personal AI assistant** that learns and remembers your preferences, habits, and details. It interacts via **text or voice**, provides **real-time weather and time updates** using local tool-calling, and adapts its responses to your personality—all while keeping **all data securely on your device**.

---

## ✨ Key Features

| Feature | Description | Modules Involved |
| :--- | :--- | :--- |
| 🧠 **Deep Personal Memory** | Remembers your name, hobbies, and routines. Stores all details in the local `user_data.json` file. | `memory.py` |
| ⚙️ **Function Calling (Tools)** | Leverages Mistral's advanced capabilities to intelligently execute Python functions for **real-time Weather and Time information**. | `ai_core.py`, `tools.py` |
| 🎙️ **Voice & Text Interaction** | Chat via microphone or keyboard, with text-to-speech output (`pyttsx3`) and speech-to-text input (`SpeechRecognition`). | `io_handler.py` |
| 🔒 **100% Local Privacy** | All LLM processes run via Ollama on your device; zero data is ever sent to the cloud. | Core Design |
| 🏗️ **Modular Design** | The project is structurally divided into five core modules (`config`, `memory`, `ai_core`, `io_handler`, `tools`) for ease of development and extension. | Entire Project |

---

## 🚧 Development Status

This project is currently **under active development**. We are focusing on stabilizing the multi-turn Function Calling logic and improving memory management (context pruning). Feedback and contributions are highly encouraged!

---

## 🛠️ Setup and Installation

Privy.AI relies on a **local Mistral model** served by the **Ollama** engine.

### 1. Prerequisites

* **RAM:** Minimum 8-16 GB (16+ recommended).
* **Operating System:** macOS, Linux, or Windows (WSL is highly recommended).

### 2. Ollama Installation

Install Ollama according to your OS and ensure it is running:

```bash
# macOS (Homebrew)
brew install ollama

# Linux
curl -fsSL [https://ollama.com/install.sh](https://ollama.com/install.sh) | sh

# Verify installation
ollama --version

3. Pull the Mistral Model
Pull the specific model required for Function Calling support:

ollama pull mistral

# Verify the model is listed
ollama list

4. Project Setup and Dependencies
Clone the repository and install dependencies within a Python virtual environment:

# Clone the repository
git clone [https://github.com/YourUsername/privy.ai.git](https://github.com/YourUsername/privy.ai.git)
cd privy.ai

# Create the virtual environment
python -m venv .venv

# Activate the virtual environment:
source .venv/bin/activate        # Linux/macOS
.\.venv\Scripts\activate         # Windows (PowerShell)

Install all required Python libraries (ollama, requests, speechrecognition, etc.):

pip install -r requirements.txt


Absolutely! Here is the complete README.md formatted in English, emphasizing that the project is currently in the development phase and highlighting the modular structure resulting from our process.

Markdown

# 🚀 Privy.AI – Your Local, Private AI Companion

![AI Companion Logo Placeholder](https://img.shields.io/badge/Status-In_Development-orange)
![License](https://img.shields.io/badge/License-MIT-blue)
![Ollama](https://img.shields.io/badge/LLM-Ollama_Mistral-informational)
![Privacy](https://imgshields.io/badge/Data-Local_Only-red)

Privy.AI is a fully **local, private, personal AI assistant** that learns and remembers your preferences, habits, and details. It interacts via **text or voice**, provides **real-time weather and time updates** using local tool-calling, and adapts its responses to your personality—all while keeping **all data securely on your device**.

---

## ✨ Key Features

| Feature | Description | Modules Involved |
| :--- | :--- | :--- |
| 🧠 **Deep Personal Memory** | Remembers your name, hobbies, and routines. Stores all details in the local `user_data.json` file. | `memory.py` |
| ⚙️ **Function Calling (Tools)** | Leverages Mistral's advanced capabilities to intelligently execute Python functions for **real-time Weather and Time information**. | `ai_core.py`, `tools.py` |
| 🎙️ **Voice & Text Interaction** | Chat via microphone or keyboard, with text-to-speech output (`pyttsx3`) and speech-to-text input (`SpeechRecognition`). | `io_handler.py` |
| 🔒 **100% Local Privacy** | All LLM processes run via Ollama on your device; zero data is ever sent to the cloud. | Core Design |
| 🏗️ **Modular Design** | The project is structurally divided into five core modules (`config`, `memory`, `ai_core`, `io_handler`, `tools`) for ease of development and extension. | Entire Project |

---

## 🚧 Development Status

This project is currently **under active development**. We are focusing on stabilizing the multi-turn Function Calling logic and improving memory management (context pruning). Feedback and contributions are highly encouraged!

---

## 🛠️ Setup and Installation

Privy.AI relies on a **local Mistral model** served by the **Ollama** engine.

### 1. Prerequisites

* **RAM:** Minimum 8-16 GB (16+ recommended).
* **Operating System:** macOS, Linux, or Windows (WSL is highly recommended).

### 2. Ollama Installation

Install Ollama according to your OS and ensure it is running:

```bash
# macOS (Homebrew)
brew install ollama

# Linux
curl -fsSL [https://ollama.com/install.sh](https://ollama.com/install.sh) | sh

# Verify installation
ollama --version
3. Pull the Mistral Model
Pull the specific model required for Function Calling support:

Bash

ollama pull mistral

# Verify the model is listed
ollama list
4. Project Setup and Dependencies
Clone the repository and install dependencies within a Python virtual environment:

Bash

# Clone the repository
git clone [https://github.com/YourUsername/privy.ai.git](https://github.com/YourUsername/privy.ai.git)
cd privy.ai

# Create the virtual environment
python -m venv .venv

# Activate the virtual environment:
source .venv/bin/activate        # Linux/macOS
.\.venv\Scripts\activate         # Windows (PowerShell)
Install all required Python libraries (ollama, requests, speechrecognition, etc.):

pip install -r requirements.txt
⚙️ Configuration
Before running, you must configure the external API key for the weather tool.

🔑 Set API Key (Mandatory for Weather)
The Weather function requires an API key (e.g., from OpenWeatherMap). Update config.py:

# config.py
# ...
WEATHER_API_KEY = "YOUR_API_KEY" # ⚠️ REPLACE WITH YOUR ACTUAL KEY
WEATHER_BASE_URL = "[https://api.openweathermap.org/data/2.5/weather](https://api.openweathermap.org/data/2.5/weather)"
# ...

Adjusting LLM Behavior
You can fine-tune the assistant's behavior in config.py:

# config.py

# Input Mode: True = Voice Input (TTS/STT), False = Keyboard Input
USE_VOICE_INPUT = False

# Creativity Level: Higher = More imaginative/less conservative
TEMP_DEFAULT = 0.8       

# Maximum Response Length (in tokens)
MAX_TOKENS_DEFAULT = 200

▶️ Usage
Ensure your virtual environment is active ((venv) prefix visible).

Run the main script:

python main.py


Absolutely! Here is the complete README.md formatted in English, emphasizing that the project is currently in the development phase and highlighting the modular structure resulting from our process.

Markdown

# 🚀 Privy.AI – Your Local, Private AI Companion

![AI Companion Logo Placeholder](https://img.shields.io/badge/Status-In_Development-orange)
![License](https://img.shields.io/badge/License-MIT-blue)
![Ollama](https://img.shields.io/badge/LLM-Ollama_Mistral-informational)
![Privacy](https://imgshields.io/badge/Data-Local_Only-red)

Privy.AI is a fully **local, private, personal AI assistant** that learns and remembers your preferences, habits, and details. It interacts via **text or voice**, provides **real-time weather and time updates** using local tool-calling, and adapts its responses to your personality—all while keeping **all data securely on your device**.

---

## ✨ Key Features

| Feature | Description | Modules Involved |
| :--- | :--- | :--- |
| 🧠 **Deep Personal Memory** | Remembers your name, hobbies, and routines. Stores all details in the local `user_data.json` file. | `memory.py` |
| ⚙️ **Function Calling (Tools)** | Leverages Mistral's advanced capabilities to intelligently execute Python functions for **real-time Weather and Time information**. | `ai_core.py`, `tools.py` |
| 🎙️ **Voice & Text Interaction** | Chat via microphone or keyboard, with text-to-speech output (`pyttsx3`) and speech-to-text input (`SpeechRecognition`). | `io_handler.py` |
| 🔒 **100% Local Privacy** | All LLM processes run via Ollama on your device; zero data is ever sent to the cloud. | Core Design |
| 🏗️ **Modular Design** | The project is structurally divided into five core modules (`config`, `memory`, `ai_core`, `io_handler`, `tools`) for ease of development and extension. | Entire Project |

---

## 🚧 Development Status

This project is currently **under active development**. We are focusing on stabilizing the multi-turn Function Calling logic and improving memory management (context pruning). Feedback and contributions are highly encouraged!

---

## 🛠️ Setup and Installation

Privy.AI relies on a **local Mistral model** served by the **Ollama** engine.

### 1. Prerequisites

* **RAM:** Minimum 8-16 GB (16+ recommended).
* **Operating System:** macOS, Linux, or Windows (WSL is highly recommended).

### 2. Ollama Installation

Install Ollama according to your OS and ensure it is running:

```bash
# macOS (Homebrew)
brew install ollama

# Linux
curl -fsSL [https://ollama.com/install.sh](https://ollama.com/install.sh) | sh

# Verify installation
ollama --version
3. Pull the Mistral Model
Pull the specific model required for Function Calling support:

Bash

ollama pull mistral

# Verify the model is listed
ollama list
4. Project Setup and Dependencies
Clone the repository and install dependencies within a Python virtual environment:

Bash

# Clone the repository
git clone [https://github.com/YourUsername/privy.ai.git](https://github.com/YourUsername/privy.ai.git)
cd privy.ai

# Create the virtual environment
python -m venv .venv

# Activate the virtual environment:
source .venv/bin/activate        # Linux/macOS
.\.venv\Scripts\activate         # Windows (PowerShell)
Install all required Python libraries (ollama, requests, speechrecognition, etc.):

Bash

pip install -r requirements.txt
⚙️ Configuration
Before running, you must configure the external API key for the weather tool.

🔑 Set API Key (Mandatory for Weather)
The Weather function requires an API key (e.g., from OpenWeatherMap). Update config.py:

Python

# config.py
# ...
WEATHER_API_KEY = "YOUR_API_KEY" # ⚠️ REPLACE WITH YOUR ACTUAL KEY
WEATHER_BASE_URL = "[https://api.openweathermap.org/data/2.5/weather](https://api.openweathermap.org/data/2.5/weather)"
# ...
Adjusting LLM Behavior
You can fine-tune the assistant's behavior in config.py:

Python

# config.py

# Input Mode: True = Voice Input (TTS/STT), False = Keyboard Input
USE_VOICE_INPUT = False

# Creativity Level: Higher = More imaginative/less conservative
TEMP_DEFAULT = 0.8       

# Maximum Response Length (in tokens)
MAX_TOKENS_DEFAULT = 200 
▶️ Usage
Ensure your virtual environment is active ((venv) prefix visible).

Run the main script:

Bash

python main.py
Privy.AI will verify the Ollama connection and create the user_data.json file if it doesn't exist, then provide a personalized greeting.

Example Commands
"My name is Alice, and I love hiking." (Records personal info)

"What is the current time?" (Calls time function)

"What is the weather like in London?" (Calls weather function)

"What is my favorite hobby?" (Recalls stored information)

⚠️ Troubleshooting

Issue,Solution
ollama command not found,Check your system's PATH variable and Ollama installation.
PyAudio installation error,"On Linux, install portaudio (sudo apt-get install portaudio19-dev) or set USE_VOICE_INPUT = False."
Weather/Time not working,Ensure your WEATHER_API_KEY is correctly set in config.py.
Connection Error,Ensure the Ollama server is running in the background.

🤝 Contributing
Privy.AI thrives on community improvements. Feel free to fork, submit pull requests, and report issues. Priority is given to features that enhance privacy, local performance, and modularity.

📄 License
This project is released under the MIT License. It is fully open, local, private, and yours.
