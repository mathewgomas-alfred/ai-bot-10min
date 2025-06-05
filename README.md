# ai-bot-10min
⚡ Build your first AI chatbot in just 10 minutes using Python and OpenAI’s GPT! Clean, beginner-friendly code with step-by-step instructions — perfect for fast prototyping or learning AI automation.
 🤖 Make Your First AI Bot in 10 Minutes (with Python + GPT)

This project shows you how to build a simple AI chatbot using Python and OpenAI's GPT API — in under 10 minutes.

---

 📦 Features

- Interactive command-line chatbot
- Uses `gpt-3.5-turbo` (or `gpt-4` if available)
- Built with just Python + OpenAI
- Easily extendable to web, Telegram, or GUI apps

---

 🛠️ Requirements

- Python 3.8+
- OpenAI API key

---

 🚀 Quick Start

 1. Clone this repo

```bash
git clone https://github.com/mathewgomas-alfred/ai-bot-10min.git
cd ai-bot
```
2. Set up virtual environment
bash

python -m venv venv
```
python3 -m venv venv
```
source venv/bin/activate 
```
# Use venv\Scripts\activate on Windows

```
3. Install dependencies
bash
 create a requirements.txt file, you can: Create an empty one
```
 touch requirements.txt
 
```
pip install -r requirements.txt

```
4. Add your OpenAI API key
Create a .env file in the root directory:

ini

OPENAI_API_KEY=your-openai-key-here
```
Add Your OpenAI API Key with a .env File

✅ Step 1: Install python-dotenv
If you haven’t already, install the package that lets Python read from .env files:

bash

pip install python-dotenv

```
✅ Step 2: Create the .env File
In your project root folder, create a file named exactly .env (with no filename prefix).

```
touch .env

```
Example (Windows):

Open Notepad

Save as .env (with quotes to avoid .env.txt)

Place it in your project root

```
Then, edit the file and add your OpenAI API key like this:

OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

🔒 Replace the sk-xxxx... part with your actual OpenAI key from https://platform.openai.com/api-keys
Important: Never commit your .env file to git! Add it to .gitignore:
```
echo ".env" >> .gitignore
```
✅ Step 3: Create .env.example file for your AI bot project for Sharing.
This version is for your GitHub repo so others know what the .env should look like (but without your actual key):
 Rename to .env and paste your OpenAI API key
OPENAI_API_KEY=your-openai-api-key-here
Save this as env.example in your project root.

```
✅ Step 4: Update .gitignore
Make sure .env is listed so it never gets uploaded to GitHub.

Add this to your .gitignore (if not already):
```
.env
```
✅ Step 5: Use It in Your Code
In your bot.py, load the key like this:
from dotenv import load_dotenv
import os
load_dotenv()
openai.api_key = os.getenv("OPENAI_API_KEY")
```
🧪 Optional: Test It
To make sure the .env is working, print the key (temporarily):

print("Loaded API Key:", openai.api_key)
Then run:

python bot.py
```
You should see your key printed (just once, for testing — remove after).

🔁 Option 2: Use Open Source Model with Hugging Face (No API Key Needed)
You can use a free model like mistralai/Mistral-7B-Instruct-v0.1 via Hugging Face’s transformers library.

🪜 Steps:
Install required packages:

pip install transformers torch
```

Replace bot.py with this version:
```
from transformers import pipeline

# Load a free open-source chatbot
chatbot = pipeline("text-generation", model="mistralai/Mistral-7B-Instruct-v0.1")

print("Chatbot is ready. Type 'exit' to quit.")
while True:
    user_input = input("You: ")
    if user_input.lower() in ["exit", "quit"]:
        break
    response = chatbot(user_input, max_new_tokens=100, do_sample=True, temperature=0.7)
    print("Bot:", response[0]['generated_text'].replace(user_input, '').strip())
```
```
5. Run the chatbot
```
bash
python bot.py

🧠 Sample Interaction

```
You: Tell me a joke.
```
Bot: Why don’t skeletons fight each other? They don’t have the guts.
```
