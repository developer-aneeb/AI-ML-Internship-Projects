# 🧠 SerenityAI: Empathetic Mental Health Support Chatbot

[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models-orange?style=for-the-badge)](https://huggingface.co/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![Fine-Tuning](https://img.shields.io/badge/Task-Fine--Tuning-blue?style=for-the-badge)](https://huggingface.co/docs/transformers/training)

> **Empowering Emotional Wellness through Generative AI.** SerenityAI is a specialized conversational agent fine-tuned on the **EmpatheticDialogues** dataset to provide supportive, resonant interactions for individuals navigating stress and anxiety.

---

## 📖 Project Overview
In a world where mental health resources are often scarce or stigmatized, **SerenityAI** serves as an accessible, non-judgmental first point of contact. Unlike generic LLMs, this chatbot is specifically engineered to acknowledge emotional nuance—transitioning from simple "fact-retrieval" to "empathetic listening."

Developed as an end-to-end NLP engineering project, it covers the complete lifecycle: from **automated dataset standardization** and **Exploratory Data Analysis (EDA)** to **Parameter-Efficient Fine-Tuning** and **Safety-First deployment**.

---

## 🎯 Task Objective
The primary goal was to transform a base **GPT-Neo 125M** model into a domain-specific emotional support tool. Technical objectives included:
1.  **Emotion-Conditioned Generation**: Fine-tuning the model to recognize 32 distinct emotion labels and generate appropriate supportive responses.
2.  **Robust Preprocessing Pipeline**: Engineering a reusable data cleaning module to handle noise in human-to-human dialogue datasets.
3.  **Safety Guardrails**: Integrating a regex-based **Safety Gate** to detect high-risk prompts (self-harm, emergencies) and provide immediate professional resources.

---

## 📊 Dataset: EmpatheticDialogues (Facebook AI)
The project utilizes the **EmpatheticDialogues** dataset (64k+ rows), which is specifically curated for training emotionally intelligent machines.

*   **Source**: `atharvjairath/empathetic-dialogues-facebook-ai` (Kaggle).
*   **Key Features**:
    *   `Situation`: The context provided by the user.
    *   `Emotion`: Grounded labels (e.g., *Devastated, Sentimental, Apprehensive*).
    *   `Dialogue`: Multi-turn exchanges between a "Speaker" and a "Listener".
*   **Data Engineering**:
    *   Implemented a `normalize_col` utility for column name standardization.
    *   Automated column detection logic (`find_column`) to handle various CSV schemas.
    *   Conducted length distribution analysis to optimize `MAX_LENGTH` constraints.

---

## 🛠️ Tech Stack
*   **Core Logic**: `Python 3.12`, `PyTorch`.
*   **LLM Framework**: `Transformers`.
*   **Model**: **GPT-Neo 125M** (Selected for its balance of causal reasoning and small-footprint training stability).
*   **Hardware**: `NVIDIA Tesla T4 GPU` (Mixed Precision training enabled).
*   **Visualization**: `Seaborn` & `Matplotlib` for loss curve and emotion distribution plotting.

---

## 🧠 Machine Learning Workflow
1.  **Exploratory Data Analysis (EDA)**: Analyzed the frequency of 32 emotions and dialogue word counts to prevent data truncation during tokenization.
2.  **Standardization**: Transformed raw dialogue into a unified format: `[Emotion] <|context|> [Situation] <|response|> [Dialogue]`.
3.  **Training Strategy**:
    *   **Architecture**: Decoder-only Causal Language Modeling.
    *   **Optimization**: `AdamW` with a Linear Learning Rate Scheduler.
    *   **Hyperparameters**: 3 Epochs, 5e-5 Learning Rate, 0.1 Warmup Ratio, and **Gradient Accumulation (4)** to simulate larger batch sizes on constrained VRAM.
4.  **Evaluation**: Monitored Perplexity and Validation Loss; utilized `EarlyStoppingCallback` to maintain generalizability.

---

## 📈 Key Results & Findings
*   **Convergence**: The model demonstrated a smooth decline in training loss, indicating successful alignment with the "supportive listener" persona.
*   **Versatility**: Qualitative testing showed the model could distinguish between positive emotions (Hopeful, Proud) and negative stressors (Jealous, Disappointed), adjusting its tone accordingly.
*   **Inference Efficiency**: Sub-second response generation, making it viable for real-time CLI or Web deployment.

---

## 🛡️ Responsible AI & Safety Gating
**SerenityAI is engineered with a strict ethical framework:**

1.  **Non-Medical Disclaimer**: The system explicitly states it is an AI wellness tool, not a substitute for clinical therapy.
2.  **Emergency Interception**: A hard-coded `Safety Gate` monitors for high-risk keywords. Upon detection, it bypasses LLM generation to provide verified emergency hotlines (e.g., 988 in the US).
3.  **Hallucination Mitigation**: Use of controlled temperature and top-p sampling to prevent the model from providing medical advice.

---

## 📂 Project Structure
```text
SerenityAI/
│── mental-health-support-chatbot.ipynb   # Complete pipeline: EDA -> Training -> Inference
│── empathetic_chatbot_gptneo125m/        # Model checkpoints and config
│── README.md                             # Professional documentation
                           # EDA charts and loss curves
```

---

## 🏛️ Final Conclusion
This project demonstrates that even smaller transformer models (125M parameters) can achieve high levels of emotional resonance when fine-tuned on high-quality, domain-specific data. It reflects a sophisticated understanding of both **generative AI engineering** and **responsible development practices**.

---
**Developed by Aneeb Ur Rehman**  
**AI/ML Intern at DevelopersHub Corporation**
