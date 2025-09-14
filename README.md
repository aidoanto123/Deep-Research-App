# 🧠 Deep Research

Deep Research is an AI-powered pipeline for automated web research, report generation, and email delivery.  
It leverages multiple specialized agents (planner, searcher, writer, and emailer) to turn a simple query into a **detailed, structured research report** — and even send it straight to your inbox.

---

## 🚀 Features

- **Interactive UI** powered by [Gradio](https://gradio.app/)  
- **Planner Agent** – breaks down queries into the most relevant web searches  
- **Search Agent** – performs concise web research summaries  
- **Writer Agent** – synthesizes search results into a **5–10 page markdown report**  
- **Email Agent** – formats and delivers the report as an HTML email  
- **Tracing & Debugging** with OpenAI’s tracing tools  
- Fully **async** architecture for faster research workflows  

---

## 📂 Project Structure

deep_research.py: Main Gradio interface for running research queries



research_manager.py: Orchestrates the entire research workflow



planner_agent.py: Plans the best web searches



search_agent.py: Executes searches and summarizes findings



writer_agent.py: Writes a detailed research report



email_agent.py: Sends formatted report via email



agents/: Directory containing shared agent logic (Agent, Runner, tools, etc.)
---

# `🛠️ Setup Instructions`

### `Create & activate a virtual environment`
~~~bash
python -m venv .venv
source .venv/bin/activate   # macOS/Linux
.venv\Scripts\activate      # Windows
~~~

### `Install dependencies`
~~~bash
pip install -r requirements.txt
~~~

### `Set environment variables`
Create a `.env` file in the project root:
~~~env
OPENAI_API_KEY=your_openai_api_key
SENDGRID_API_KEY=your_sendgrid_api_key
~~~

---

# `▶️ Usage`

### `Launch the research app`
~~~bash
python deep_research.py
~~~

This will:
- Open the Gradio UI in your browser.
- Prompt you for a research query.
- Show live progress updates:
  - Planning searches
  - Running web searches
  - Writing a report
  - Sending email
- Display the final markdown report in the UI.

---

# `📧 Email Reports`

The `Email Agent` automatically sends a formatted version of the research report.

### `Configure sender and recipient addresses` (in `email_agent.py`)
~~~python
from_email = "your_verified_sender@example.com"
to_email = "recipient@example.com"
~~~

⚠️ You must have a [verified sender in SendGrid](https://docs.sendgrid.com/ui/sending-email/senders) for emails to be delivered.

---

# `🔍 Example Workflow`

### `Enter`
~~~text
"What are the latest developments in quantum computing applications for cybersecurity?"
~~~

### `The system will`
- Plan 5 relevant web searches
- Fetch and summarize findings
- Generate a long-form research report (5–10 pages) in markdown
- Send the report as a well-formatted HTML email

---
