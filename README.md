# 🚀 Google DeepMind: AI Research Foundations

<div align="center">
  <img src="https://storage.googleapis.com/dm-educational/assets/ai_foundations/GDM-Labs-banner-image-C1-white-bg.png" alt="Google DeepMind AI Foundations Banner" width="100%">
  <br><br>
  <p>
    <b>An epic journey into the mathematical and practical foundations of modern Generative AI.</b>
  </p>
  <p>
    🇧🇷 <a href="./README_PTBR.md">Versão em Português (Portuguese Version)</a>
  </p>
</div>

---

## 🗺️ The Journey: AI Research Foundations
This repository documents my hands-on research and exploration through the **Google DeepMind: AI Research Foundations** curriculum. This university-grade program dives deep into the mechanisms under the hood of Large Language Models (LLMs), starting from basic probability and leading to building, training, and optimizing complex neural architectures.

* **Curriculum Link:** [Google DeepMind: AI Research Foundations](https://www.skills.google/paths/3135)
* **GitHub Repository:** [OYanEnrique/google-deepmind-ai](https://github.com/OYanEnrique/google-deepmind-ai)
* **Author:** [@OYanEnrique](https://github.com/OYanEnrique)

---

## 📖 Chapter 1: The Magic of the Next Word
*How do machines generate text? We begin by simulating the core intuition of language models: predicting the next word based on context.*

```
[Prompt] "Jide was hungry so she went looking for..." ---> [Probability Distribution] ---> [Sampling] ---> "food"
```

### Labs & Breakthroughs
* [**`01-Google-Deepmind.ipynb`**](./notebooks/01-Google-Deepmind.ipynb) — **Creating Probability Distributions**
  * **The Mission:** Step into the shoes of an AI. Given the prompt *"Jide was hungry so she went looking for..."*, we manually assigned probability weights to candidate words and sampled them using `random.choices`.
  * **The Breakthrough:** I learned that text generation is fundamentally stochastic. By changing the context (e.g., from *hungry* to *thirsty*), we see how a model's "mental model" shifts the probability weights of candidate words.
* [**`02-Google-Deepmind.ipynb`**](./notebooks/02-Google-Deepmind.ipynb) — **N-Gram Models**
  * **The Mission:** Instead of guessing probabilities, we automated the process by counting words in a corpus. We built Bigram and Trigram models.
  * **The Breakthrough:** I discovered the mechanics of statistical NLP. N-Grams calculate probabilities by looking back at the last $N-1$ words. While fast, they fail to grasp long-term context because of their limited window.
* [**`03-Google-Deepmind.ipynb`**](./notebooks/03-Google-Deepmind.ipynb) — **N-Grams vs. Transformers**
  * **The Mission:** Pit a classical N-Gram model against a state-of-the-art Transformer model on the task of text completion.
  * **The Breakthrough:** A stark realization of the "attention mechanism" power. Transformers don't just look at the last few words; they capture semantic dependencies across the entire sentence, avoiding the nonsensical loops common in N-Grams.
* [**`04-Google-Deepmind.ipynb`**](./notebooks/04-Google-Deepmind.ipynb) — **Preparing the Dataset for an SLM**
  * **The Mission:** Construct a complete data pipeline to clean, format, and package raw text into training datasets for a Small Language Model (SLM).
  * **The Breakthrough:** The realization that "garbage in, garbage out" is real. I mastered text cleanup, formatting token lists, and building efficient input-target pairs for autoregressive training.

---

## 📖 Chapter 2: The Language of Machines
*To process language, computers cannot use raw characters or words. We must convert human text into mathematical vectors that capture meaning.*

```
"Text" ---> [Preprocessing] ---> [BPE Tokenization] ---> [Embedding Layer] ---> Vector Space (0.15, -0.82, ...)
```

### Labs & Breakthroughs
* [**`05-Google-Deepmind.ipynb`**](./notebooks/05-Google-Deepmind.ipynb) — **Text Preprocessing**
  * **The Mission:** Clean raw text data by removing noise, normalizing capitalizations, handling special characters, and converting text to a uniform format.
  * **The Breakthrough:** I learned how to sanitize text to reduce vocabulary size without losing semantic meaning, laying the foundation for efficient tokenization.
* [**`06-Google-Deepmind.ipynb`**](./notebooks/06-Google-Deepmind.ipynb) — **Subword Tokenization**
  * **The Mission:** Explore the middle ground between character-level and word-level representations: subwords.
  * **The Breakthrough:** I understood how subword tokenization elegantly handles "Out-of-Vocabulary" (OOV) words. By breaking unknown words into known subword roots, we prevent model crashes while keeping vocabulary sizes manageable.
* [**`07-Google-Deepmind.ipynb`**](./notebooks/07-Google-Deepmind.ipynb) — **Character vs. Word Tokenization**
  * **The Mission:** Compare character-level tokenization (huge sequences, tiny vocabulary) against word-level tokenization (short sequences, massive vocabulary).
  * **The Breakthrough:** Visualized the tradeoffs: Character models require massive compute to learn simple words; word models struggle with new words. This comparison solidified why subword-level methods are the industry standard.
* [**`08-Google-Deepmind.ipynb`**](./notebooks/08-Google-Deepmind.ipynb) — **Implementing a BPE Tokenizer**
  * **The Mission:** Build a Byte-Pair Encoding (BPE) tokenizer from scratch.
  * **The Breakthrough:** I implemented the core algorithm that powers models like GPT. By starting with individual characters and iteratively merging the most frequent token pairs, I saw how a custom vocabulary adaptively grows based on text statistics.
* [**`09-Google-Deepmind.ipynb`**](./notebooks/09-Google-Deepmind.ipynb) — **Experimenting with Embeddings**
  * **The Mission:** Translate discrete tokens into continuous vector spaces.
  * **The Breakthrough:** Experienced the geometry of language. I learned how semantic relationships (like synonyms or analogies) translate to geometric distance (cosine similarity) and how models cluster related concepts in high-dimensional space.
* [**`10-Google-Deepmind.ipynb`**](./notebooks/10-Google-Deepmind.ipynb) — **Training an SLM with a BPE Tokenizer**
  * **The Mission:** Integrate the custom-built BPE tokenizer with a Small Language Model (SLM) and train it on text.
  * **The Breakthrough:** I closed the loop between tokenization and model training. I observed how the quality of token representations directly impacts the stability and coherence of the generated output.

---

## 📖 Chapter 3: Crafting the Artificial Brain
*We step away from simple statistics and enter the world of Deep Learning. How do we design networks that learn from error and adjust their parameters?*

```
Inputs ---> [Weights & Biases] ---> [Activation Function] ---> Loss Calculation ---> [Backpropagation] ---> Update
```

### Labs & Breakthroughs
* [**`11-Google-Deepmind.ipynb`**](./notebooks/11-Google-Deepmind.ipynb) — **Signal vs. Noise**
  * **The Mission:** Determine how a mathematical function can draw a line (decision boundary) to classify data points into separate groups.
  * **The Breakthrough:** I learned the concept of linear classification and why identifying clean mathematical patterns is essential to filter out chaotic background noise.
* [**`12-Google-Deepmind.ipynb`**](./notebooks/12-Google-Deepmind.ipynb) — **Single-Layer Neural Networks**
  * **The Mission:** Implement a basic single-neuron classifier (Perceptron) to make binary decisions.
  * **The Breakthrough:** I mastered how weights scale features and how bias shifts the decision boundary, mapping inputs directly to predictions.
* [**`13-Google-Deepmind.ipynb`**](./notebooks/13-Google-Deepmind.ipynb) — **Separating Complex Data**
  * **The Mission:** Challenge a linear single-layer network with non-linearly separable datasets (like the XOR problem).
  * **The Breakthrough:** I experienced the "linear limitation." I understood why single-layer networks fail at complex patterns, demonstrating the absolute necessity of hidden layers and non-linear activation functions.
* [**`14-Google-Deepmind.ipynb`**](./notebooks/14-Google-Deepmind.ipynb) — **Designing an MLP**
  * **The Mission:** Architect a Multi-Layer Perceptron (MLP) from scratch.
  * **The Breakthrough:** By stacking input layers, hidden layers with activations (like ReLU), and output layers, I learned how neural networks warp vector space to draw complex, curved decision boundaries.
* [**`15-Google-Deepmind.ipynb`**](./notebooks/15-Google-Deepmind.ipynb) — **Hyperparameter Tuning**
  * **The Mission:** Tune learning rates, batch sizes, epochs, and layer sizes to optimize training speed and accuracy.
  * **The Breakthrough:** I realized that deep learning is as much an art as it is a science. I observed how a high learning rate causes divergence, while a low rate slows training to a crawl.
* [**`16-Google-Deepmind.ipynb`**](./notebooks/16-Google-Deepmind.ipynb) — **Mitigating Overfitting**
  * **The Mission:** Train a model that doesn't just memorize the training dataset but generalizes to unseen test data.
  * **The Breakthrough:** I explored the bias-variance trade-off and applied regularization techniques (like weight decay, dropout, and early stopping) to prevent the model from memorizing noise.
* [**`17-Google-Deepmind.ipynb`**](./notebooks/17-Google-Deepmind.ipynb) — **Gradients and Backpropagation**
  * **The Mission:** Deconstruct the engine of AI: gradients and the chain rule of calculus.
  * **The Breakthrough:** I manually computed gradients to understand how the loss error flows backward through the network, updating weights via Gradient Descent.
* [**`18-Google-Deepmind.ipynb`**](./notebooks/18-Google-Deepmind.ipynb) — **Training with Keras**
  * **The Mission:** Transition from manual, low-level math coding to high-level framework building using Keras.
  * **The Breakthrough:** I built, compiled, and trained deep learning models efficiently, leveraging industry-standard tools to automate model definition, loss optimization, and evaluation pipelines.

---

## 📖 Chapter 4: Discover The Transformer Architecture
*How do transformers process information? We dive into the core components of the transformer architecture: attention, multi-head configurations, masking, positional embeddings, and parameter scaling.*

```
Input Tokens ---> [Embeddings + Positional Encoding] ---> [Masked Multi-Head Attention] ---> [LayerNorm & MLP] ---> Next Token Predictions
```

### Labs & Breakthroughs
* [**`19-Google-Deepmind.ipynb`**](./notebooks/19-Google-Deepmind.ipynb) — **Visualizing Attention Weights**
  * **The Mission:** Step into the inner workings of a transformer. We visualized how the attention mechanism of the Gemma-1B model distributes weights across different prompt tokens to predict the next word.
  * **The Breakthrough:** I observed how attention changes across different model layers and how it can successfully capture long-range dependencies, spanning across multiple sentences to retrieve context from the beginning of the text.
* [**`20-Google-Deepmind.ipynb`**](./notebooks/20-Google-Deepmind.ipynb) — **Implementing the Attention Equation**
  * **The Mission:** Get under the hood of the attention mechanism by implementing the attention query, key, and value ($Q, K, V$) calculations from scratch using JAX.
  * **The Breakthrough:** I implemented the fundamental scaled dot-product attention equation, using the learned projection matrices of Gemma-1B to calculate custom attention weights and construct contextual embeddings.
* [**`21-Google-Deepmind.ipynb`**](./notebooks/21-Google-Deepmind.ipynb) — **Implementing Masked Multi-Head Attention**
  * **The Mission:** Build a complete masked multi-head attention mechanism from scratch, introducing causal masking and parallel head processing.
  * **The Breakthrough:** I understood how multiple attention heads focus on different parts of a sentence simultaneously, and why causal masking is essential during autoregressive training to prevent the model from "cheating" by looking at future tokens.
* [**`22-Google-Deepmind.ipynb`**](./notebooks/22-Google-Deepmind.ipynb) — **Positional Embeddings**
  * **The Mission:** Explore the order-invariance property of raw self-attention by demonstrating how changing word order without positional information leads to the exact same outputs.
  * **The Breakthrough:** A deep realization of why positional encodings are mandatory. Without them, a transformer treats a sentence as a bag of words, failing to distinguish between *"the zebra chased the lion"* and *"the lion chased the zebra"*.
* [**`23-Google-Deepmind.ipynb`**](./notebooks/23-Google-Deepmind.ipynb) — **Trainable Parameters in the Transformer Model**
  * **The Mission:** Walk through the complete Keras and JAX implementation of a modular transformer model, writing equations to count the trainable parameters of each building block.
  * **The Breakthrough:** I mastered the parameter scaling dynamics of transformers. By dissecting LayerNorm, Embeddings, Attention, and MLP components, I learned how model hyperparameters and vocabulary size mathematically scale the total parameter count.

---

## 🔮 The Quest Continues...

The journey is far from over. The notebook folder currently contains labs up to Course 4. As I progress through the remaining modules of the path, new notebooks and breakthroughs will be committed here:

* [ ] **Google DeepMind: 05 Fine-Tune Your Model**
* [ ] **Google DeepMind: 07 Accelerate Your Model**


<div align="center">

<br>

**Project Author:** [Yan Enrique (OYanEnrique)](https://github.com/OYanEnrique)  
*(Data Scientist | Machine Learning Engineer)*

</div>

---

## 📝 Licença

This project is licensed under the **MIT**. See the [LICENSE](LICENSE) for more details.