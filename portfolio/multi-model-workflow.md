# Multi‑Model Workflow: Planner + Coder Architecture

This case study documents my experiments with a two‑model workflow:  
a **Planner model** for high‑level reasoning and architecture, and a **Coder model** for implementation and debugging.

It was inspired by the idea that different models have different strengths — and that combining them might produce better results than relying on a single model.

The reality was more complicated, and far more educational.

---

## 🧠 The Setup

I used two local models running through Ollama:

- **Planner:** Llama 3.3 70B (architecture, reasoning, design)
- **Coder:** Qwen 2.5 Coder 32B (implementation, debugging, file edits)

My workflow configuration looked something like this:

- Planner handles architecture, design review, and high‑level reasoning  
- Coder handles implementation, debugging, and file edits  
- Manual task switching  
- Verbose logging  
- Confirm‑before‑writing enabled  

The idea was simple:  
**Let the Planner think, let the Coder build.**

---

## 🔍 What I Expected

I expected:

- Cleaner architecture  
- Fewer hallucinations  
- Better separation of concerns  
- More stable code generation  
- A smoother development flow  

And in some cases, I did get that.

But the real lessons came from what *didn’t* work.

---

## ⚠️ What Went Wrong (and Why)

### **1. The Planner hallucinated structure**
Large models sometimes “over‑plan,” inventing:

- Files that didn’t exist  
- Components I never asked for  
- Entire architectures that didn’t match the project  

### **2. The Coder followed the hallucinations**
The Coder model would try to implement whatever the Planner said — even if it was wrong.

This created a feedback loop of confusion.

### **3. Context drift became a real problem**
The more the Planner talked, the more it drifted from the original requirements.

### **4. Debugging became harder, not easier**
Instead of debugging code, I was debugging:

- Model disagreements  
- Conflicting instructions  
- Missing files  
- Incorrect assumptions  

### **5. Bigger models ≠ better results**
This was one of the biggest lessons.

Large models:

- Hallucinate more  
- Drift more  
- Over‑generalize  
- Try to be “creative” when I needed them to be precise  

---

## 🧠 What I Learned

### **1. Simplicity wins**
A single strong coder model with a tight prompt often outperformed the two‑model setup.

### **2. Human oversight is essential**
I had to:

- Correct the Planner  
- Override the Coder  
- Re‑align the architecture  
- Re‑prompt both models  

### **3. Multi‑model workflows need strict constraints**
Without guardrails, the Planner becomes a novelist.

### **4. AI is a collaborator, not an autopilot**
The best results came when I treated the models as assistants, not decision‑makers.

---

## 🛠️ What I’d Try Next

- Add a **verification model** to check Planner output  
- Add a **critic model** to evaluate code before execution  
- Use **smaller models** for more predictable behavior  
- Add a **debugger agent** to analyze runtime errors  
- Build a **prompt library** for consistent instructions  

---

## 📦 Related Repository

This workflow was used while building:

https://github.com/LabNotesAI/ReactMongoAI
