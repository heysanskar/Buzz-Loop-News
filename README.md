⚡ Buzz Loop News
<br>
🤖 Local AI-Powered News Fetcher & Email Briefing
<br>
Buzz Loop News is a Python-based automated news aggregation and AI summarization application.<br>
It fetches the latest headlines from multiple RSS news sources, processes them using Mistral through Ollama, generates a short Gen Z-style news briefing, and delivers the generated briefing directly to an email inbox.<br>

The project combines RSS feed parsing, local AI inference, prompt engineering, Python automation, and SMTP email delivery into a single workflow.<br>

<br>
🚀 Features
<br>
📰 Fetch news from multiple RSS sources<br>
🌐 Aggregate headlines from different news publishers<br>
🔄 Automatically retrieve the latest available headlines<br>
🤖 Use Mistral locally through Ollama<br>
🧠 AI-powered news summarization<br>
⚡ Generate a quick news briefing<br>
📋 Generate 8–10 important news updates<br>
🔥 Generate a Gen Z-style presentation of the news<br>
🎯 Generate a final one-sentence "Vibe Check"<br>
📧 Automatically send the generated briefing through email<br>
🔐 Use Gmail SMTP for email delivery<br>
🏠 Run AI processing locally without an external AI API<br>
<br>
🧠 How It Works
<br>
The application follows this pipeline:<br>
Multiple RSS News Sources
          │
          ▼
      Feedparser
          │
          ▼
     News Headlines
          │
          ▼
   Mistral via Ollama
          │
          ▼
   AI News Briefing
          │
          ▼
      Gmail SMTP
          │
          ▼
      Email Inbox

<br>
📰 News Sources
<br>
The application currently fetches news from multiple RSS feeds:<br>
🌐 Google Top News<br>
🌍 BBC World News<br>
💻 TechCrunch<br>

<br>
The application retrieves the top 3 articles from each configured source.<br>

The collected headlines are then combined and passed to the local AI model for processing.<br>

<br>
🔄 Application Workflow
<br>
1. 📰 Fetch News
<br>
The application connects to the configured RSS feeds using Feedparser.<br>
It collects the top 3 available articles from each configured source.<br>

The headlines are then combined into a single text dataset for AI processing.<br>

<br>
2. 🤖 Local AI Processing
<br>
The collected headlines are sent to Mistral running locally through Ollama.<br>
The model analyzes the headlines and rewrites them into a short, engaging news briefing.<br>

<br>
The prompt instructs the model to use a casual Gen Z-style presentation with phrases such as "lowkey", "highkey", "no cap", "cooked", "ate", and similar expressions.<br>

<br>
3. ⚡ Generate News Briefing
<br>
The AI generates:<br>
📝 A short and catchy briefing title<br>
📰 8–10 summarized news updates<br>
🎯 A final one-sentence "Vibe Check"<br>

<br>
4. 📧 Email Delivery
<br>
The generated briefing is sent using Python's SMTP email functionality.<br>
The application connects to Gmail's SMTP server using TLS and sends the generated briefing to the configured recipient.<br>

<br>
🛠️ Tech Stack
<br>
Technology	Purpose
Python	Application development and automation
Feedparser	RSS feed parsing
Ollama	Local LLM runtime
Mistral	AI-powered news summarization
SMTP	Email delivery
Gmail SMTP	Email server
smtplib	Python email communication
MIME	Email message formatting

<br>
📂 Project Structure
<br>
buzz-loop-news/
│
├── main.py
├── news_fetcher.py
├── config.example.py
├── requirements.txt
├── README.md
├── .gitignore
└── LICENSE

<br>
📄 File Description
<br>
main.py — Controls the main application workflow and handles email delivery.<br>
news_fetcher.py — Fetches RSS headlines and processes them using the local Mistral model.<br>

config.example.py — Provides an example configuration file without exposing email credentials.<br>

requirements.txt — Contains the Python dependencies required by the project.<br>

README.md — Project documentation and setup instructions.<br>

.gitignore — Prevents sensitive and unnecessary files from being uploaded to GitHub.<br>

LICENSE — Defines the terms under which the project can be used and distributed.<br>

<br>
⚙️ Installation
<br>
📋 Prerequisites
<br>
Make sure you have the following installed:<br>
🐍 Python 3.9+<br>
🤖 Ollama<br>
🦙 Mistral model<br>
📦 pip<br>
🌐 Git<br>
📧 Gmail account with an App Password<br>

<br>
1. Clone the Repository
<br>
git clone https://github.com/heysanskar/buzz-loop-news.git
cd buzz-loop-news

<br>
2. Create a Virtual Environment
<br>
python -m venv venv

<br>
Windows:<br>
venv\Scripts\activate

<br>
macOS / Linux:<br>
source venv/bin/activate

<br>
3. Install Dependencies
<br>
pip install -r requirements.txt

<br>
4. Install Mistral Using Ollama
<br>
Make sure Ollama is installed and running.<br>
Download the Mistral model using:<br>

ollama pull mistral

<br>
Verify that the model is available:<br>
ollama list

<br>
You can also test the model with:<br>
ollama run mistral

<br>
5. Configure Email
<br>
Create a local file named config.py in the project directory.<br>
Use the following structure:<br>

