# 🤖 Dialogue Summarization & Chatbot System

This project demonstrates a full pipeline that begins with fine-tuning a T5-base model for dialogue summarization, applies LoRA (Low-Rank Adaptation) for efficient parameter fine-tuning, and integrates both into a chatbot system that combines GPT-Neo for generating human-like responses with a summarizing memory module.

---

## 📌 Project Overview

### 1. Dataset Preparation
- The dataset contains multi-turn conversations along with corresponding human-written summaries.
- Input prompts were crafted to follow an instruction-style format for better learning:
  - *Start Prompt:* `Summarize the following conversation.`
  - *End Prompt:* `Summary:`

### 2. Fine-tuning T5-Base
- The T5-base model was fine-tuned using the prepared dataset.
- Hugging Face’s tokenizer was used to tokenize input/output sequences with padding and truncation.
- Training utilized `Trainer` and `TrainingArguments` from Hugging Face's Transformers library.
- Weights & Biases (W&B) was used for monitoring and logging metrics.

### 3. LoRA Fine-tuning (Parameter-Efficient Tuning)
- Low-Rank Adaptation (LoRA) was applied to the attention layers (query `q` and value `v` matrices).
- Key benefits of LoRA fine-tuning:
  - Requires fewer trainable parameters.
  - Enables faster training with less memory usage.
  - Allows higher learning rates without destabilizing training.
- PEFT (Parameter-Efficient Fine-Tuning) library from Hugging Face was used to integrate LoRA.

### 4. Chatbot Integration
- **Response Generation:** GPT-Neo model is used to generate human-like responses to user queries.
- **Memory Summarization:** The LoRA fine-tuned T5 model generates concise summaries of the conversation history.
- This setup ensures the chatbot remains context-aware while managing long conversations efficiently.

---

