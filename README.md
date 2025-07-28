# Can Generative AI infer financial actions from social media posts?

## 🧾 Abstract

The literature demonstrated that the dissemination and exchange of information online, including investor sentiment, emerging market trends, and sector-specific developments, can significantly influence stock market dynamics. To fully leverage the informational potential of online platforms, it is essential to accurately identify and interpret investment-related suggestions expressed in user-generated content. In this paper, we define and explore a novel task, Social Trading Action Detection, which involves classifying online posts according to the user’s recommendation to purchase or sell a specific stock. We investigated a broad range of natural language processing approaches for this task, including: 1) nine traditional neural network classifiers; 2) three zero-shot sequence classifiers; 3) twenty-three Large Language Models (LLMs) evaluated in zero-shot settings; and 4) twenty-two LLMs evaluated in fine-tuned settings. To support this analysis, we introduce FinReddit-2K, a novel dataset consisting of 2,123 Reddit posts manually annotated by domain experts. Our findings indicate that LLMs clearly outperform traditional methods. In particular, the LLMs fine-tuned on FinReddit-2K demonstrate excellent performance, with Mistral-7B achieving the highest F1 score (86.0%), followed by Neural-chat-7B (84.7%) and Phi 4-14B (84.6%).

---

## 📘 Introduction
This project introduces the novel task of **Social Trading Action Detection (STAD)**, which goes beyond sentiment classification to directly infer trading actions from financial discussions. To support this task, we present **FinReddit**, a new manually annotated dataset of Reddit posts, and benchmark a variety of machine learning and large language models to assess their effectiveness in identifying these actions: *buy*, *sell*, or *other*.

This repository provides:

- 📝 A manually annotated dataset of Reddit posts labeled as `buy`, `sell`, or `other`
- 🐍  A Python module for text preprocessing, used to clean and prepare posts before modeling

All experiments were conducted using the FinReddit dataset on a machine equipped with an NVIDIA A100-SXM4 GPU (80GB memory). We evaluated four families of models through a **5-fold stratified cross-validation**, ensuring class balance across folds.

---

## 📂 Repository Structure

```bash
📦 FINREDDIT-2K/
├── FinReddit-2K.csv       # Sample dataset with annotated trading actions
├── README.md              # Project overview and documentation
└── text_cleaning.py       # Preprocessing function for cleaning Reddit text
```

### 🗂️ FinReddit-2K dataset

The dataset consists of 2,123 manually annotated Reddit posts. It has the following structure:

| Column  | Description                                            |
|---------|--------------------------------------------------------|
| `text`  | The raw content of the Reddit post                     |
| `label` | The associated trading action: `buy`, `sell`, or `other` |


## 👥 Authors

[**Simone D'Amico**](https://orcid.org/0009-0002-2820-0277), Department of Electrical Engineering and Information Technology, University of Naples Federico II, Naples, Italy

[**Andrea Maurino**](https://orcid.org/0000-0001-9803-3668), Department of Informatics, Systems and Communication, University of Milano-Bicocca, Milan, Italy

[**Francesco Osborne**](https://orcid.org/0000-0001-6557-3131), Department of Business and Law, University of Milano-Bicocca, Milan, Italy

[**Giancarlo Sperlì**](https://orcid.org/0000-0003-4033-3777), Department of Electrical Engineering and Information Technology, University of Naples Federico II, Naples, Italy




## ✅ License

This project is released under the [MIT License](LICENSE).

