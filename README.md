# 🤖 AI Joke Generator (LSTM)

An end-to-end Natural Language Processing (NLP) project built from scratch using **TensorFlow/Keras**. This model uses a Stacked LSTM (Long Short-Term Memory) architecture to learn the structure of English jokes and generate new (often hilariously nonsensical) ones word-by-word.

## 📊 Dataset & Architecture

- **Vocabulary Size:** 23,656 unique words
- **Sequence Length:** 40 words (input) $\rightarrow$ predicting the 41st word
- **Embedding Dimension:** 300
- **Architecture:** `Embedding -> LSTM(512) -> LSTM(512) -> Dense(512) -> Dense(Vocab_Size, Softmax)`
- **Training:** Achieved a peak validation accuracy of **~33%** (predicting the exact next word out of 23,656 possibilities).

## 🧠 Key Concepts Learned & Implemented

- **Text Preprocessing:** Tokenization, building a vocabulary index, and sequence padding.
- **Embeddings:** Mapping discrete word IDs to continuous dense vectors.
- **Stacked LSTMs:** Using `return_sequences=True` to pass sequence data between LSTM layers and learning long-term dependencies.
- **Overfitting Mitigation:** Implemented Dropout layers (0.2 and 0.4) and Early Stopping.
- **Text Generation:** Implemented **Top-K Sampling** (Temperature Sampling) using `np.random.choice` to prevent the model from getting stuck in infinite loops, allowing for more "creative" text generation.

## 🚀 How to Use

1. **Clone the repo:**
   ```bash
   git clone https://github.com/DhamzBonaparte/AI-Joke-Generator-LSTM.git
   cd AI-Joke-Generator-LSTM
   ```

2. **Install requirements:**
   ```bash
   pip install tensorflow numpy
   ```

3. **Generate Jokes:**
   Load the saved model (`joke_model.h5`) and tokenizer (`tokenizer.pickle`) using the provided `generate.py` script.

## 😂 Sample Outputs

Because the model is a basic LSTM (not a Transformer), it learns sentence structures well but lacks complex logical reasoning, resulting in surrealist comedy:

> *"I told my wife is on the same time in china and a gay girl and the most of the morning the world in"*

> *"Why did the chicken go to the bathroom in a plane in the morning a tree to be to the most of the same"*

## 🔮 Future Improvements

- **Switch to Transformers:** Upgrade to a pre-trained Hugging Face model (e.g., DistilGPT2) for coherent, context-aware joke generation.
- **Attention Mechanism:** Add an Attention layer to help the LSTM focus on the most important words in the setup.