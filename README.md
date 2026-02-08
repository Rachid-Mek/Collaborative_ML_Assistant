# Collaborative Machine Learning Design Assistant (CoML-DS)

## Overview

**CoML-DS** is a minimal prototype of an **LLM-based collaborative learning application** designed to support
graduate-level students in **Machine Learning decision-making**.

Unlike traditional AI assistants that provide direct answers, CoML-DS is intentionally designed to:

- Encourage reflective thinking
- Ask clarifying and critical questions
- Challenge assumptions respectfully
- Support justification, comparison, and revision of ideas

The system positions the Large Language Model (LLM) as a **critical peer**, fostering **collaborative learning**
rather than solution delivery.

This prototype was developed as part of a **PhD Trial Task** for the **ALMA project**.

---

## Educational Context

- **Target learners**: Master’s students in Data Science / Artificial Intelligence
- **Learning domain**: Machine Learning model and pipeline design
- **Pedagogical goal**:
  - Help learners articulate and justify their ML design choices
  - Promote critical reflection rather than answer consumption
  - Encourage comparison of alternative approaches

The assistant does not evaluate decisions as correct or incorrect.
Instead, it supports **collaborative reasoning and sense-making**.

---

## Design Rationale

### Collaboration with an LLM

In this system, collaboration is defined as an **interactive process** in which the learner and the LLM
jointly explore decisions, assumptions, and alternatives.

The LLM is designed to act as a:

- **Critical peer**
- **Facilitator of reflection**
- **Co-explorer of design choices**

Rather than providing final answers, the LLM:

- Asks _why_ a choice was made
- Highlights potential trade-offs
- Suggests alternative perspectives
- Encourages revision and comparison

---

## System Architecture

The system follows a simple and transparent interaction-driven architecture:

![System Architecture](schema.png)

This architecture ensures that **collaborative behavior emerges from prompt design and interaction patterns**,
rather than from external knowledge augmentation.

---

## Adaptation Technique

The prototype relies on **prompt engineering** as its primary adaptation technique.

The collaborative behavior is achieved by:

- Explicitly defining the role of the LLM
- Constraining the LLM to avoid direct answers
- Structuring responses around reflection, justification, and alternatives

This choice allows the prototype to isolate **interaction design** as the main research variable,
without conflating it with content augmentation mechanisms such as Retrieval-Augmented Generation (RAG).

---

## Technologies Used

- **Programming language**: Python
- **Environment**: Jupyter Notebook
- **LLM**: OpenAI GPT-5 Mini
- **Libraries**:
  - `openai`
  - `python-dotenv`

---

## Repository Structure

├── CoML_DS_Collaborative_ML_Assistant.ipynb
├── README.md
├── schema.png
├── .env

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone <repository_url>
cd Collaborative_ML_Assistant
```

### 2 Create a virtual environment (optional but recommended)

```bash
python -m venv venv
source venv/bin/activate  # Linux / macOS
venv\Scripts\activate     # Windows
```

### 3. Install dependencies

```bash
pip install openai python-dotenv
```

### 4. Configure the OpenAI API key

Create a .env file in the project root directory:
OPENAI_API_KEY=your_openai_api_key_here

## Running the Application

### 1. Open CoML_DS_Collaborative_ML_Assistant.ipynb

### 2. Run all cells and enter a Machine Learning design decision when prompted.

Example inputs:

- I choose accuracy as the evaluation metric.
- I will use logistic regression because it is simple.
- I plan to use all features without feature selection.

Example Interaction:
Student input:

- I choose accuracy as the evaluation metric for my ML project.

Assistant response (excerpt):

- Why do you think accuracy is appropriate for this task?

- How might class imbalance affect this choice?

- Would recall or AUC provide complementary insights?

- Under what conditions would you reconsider this decision?

This interaction illustrates how the assistant supports collaborative reasoning
instead of providing direct answers.

#### Limitations

- Collaborative behavior depends strongly on prompt design
- No learner modeling or personalization
- No automatic evaluation of collaboration quality
- The LLM may still implicitly influence decisions

These limitations are acknowledged as part of the exploratory nature of this prototype.

#### Future Work

Potential extensions include:

- Adaptive prompting based on learner responses
- Integration of Retrieval-Augmented Generation (RAG) to introduce external viewpoints
- Collection of interaction metrics (e.g., number of revisions, justifications, dialogue turns)
- Comparative studies between collaborative and answer-based LLM behaviors

#### Conclusion

This prototype demonstrates that prompt engineering alone can be sufficient to design LLM-based systems that promote collaborative learning.

By aligning pedagogical goals with interaction design, CoML-DS illustrates how LLMs can move beyond answer generation toward meaningful collaboration with learners.
