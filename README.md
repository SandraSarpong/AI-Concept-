# 🤖 AI & ML Fundamentals

> A personal knowledge base for my transition into AI Systems Engineering. No fluff. No unnecessary jargon. Just honest explanations I can actually use.

---

## 📌 Table of Contents

- [What is AI and ML?](#what-is-ai-and-ml)
- [What Are AI Models?](#what-are-ai-models)
- [Features and Labels](#features-and-labels)
- [AI Training vs Inference](#ai-training-vs-inference)
- [ML vs Deep Learning vs Generative AI](#ml-vs-deep-learning-vs-generative-ai)
- [Neural Networks](#neural-networks)
- [AI Agents](#ai-agents)
- [AI Development Options](#ai-development-options)
- [AI Development Workflows](#ai-development-workflows)
- [Capabilities and Limitations](#capabilities-and-limitations)
- [Using AI Responsibly](#using-ai-responsibly)

---

## What is AI and ML?

**Artificial Intelligence (AI)** is the big umbrella. Anything where a computer does something that would normally require human intelligence, like reading text, recognising faces, and making decisions, falls under AI.

**Machine Learning (ML)** lives inside that umbrella. It's the specific approach where, instead of you writing rules like `if X then do Y`, you feed the computer a pile of examples and let it figure out the rules itself.

Think of it this way:

```
Traditional programming:  Data + Rules  → Answers
Machine Learning:         Data + Answers → Rules
```

The computer learns the rules by studying the examples. That's the whole trick.

---

## What Are AI Models?

An AI model is the thing that gets trained and then used to make predictions or generate output.

Under the hood, it's a mathematical function, thus a very large and complex one with thousands or even billions of adjustable settings called **parameters**. Training a model means tuning those parameters until the function reliably produces useful output.

You can think of a model like a finely tuned instrument: it took a lot of work to get it sounding right, but once it does, you can play it whenever you need to.

---

## Features and Labels

These two terms come up constantly in ML, so let's be precise.

**Features** are the inputs, thus the measurable characteristics of whatever you're studying.

| Example Task | Features |
|---|---|
| Predicting house prices | Square footage, location, number of rooms |
| Detecting spam email | Word frequency, sender history, link count |
| Diagnosing a disease | Age, test results, symptoms |

**Labels** are the correct answers you're training the model to predict.

- House price: `£320,000`
- Email: `spam` or `not spam`
- Diagnosis: `positive` or `negative`

During training, the model sees the features and tries to predict the label. If it's wrong, it adjusts. If it's right, it reinforces that approach. Over enough examples, it gets good at predicting labels it's never seen before.

---

## AI Training vs Inference

These are the two phases of an AI model's life.

### 🏋️ Training — The Learning Phase

This is where the model is built. The process looks like this:

1. Feed the model a massive dataset
2. The model makes predictions
3. Compare those predictions to the correct answers
4. Measure the error (using something called a **loss function**)
5. Push the model's parameters in the direction that reduces the error
6. Repeat over and over again, a thousand or millions of times

Two core approaches to training:

- **Supervised Learning**: The training data has labels. The model learns to map inputs to known outputs. For instance, teaching with an answer key.
- **Unsupervised Learning**: No labels. The model looks for patterns and structure in the data on its own. For instance, asking someone to sort a pile of objects with no instructions.

### 🚀 Inference — The Production Phase

Once training is done, the model is deployed. Inference is when the model takes a brand-new input it's never seen before and produces an output using everything it's learned.

Crucially: **the model doesn't learn during inference**. Its parameters are frozen. It's just applying what it already knows fast, at scale.

```
Training = learning on historical data (slow, expensive, done once or periodically)
Inference = applying that knowledge to live data (fast, cheap, done constantly)
```

---

## ML vs Deep Learning vs Generative AI

These three get used interchangeably online. They shouldn't be.

```
Artificial Intelligence
└── Machine Learning
    └── Deep Learning
        └── Generative AI
```

| Term | What it actually means |
|---|---|
| **Machine Learning** | The broad approach of learning patterns from data |
| **Deep Learning** | A type of ML that uses neural networks with many layers. Particularly good at images, audio, and text |
| **Generative AI** | A type of deep learning where the model creates new content in the form of text, images, code, or audio rather than just classifying or predicting |

Generative AI (like ChatGPT or Stable Diffusion) is the newest and most visible layer. But it's built on decades of ML and deep learning research beneath it.

---

## Neural Networks

Neural networks are the architecture powering most modern AI, especially when it comes to deep learning.

The name is loosely inspired by the brain, but don't take that too literally. In practice, a neural network is a series of mathematical layers, each transforming its input and passing it to the next.

```
Input Layer → [Hidden Layer 1] → [Hidden Layer 2] → ... → Output Layer
```

- **Input layer**: Receives raw data (pixels, words, numbers)
- **Hidden layers**: Each layer detects increasingly abstract patterns
- **Output layer**: Produces the final prediction or generation

What makes this powerful is that the network learns *what features matter* automatically. For image recognition, early layers detect edges. Middle layers detect shapes. Later layers detect objects. Nobody programmed that, but rather it emerged from training.

The more hidden layers a network has, the "deeper" it is, hence **deep learning**.

---

## AI Agents

An AI agent is more than just a model. It's a system that can **reason** about a problem, **use tools** to interact with the outside world, and **coordinate** those pieces to actually get something done.

The three components every AI agent needs:

```
┌──────────────────────────────────────────┐
│              AI AGENT                    │
│                                          │
│  🧠 Model       → Reasoning & decisions  │
│  🔧 Tools       → External actions       │
│  🎯 Orchestration → Coordination logic   │
└──────────────────────────────────────────┘
```

**Model**:- The AI brain. It reads context, reasons about what to do next, and decides which tool to use.

**Tools**:- Anything the agent can call: a web search, a database query, a code executor, an API. Tools let the agent affect the real world, not just generate text.

**Orchestration**:- The logic that coordinates everything. It decides the sequence of steps, manages the state of the task, and handles what happens when something goes wrong.

A chatbot answers questions. An AI agent takes actions.

---

## AI Development Options

When building something AI-powered, you have three main paths:

| Option | What it means | When to use it |
|---|---|---|
| **Custom Training** | You build and train a model from scratch on your own data | You have unique data, specific requirements, and serious resources |
| **Pretrained** | You start with a model someone else trained, then fine-tune it on your data | You want the benefits of a large model without training from zero |
| **Fully Managed / Pretrained as-is** | You use a model via API with no training at all | You need to move fast, and the general model is good enough |

Most real-world projects today start with a pretrained model and fine-tune it. Training from scratch is expensive and rarely necessary unless your problem is genuinely novel.

---

## AI Development Workflows

Building an AI system isn't just about the model. The workflow has three major phases:

### 1. 📦 Data Preparation
Garbage in, garbage out. This phase is often the most time-consuming and the most important.

- Collecting raw data
- Cleaning it (removing duplicates, fixing errors, handling missing values)
- Labelling it (for supervised learning)
- Splitting it into training, validation, and test sets

### 2. 🏗️ Model Development
Choosing and designing the model architecture.

- What type of model fits the problem?
- How many layers, what size, what structure?
- What loss function and optimiser?

### 3. 🎓 Model Training
Running the training loop by feeding data through, computing loss, updating parameters, and evaluating performance.

- Monitor training metrics
- Watch for overfitting (memorising training data) vs underfitting (not learning enough)
- Iterate on architecture and hyperparameters
- Evaluate on the held-out test set

Then: deployment, monitoring, and eventually retraining. The work doesn't stop at launch.

---

## Capabilities and Limitations

It's easy to be dazzled by what AI can do. It's more useful to be clear-eyed about both sides.

### ✅ What AI is genuinely good at

- Processing and finding patterns in very large datasets
- Performing repetitive cognitive tasks at scale and speed
- Generating plausible text, images, and code
- Classification, prediction, and recommendation at production scale
- Surfacing information and summarising it quickly

### ⚠️ What AI is not good at

- **Reasoning from first principles** — AI pattern-matches; it doesn't truly reason
- **Understanding context the way humans do** — It can miss things that would be obvious to anyone in the room
- **Knowing what it doesn't know** — Models can confidently produce wrong answers (hallucination)
- **Handling data very different from its training set** — Distribution shift breaks models quietly
- **Anything requiring genuine creativity, empathy, or ethical judgment** — These are human strengths

Humans bring critical reasoning, emotional intelligence, and contextual understanding that AI systems fundamentally lack. AI is a tool that amplifies what humans can do and not a replacement for human judgment.

---

## Using AI Responsibly

**Responsible AI** is the commitment to building and using AI in ways that benefit people and society, and actively avoid harm. It's not a box-ticking exercise, but rather it's an ongoing obligation.

Key principles to keep in mind:

**🎯 AI Bias**
AI models learn from data. If that data reflects historical biases like race, gender, or socioeconomic status, the model will learn and often amplify those biases. A hiring model trained on historical decisions will replicate historical discrimination unless you specifically work to prevent it. Always ask: *Who collected this data, and whose experiences are underrepresented in it?*

**🔍 Transparency**
People affected by AI decisions deserve to understand how those decisions were made. Build systems that are explainable where it matters.

**🧑‍⚖️ Human oversight**
High-stakes decisions like medical, legal, and financial should keep humans in the loop. AI should inform and assist, not replace, human judgment in consequential situations.

**📏 Know the limitations**
The most dangerous AI user is the one who doesn't know what the tool can't do. Understanding limitations isn't pessimism, it's professional competence.

---

## 📚 Further Reading
You can check out my blog post on Medium 
- [How machines learn](https://medium.com/@maameyaasarp/how-machines-learn-a-plain-english-guide-to-one-of-techs-most-misunderstood-concepts-ac456d6b7dcd)
- [The art of prompt engineering](https://medium.com/@maameyaasarp/the-art-of-prompting-how-to-talk-to-ai-like-you-mean-it-3b97ef464fcf)


---
