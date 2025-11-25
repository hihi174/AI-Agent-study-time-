# AI-Agent(study-time)

---

# **StudyMate AI Agent**

A lightweight, modular AI-powered study assistant built using a **4-step agent architecture**.
The agent takes any study request, analyzes it, breaks it into structured tasks, and returns a clean, actionable output.

This project uses:

* **Groq API** (fast LLM inference)
* **Modular agent logic** in `agent_logic.py`
* A simple CLI runner in `main.py`

---

## **🚀 Features**

* Modular agent pipeline:

  * **Task detection**
  * **Reasoning chain**
  * **Action planning**
  * **Formatted final output**
* Clear separation of concerns (`agent_logic.py` vs `main.py`)
* Error-handling for malformed model responses
* Works on **Google Colab** using Colab Secrets
* Human-readable JSON reasoning
* Easy to extend (add more task types / modes)

---

## **📁 Project Structure**

```
/
├── agent_logic.py   # Core agent: processing, validation, formatting
├── main.py          # CLI interface for running the agent
└── README.md
```

---

## **🔧 Setup Instructions**

### **1. Add your API key**

In **Google Colab**, go to:

**Project → Settings → Secrets → Add New**
Name it: `GROQ_API_KEY`
Value: *your actual key*

---

### **2. Install the OpenAI-compatible Groq SDK**

```bash
pip install groq
```

---

### **3. Run the CLI**

```bash
python main.py
```

You’ll see:

```
=== StudyMate Agent ===
Enter your study request:
```

Start typing things like:

* “Explain operating system paging”
* “Create a study plan for Java OOP revision”
* “Summarize CNN architecture”

---

## **📌 Example Usage**

**Input:**

```
Teach me memory management
```

**Output (formatted):**

```
Topic Breakdown  
→ Paging  
→ Segmentation  
→ Virtual Memory  

Warnings / Misconceptions  
→ …  
```

---

## **🛠 Add New Task Types**

To extend your agent:

1. Open `agent_logic.py`
2. Go to `task_router()`
3. Add new keywords and processing logic
   Example:

```python
elif "flashcards" in query:
    return generate_flashcards(query)
```

This makes the agent scalable and easy to grow.

---

## **❗ Troubleshooting**

### **JSONDecodeError**

If the model returns invalid JSON, the script:

* Catches the error
* Re-asks the model for valid JSON
* Continuously retries until fixed

You don’t need to manually debug malformed responses.

---

## **📜 License**

MIT License — free to use, modify, and build on.

---

## **🙏 Contributing**

Open PRs for:

* Better task modules
* Cleaner formatting
* New study modes (flashcards, quiz builder, summarizer, etc.)


Just say the word.
