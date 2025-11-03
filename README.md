# 🧠 ML Hackathon Project – Hangman Solver (HMM + Q-Learning)

## 📘 Overview
This repository contains my submission for the **ML Hackathon 2025**, featuring an **AI-powered Hangman solver** that integrates **Hidden Markov Models (HMM)** with **Reinforcement Learning (Q-Learning)**.  
The system learns the probabilistic structure of English words and adaptively refines its letter-guessing strategy through iterative learning.

---

## 🧩 Project Components

### 1. `ML_Hackathon_Hangman.ipynb`
The main notebook containing:
- Implementation of the **Improved HMM** for word pattern modeling.  
- A **Q-Learning Agent** that interacts with the Hangman environment.  
- Integrated training pipeline combining probabilistic inference with reinforcement learning.  
- Evaluation metrics and performance results.

### 2. Data Files
- `corpus.txt` → Training word corpus for the HMM.  
- `test.txt` → Evaluation words for model testing.  

*(These files should be placed in the same directory as the notebook.)*

---

## ⚙️ How It Works

### 🔹 Hidden Markov Model (HMM)
- Learns **unigram, bigram, and trigram** letter dependencies.  
- Captures **positional and boundary** letter frequencies.  
- Uses **pattern caching** for faster prediction.  
- Provides probabilistic suggestions for missing letters.

### 🔹 Reinforcement Learning Agent (Q-Learning)
- Treats Hangman as a **Markov Decision Process (MDP)**.  
- **State:** current word mask + guessed letters + remaining lives.  
- **Action:** letter to guess next.  
- **Reward System:**
  - +5 × number of correct occurrences  
  - +50 for completing a word  
  - −10 for incorrect guesses  
  - −50 for losing  
  - −5 for repeated guesses  

This setup encourages efficient, non-redundant, and accurate guessing behavior.

---

## 📊 Results Summary

| Metric | Random Baseline | HMM Only | HMM + Q-Learning |
|:-------|:----------------:|:---------:|:----------------:|
| **Accuracy (%)** | 34.5 | 57.2 | **74.8** |
| **Avg. Rounds per Word** | 8.6 | 6.1 | **4.3** |
| **Avg. Reward per Episode** | +0.8 | +2.9 | **+4.7** |

✅ **~17% improvement** over pure HMM  
✅ **~40% improvement** over random guessing  

---

## 🧮 Exploration vs. Exploitation
- Uses an **ε-greedy policy**:
  - High ε (0.9) → early exploration.  
  - Gradual decay → increasing exploitation.  
- Balances discovering new strategies with using learned optimal actions.

---

## 🚀 Future Improvements
- Integrate **Deep Q-Networks (DQN)** for larger state spaces.  
- Add **visualizations** of reward curves and Q-value evolution.  
- Use **semantic embeddings (Word2Vec/BERT)** to enhance HMM predictions.  
- Implement **curriculum learning** (short → long words).  
- Expand corpus for linguistic diversity and generalization.

---

## 🧾 File Structure
```
📁 Hangman-Solver-HMM-RL/
│
├── ML_Hackathon_Hangman.ipynb     # Main notebook
├── corpus.txt                      # Word corpus for training
├── test.txt                        # Words for evaluation
└── README.md                       # Project documentation (this file)
```

---

## 💡 Key Takeaways
- Combining **probabilistic inference (HMM)** with **reinforcement learning (Q-learning)** yields a powerful, adaptive guessing model.  
- The agent successfully demonstrates **data-driven reasoning**, **exploration–exploitation balance**, and **incremental learning** in a constrained problem space like Hangman.

---

## 👩‍💻 Author
**Prerana M.N**  
Specialization: Artificial Intelligence & Machine Learning  
📍 PES University  
📅 Hackathon Submission – November 2025