SENDER_EMAIL = "your-email@gmail.com"
SENDER_PASSWORD = "your-gmail-app-password"
RECEIVER_EMAIL = "receiver-email@gmail.com"

SMTP_SERVER = "smtp.gmail.com"
SMTP_PORT = 587

<br>
⚠️ Do not upload config.py to GitHub.<br>
Your .gitignore file should contain:<br>

config.py
.env
venv/
__pycache__/
*.pyc

<br>
The repository includes config.example.py as a safe configuration template.<br>
<br>
6. Run the Application
<br>
Run the following command:<br>
python main.py

<br>
The application will perform the following steps:<br>
1/3 — Fetch news from RSS sources<br>

2/3 — Process the headlines using Mistral through Ollama<br>

3/3 — Deliver the generated briefing through email<br>

<br>
📧 Email Automation
<br>
Buzz Loop News uses Python's built-in SMTP functionality to deliver the generated news briefing.<br>
The application connects to Gmail using:<br>

🔐 TLS encryption<br>
📧 Gmail SMTP<br>
🔑 Gmail App Password authentication<br>

<br>
The default email subject is:<br>

⚡ Your Daily Buzz Loop Briefing<br>

<br>
The email contains the AI-generated news briefing produced by Mistral.<br>

<br>
🔒 Privacy & Security
<br>
Buzz Loop News uses a local-first AI architecture for news summarization.<br>
The news summarization process runs locally through Ollama and Mistral.<br>

No external AI API key is required for the AI processing component.<br>

<br>
However, the application uses Gmail SMTP to deliver the final briefing to the configured email address.<br>

<br>
⚠️ Security Recommendations
<br>
🔐 Never commit config.py to GitHub.<br>
🔑 Never expose your Gmail App Password.<br>

🚫 Do not hard-code credentials directly into public source code.<br>

📁 Keep sensitive configuration files inside .gitignore.<br>

🔄 If credentials are accidentally exposed, revoke them immediately and create new credentials.<br>

<br>
🎯 Project Objective
<br>
The objective of Buzz Loop News is to automate personal news consumption using RSS feeds, local AI, and email automation.<br>
Instead of manually checking multiple news sources, the application collects headlines from different publishers and uses a local LLM to generate a concise news briefing.<br>

<br>
The final briefing is automatically delivered to the user's email inbox.<br>

<br>
The project demonstrates how a local LLM can be integrated into a practical Python automation workflow without requiring a cloud-based AI API.<br>

<br>
⭐ Key Highlights
<br>
📰 Multi-source RSS news aggregation<br>
🔄 Automated headline collection<br>

🤖 Local Mistral LLM integration using Ollama<br>

🧠 Prompt engineering for news summarization<br>

⚡ Automated news briefing generation<br>

📧 SMTP-based email automation<br>

🔐 Secure credential separation using configuration files<br>

🐍 Python automation workflow<br>

🌐 RSS-based data collection<br>

📋 Multi-stage AI processing pipeline<br>

🏠 Local AI inference<br>

<br>
🔮 Future Improvements
<br>
🕐 Scheduled News Delivery — Automatically run the application at a specific time every day.<br>
📰 More News Sources — Add additional RSS-compatible news sources.<br>

🏷️ Category-Based Briefings — Add separate sections for technology, business, sports, science, and world news.<br>

🎯 Personalized News — Allow users to select preferred topics and news sources.<br>

📊 News Dashboard — Add a Streamlit dashboard for viewing generated briefings.<br>

🔍 Article Links — Include links to the original articles in the email.<br>

🧠 Improved Summarization — Detect and merge multiple headlines covering the same story.<br>

🌐 Multi-language Support — Generate news briefings in multiple languages.<br>

📱 Mobile-Friendly Email Format — Improve email formatting for mobile devices.<br>

💾 Briefing History — Store previously generated briefings locally.<br>

📈 Trending Topics — Detect trending topics across multiple news sources.<br>

🔐 Improved Credential Management — Use environment variables or a dedicated secrets manager for sensitive configuration.<br>

🧪 Automated Testing — Add unit and integration tests for RSS fetching, AI processing, and email delivery.<br>

<br>
📚 Key Concepts Demonstrated
<br>
This project demonstrates practical implementation of:<br>
RSS Feed Parsing<br>

News Aggregation<br>

Local Large Language Models (LLMs)<br>

Ollama Integration<br>

Mistral LLM Integration<br>

Prompt Engineering<br>

Text Summarization<br>

Python Automation<br>

SMTP Email Automation<br>

Gmail SMTP Integration<br>

MIME Email Formatting<br>

Exception Handling<br>

Configuration Management<br>

Local AI Inference<br>

REST-style API integration through local AI tooling<br>

<br>
👨‍💻 Author
<br>
Sanskar Aman
<br>
GitHub: https://github.com/heysanskar<br>
LinkedIn: https://www.linkedin.com/in/sanskar-a-881719248/<br>

<br>
⭐ Support
<br>
If you find Buzz Loop News useful or interesting, consider giving the repository a ⭐ on GitHub.<br>
<br>
Built with Python 🐍 + Ollama 🤖 + Mistral 🧠 + RSS 📰 + Gmail 📧
