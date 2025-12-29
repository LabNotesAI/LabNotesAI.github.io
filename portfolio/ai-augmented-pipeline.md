# AI‑Augmented Pipeline: Raspberry Pi → Python → LLM → MongoDB

This project started as a way to organize the huge amount of text notes I tend to dump into Notepad. Instead of letting them scatter across my system, I wanted a simple pipeline that could ingest a text file, extract meaning, and store it in a structured way.

It became my first real experience with **AI‑augmented engineering** — using local LLMs as collaborators, not replacements.

---

## 🧠 What I Built

- A **Raspberry Pi** running a lightweight Python script  
- A file‑drop system: whenever I placed a `.txt` file into a folder, the script would:
  - Parse the text  
  - Send it to a local LLM (Ollama)  
  - Ask the model for **semantic tags**  
  - Store the text + tags in **MongoDB**  

It’s simple, but it solved a real problem for me and taught me a lot about working with local models.

---

## 🔍 Why AI Was Involved

I didn’t want to manually tag or categorize notes.  
I wanted the model to:

- Identify themes  
- Suggest categories  
- Extract keywords  
- Help me search later  

This was my first time treating an LLM like a **tool in a pipeline**, not a chatbot.

---

## 🧪 What Went Right

- The Pi handled the workload surprisingly well  
- The LLM produced useful tags  
- MongoDB made searching easy  
- The whole system felt “modular” and expandable  

---

## ⚠️ What Went Wrong (and What I Learned)

- Some models hallucinated tags that didn’t exist  
- Larger models drifted or over‑generalized  
- Prompt specificity mattered more than I expected  
- I had to refine the prompt several times to stabilize output  
- I learned that **smaller models often behave more predictably**  

This was my first real lesson in **hallucination control**.

---

## 🛠️ Human‑in‑the‑Loop Debugging

Even though the model generated tags, I:

- Reviewed them  
- Corrected mistakes  
- Adjusted prompts  
- Re‑ran tests  
- Logged outputs  

This reinforced something important:  
**AI is powerful, but it still needs a human steering the ship.**

---

## 🚀 What I’d Improve Next

- Add a second model for verification  
- Add a confidence score for tags  
- Build a small UI for browsing notes  
- Add a “tag correction” workflow  
- Containerize the whole pipeline  

---

## 📦 Repository

https://github.com/LabNotesAI/NoteParserAI
