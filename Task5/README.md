🤖 Empathetic Chatbot with DistilGPT-2
Overview
This project fine-tunes the DistilGPT-2 language model using the EmpatheticDialogues dataset to build a chatbot capable of generating emotionally aware and contextually appropriate responses. It takes user inputs, tracks conversation history, and responds with empathy based on past utterances and emotional labels.

Dataset
Name: EmpatheticDialogues

Source: Hugging Face Datasets

Splits: train, validation, test

Features used: prompt, utterance, conv_id, utterance_idx, speaker_idx, context (emotion)

Model
Base: distilgpt2

Tokenizer: AutoTokenizer with pad_token set to eos_token

Framework: Hugging Face Transformers

Modified to mask user input tokens from contributing to loss

Model and tokenizer saved as empathetic-kaggle_v2

Preprocessing
Grouped utterances by conversation ID

Sorted by utterance index to preserve dialogue order

Identified user and bot speakers

Built prompt, history, and utterance into a structured input

Output text includes emotion followed by bot’s reply

Tokenized both input and target with masking for causal loss

Training
Used Hugging Face Trainer API

4 epochs, batch size 16, gradient accumulation of 2

Cosine learning rate scheduler with warmup

EarlyStoppingCallback with patience of 2

Evaluation every 1000 steps

Final train loss around 0.41 and validation loss around 0.32

Model saved to empathetic-kaggle_v2 directory

Inference
Loads model and tokenizer from saved directory

Runs a chat loop in terminal

Maintains recent history of 6 lines max for context

Generates responses using temperature, top-k, top-p, and no-repeat n-gram settings

Allows resetting conversation using "new" or "reset" commands

How to Run
Install requirements: transformers, datasets, torch, tqdm

Run the notebook or script to train the model

Use the chat() function to interact with the bot

The bot will respond empathetically based on your input and chat history

Sample Interaction
You: I lost my job today
Bot: I'm really sorry to hear that. Are you okay?

You: It's been really hard
Bot: I understand. That must be incredibly stressful.

Features
Emotionally conditioned response generation

Supports multi-turn conversation with memory

Lightweight model (DistilGPT-2) for faster fine-tuning

Emotion integrated in target response for richer supervision

Future Work
Support for longer context beyond 6 lines

Add frontend interface (web or mobile)

Experiment with other base models like GPT2-large or LLaMA

Evaluate with BLEU/ROUGE or human feedback
