🤖 Dialogue Summarization & Chatbot System

This project showcases a complete pipeline starting from fine-tuning a T5-base model for dialogue summarization, enhancing it using LoRA (Low-Rank Adaptation) for efficient parameter tuning, and integrating it into a chatbot that generates responses with GPT-Neo and summarizes the chat history with the fine-tuned T5 model.
📌 Project Overview

    Dataset Preparation
    We utilized a dialogue-summary dataset where each entry contains a multi-turn conversation and its corresponding summary.

    Fine-tuning T5-Base

        The T5-base model was fine-tuned using instruction-style prompts for better understanding and alignment with the summarization task.

        Tokenization was applied using the T5 tokenizer with prompt engineering for both input and output.

        Training was monitored using Weights & Biases (W&B).

    Parameter-Efficient Fine-tuning with LoRA

        LoRA was applied to the attention mechanism (query q and value v matrices).

        Only a small number of additional parameters were trained while freezing the rest of the model.

        This enabled high learning rates, low memory consumption, and faster convergence.

    Chatbot Integration

        GPT-Neo was used for generating human-like responses in the chatbot.

        The dialogue history is summarized using the fine-tuned LoRA-T5 model to maintain concise context and memory.

        This two-model architecture ensures both response generation and memory efficiency.

💡 Highlights

    ✅ Instruction-tuned summarization using prompt formatting

    ✅ LoRA-based model for resource-efficient fine-tuning

    ✅ Integration of summarization and generation in a chatbot

    ✅ Uses Hugging Face Transformers, Datasets, PEFT, and Weights & Biases
