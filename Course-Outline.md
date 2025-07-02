# 🗺️ CS336: Language Modeling from Scratch - Course Outline & Dashboard

This file serves as the master plan and progress tracker for my study of Stanford's CS336 course (Spring 2025). All notes and assignments are linked from here.

**Original Course Link:** [https://stanford-cs336.github.io/spring2025/](https://stanford-cs336.github.io/spring2025/)

---

## 👥 Course Staff & Logistics

### Instructors
- **Tatsunori Hashimoto**
- **Percy Liang**

### Course Assistants (CAs)
- Marcel Rød
- Neil Band
- Rohith Kuditipudi

### Logistics
- **Lectures:** Tuesday/Thursday 3:00-4:20pm in NVIDIA Auditorium
- **Contact:** Use public Slack channels for course-related questions. For personal matters, email `cs336-spr2425-staff@lists.stanford.edu`.

---

## 🎯 Course Description

Language models serve as the cornerstone of modern natural language processing (NLP) applications and open up a new paradigm of having a single general-purpose system address a range of downstream tasks. As the field of artificial intelligence (AI), machine learning (ML), and NLP continues to grow, possessing a deep understanding of language models becomes essential for scientists and engineers alike. This course is designed to provide students with a comprehensive understanding of language models by walking them through the entire process of developing their own. Drawing inspiration from operating systems courses that create an entire operating system from scratch, we will lead students through every aspect of language model creation, including data collection and cleaning for pre-training, transformer model construction, model training, and evaluation before deployment.

---

##  Prerequisites

* **Proficiency in Python:** This is a very implementation-heavy class. The amount of code you will write will be at least an order of magnitude greater than for other classes.
* **Experience with deep learning and systems optimization:** Strong familiarity with **PyTorch** and basic systems concepts like the memory hierarchy is expected.
* **College Calculus, Linear Algebra:** Comfortable understanding matrix/vector notation and operations.
* **Basic Probability and Statistics:** Knowledge of probabilities, Gaussian distributions, mean, standard deviation, etc.
* **Machine Learning:** Comfortable with the basics of machine learning and deep learning (e.g., from CS221, CS229, CS224N).

> **Note:** This is a 5-unit class requiring a significant time commitment.

---

## 💻 Coursework Dashboard

| ID | Assignment & Official Links | Key Topics | Status | My Project |
| :--: | :--- | :--- | :---: | :---: |
| A1 | [**Basics**](https://github.com/stanford-cs336/assignment1-basics/tree/main) <br> [[Leaderboard]](https://github.com/stanford-cs336/assignment1-basics-leaderboard/tree/master) | Tokenizer, Transformer Architecture, Optimizer, Training a minimal LM. | `[ ]` | [Project Link](./Assignments-Projects/A1_Basics/) |
| A2 | [**Systems**](https://github.com/stanford-cs336/assignment2-systems/tree/main) <br> [[Leaderboard]](https://github.com/stanford-cs336/assignment2-systems-leaderboard/tree/main) | Profiling, Benchmarking, Custom Triton Kernel for FlashAttention2, Distributed Training. | `[ ]` | [Project Link](./Assignments-Projects/A2_Systems/) |
| A3 | [**Scaling**](https://github.com/stanford-cs336/assignment3-scaling/tree/main) | Transformer Components Analysis, Fitting Scaling Laws via Training API. | `[ ]` | [Project Link](./Assignments-Projects/A3_Scaling/) |
| A4 | [**Data**](https://github.com/stanford-cs336/assignment4-data/tree/main) <br> [[Leaderboard]](https://github.com/stanford-cs336/assignment4-data-leaderboard) | Processing Common Crawl, Data Filtering, Deduplication. | `[ ]` | [Project Link](./Assignments-Projects/A4_Data/) |
| A5 | [**Alignment**](https://github.com/stanford-cs336/assignment5-alignment) | SFT/RLHF for Math Problems. <br> **Optional Part 2:** [Safety RLHF (PDF)](https://github.com/stanford-cs336/assignment5-alignment/blob/main/cs336_spring2025_assignment5_supplement_safety_rlhf.pdf) | `[ ]` | [Project Link](./Assignments-Projects/A5_Alignment/) |

---

## 🛠️ Resources & Tools

### GPU Compute for Self-Study
If you are following along at home, you can access GPU compute from a cloud provider to complete the assignments. Here are a few options (prices for a single H100 80GB GPU on June 6, 2025):
- **RunPod:** $1.99-$2.99/hour
- **Lambda Labs:** $2.49–$3.29/hour
- **Paperspace:** $2.24/hour
- **Together:** $2.85/hour, minimum 8 GPUs

> **Recommendation:** Debug correctness of your implementation on CPU first and then use GPU(s) for completing training runs (A1, A4, A5) or benchmarking GPU operations (A2).

---

## 🗓️ Lecture Schedule & Notes

| # | Date | Description (Topic) | Materials | Status | My Notes |
| :-: | :--- | :--- | :--- | :---: | :---: |
| 1 | Tues April 1 | Overview, tokenization (Percy) | `lecture_01.py` | `[ ]` | [Notes](./Lectures-Notes/L01_Overview_tokenization.md) |
| 2 | Thurs April 3 | PyTorch, resource accounting (Percy) | `lecture_02.py` | `[ ]` | [Notes](./Lectures-Notes/L02_PyTorch_resource_accounting.md) |
| 3 | Tues April 8 | Architectures, hyperparameters (Tatsu) | `lecture 3.pdf` | `[ ]` | [Notes](./Lectures-Notes/L03_Architectures_hyperparameters.md) |
| 4 | Thurs April 10 | Mixture of experts (Tatsu) | `lecture 4.pdf` | `[ ]` | [Notes](./Lectures-Notes/L04_Mixture_of_experts.md) |
| 5 | Tues April 15 | GPUs (Tatsu) | `lecture 5.pdf` | `[ ]` | [Notes](./Lectures-Notes/L05_GPUs.md) |
| 6 | Thurs April 17 | Kernels, Triton (Tatsu) | `lecture_06.py` | `[ ]` | [Notes](./Lectures-Notes/L06_Kernels_Triton.md) |
| 7 | Tues April 22 | Parallelism (Tatsu) | `lecture 7.pdf` | `[ ]` | [Notes](./Lectures-Notes/L07_Parallelism_Part1.md) |
| 8 | Thurs April 24 | Parallelism (Percy) | `lecture_08.py` | `[ ]` | [Notes](./Lectures-Notes/L08_Parallelism_Part2.md) |
| 9 | Tues April 29 | Scaling laws (Tatsu) | `lecture 9.pdf` | `[ ]` | [Notes](./Lectures-Notes/L09_Scaling_laws_Part1.md) |
| 10 | Thurs May 1 | Inference (Percy) | `lecture_10.py` | `[ ]` | [Notes](./Lectures-Notes/L10_Inference.md) |
| 11 | Tues May 6 | Scaling laws (Tatsu) | `lecture 11.pdf` | `[ ]` | [Notes](./Lectures-Notes/L11_Scaling_laws_Part2.md) |
| 12 | Thurs May 8 | Evaluation (Percy) | `lecture_12.py` | `[ ]` | [Notes](./Lectures-Notes/L12_Evaluation.md) |
| 13 | Tues May 13 | Data (Percy) | `lecture_13.py` | `[ ]` | [Notes](./Lectures-Notes/L13_Data_Part1.md) |
| 14 | Thurs May 15 | Data (Percy) | `lecture_14.py` | `[ ]` | [Notes](./Lectures-Notes/L14_Data_Part2.md) |
| 15 | Tues May 20 | Alignment - SFT/RLHF (Tatsu) | `lecture 15.pdf` | `[ ]` | [Notes](./Lectures-Notes/L15_Alignment_SFT_RLHF.md) |
| 16 | Thurs May 22 | Alignment - RL (Tatsu) | `lecture 16.pdf` | `[ ]` | [Notes](./Lectures-Notes/L16_Alignment_RL_Part1.md) |
| 17 | Tues May 27 | Alignment - RL (Percy) | `lecture_17.py` | `[ ]` | [Notes](./Lectures-Notes/L17_Alignment_RL_Part2.md) |
| 18 | Thurs May 29 | Guest Lecture by Junyang Lin | - | `[ ]` | [Notes](./Lectures-Notes/L18_Guest_Lecture_Junyang_Lin.md) |
| 19 | Tues June 3 | Guest lecture by Mike Lewis | - | `[ ]` | [Notes](./Lectures-Notes/L19_Guest_Lecture_Mike_Lewis.md) |

---

## 📜 Course Policies

### Honor Code
* **Collaboration:** Study groups are allowed, but students must understand and complete their own assignments. If you work in a group, list the members' names at the top of your assignment.
* **AI tools:** Prompting LLMs for low-level programming or high-level conceptual questions is permitted. Using it directly to solve the problem is prohibited. Disabling AI autocomplete (e.g., GitHub CoPilot) is strongly encouraged.
* **Existing code:** You should not look at any existing code unless specified in the handouts.

### Submitting Coursework
* All coursework is submitted via **Gradescope**.
* You can submit as many times as you'd like until the deadline.
* Partial work is better than no work.

### Late Days
* Each student has **6 late days** to use in total.
* A maximum of **3 late days** can be used per assignment.