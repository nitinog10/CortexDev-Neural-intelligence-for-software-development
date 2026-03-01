# CortexDev-Neural-intelligence-for-software-development
<p align="center">
  <b>An AI model that thinks like a developer and outputs clean, executable code.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Model-CodeGen--350M-blue"/>
  <img src="https://img.shields.io/badge/Fine--Tuning-LoRA-green"/>
  <img src="https://img.shields.io/badge/Platform-Google%20Colab-orange"/>
  <img src="https://img.shields.io/badge/Type-Code%20Generation-purple"/>
</p>

---

## 🚀 What is Cortex Dev?

**Cortex Dev** is a personalized code generation model built by fine-tuning a code-focused LLM using **LoRA (Low-Rank Adaptation)**.

Unlike prompt-based assistants, Cortex Dev is an actual trained model whose weights are modified to generate **professional, code-only outputs by default**.

✅ Fine-tuned model  
✅ Code-only generation  
✅ Consistent output  
✅ Colab-safe  

---

## ❌ Not a Chatbot  
- ❌ Not prompt engineering  
- ❌ Not a chat assistant  

## ✅ It is  
- ✅ A real fine-tuned code generation model

---

## 🎯 Why Cortex Dev Exists

| Problem | Traditional Approach | Cortex Dev |
|--------|----------------------|------------|
| Prompt dependency | Long system prompts | Built-in behavior |
| Memory limits | Large models crash Colab | Lightweight & safe |
| Extra explanations | Mixed outputs | Code-only |
| Inconsistent style | Varies per prompt | Consistent coding style |

---

## 🧠 Core Philosophy

Training from scratch is impractical in constrained environments.  
Fine-tuning a small, code-specialized LLM is the correct and professional approach.

Cortex Dev follows **industry-standard fine-tuning practices** to remain:

✅ Efficient  
✅ Reproducible  
✅ Colab-safe  

---

## 🏗️ Architecture Overview

```
Base Code LLM (CodeGen-350M)
        ↓
Frozen Base Weights
        ↓
LoRA Adapter Layers (Trainable)
        ↓
Custom Code Dataset
        ↓
Cortex Dev – Code Generation Model
```

---

## 🤖 Base Model

**Salesforce CodeGen-350M**

**Why this model?**
- Pretrained specifically on source code  
- Strong syntax understanding  
- Small enough for Google Colab  
- Ideal for LoRA fine-tuning  

**Parameters:** ~350M  
**VRAM Usage:** ~6–8 GB (fp16 + LoRA)

---

## 🧩 Fine-Tuning Strategy

**Technique:** LoRA (Parameter-Efficient Fine-Tuning)

✅ Base model remains frozen  
✅ Only adapter layers trained  
✅ Minimal memory usage  
✅ Faster convergence  
✅ No RAM overflow  

| Method | Used |
|--------|------|
| Training from scratch | ❌ |
| Full fine-tuning | ❌ |
| LoRA / PEFT | ✅ |

---

## 🧠 Training Prompt (Model Behavior)

This prompt is embedded inside the training dataset:

```
You are a professional software engineer.

Your task is to generate clean, correct, and executable source code.

Rules:
- Output ONLY code.
- Do not explain the code.
- Follow standard coding best practices.
- Prefer simplicity, clarity, and correctness.
- Use meaningful variable and function names.
- Assume the code will be executed in a real environment.
```

📌 Used only during training  
📌 Shapes the model’s permanent behavior  

---

## 📦 Dataset Format

Each example follows a **prompt → completion** structure.

```json
{
  "prompt": "Write a Python function to check if a number is prime.",
  "completion": "def is_prime(n):\n    if n <= 1:\n        return False\n    for i in range(2, int(n ** 0.5) + 1):\n        if n % i == 0:\n            return False\n    return True"
}
```

✔ Clean  
✔ Minimal  
✔ Code-only  

---

## ⚙️ Training Configuration (Colab-Safe)

| Parameter | Value |
|----------|-------|
| Batch Size | 1 |
| Epochs | 2–3 |
| Precision | fp16 |
| Max Length | 512 |
| Optimizer | AdamW |
| Fine-Tuning | LoRA |

✅ No RAM overflow  
✅ No session crash  
✅ Runs entirely on Google Colab  

---

## 🧪 Inference Example

**Input**  
```
Write a Python function to reverse a string
```

**Output**  
```
def reverse_string(s):
    return s[::-1]
```

No explanations.  
No markdown.  
Just working code.  

---

## 🔍 Prompt vs Fine-Tuned Model

| Feature | Prompt Agent | Cortex Dev |
|---------|--------------|------------|
| Weight updates | ❌ | ✅ |
| Persistent behavior | ❌ | ✅ |
| Needs system prompt | ✅ | ❌ |
| Code-only output | ❌ | ✅ |
| Colab-safe | ✅ | ✅ |

---

## 🛠️ Tech Stack

- Python  
- HuggingFace Transformers  
- PEFT (LoRA)  
- PyTorch  
- Google Colab  

---

## 📌 Use Cases

✅ Personalized coding assistants  
✅ Hackathon accelerators  
✅ Educational code generators  
✅ Backend scaffolding tools  
✅ Domain-specific code models  

---

## 📄 License

MIT License — free to use, modify, and extend.

---

## ✨ Final Note

**Cortex Dev is not an assistant.**  
It is a trained code generation model designed to think and output like a developer.
