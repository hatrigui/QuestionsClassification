# QuestionsClassification

This repository is designed to explore and compare various methods for question classification. The **main branch** serves as the starter branch, containing the initial notebook. You can explore other branches to see the contributions of the three authors.

## Branch Information

- **QC.pdf** contains the presentation of the project.

## 📖 **Project Overview**  
This project aims to classify questions into predefined categories using classical machine learning, deep learning, and transformer-based approaches. The goal is to compare these methods and evaluate their effectiveness in the task of question classification.

---

## 🚀 **Objective**  
The project focuses on classifying questions from the TREC dataset into coarse and fine-grained categories. We explore several methodologies, from traditional techniques like Logistic Regression and SVM to advanced deep learning models (LSTM) and transformer-based architectures (e.g., Phi-4).

---

## 🗂 **Dataset**  
- **TREC Dataset**:  
  - **Coarse Classes**: 6 categories (e.g., DESCRIPTION, LOCATION)  
  - **Fine-Grained Classes**: 50 classes (e.g., DESC:manner, LOC:city)  
  - **Train Set**: 5,452 questions  
  - **Test Set**: 500 questions  
- **Challenges**:  
  - Class imbalance  
  - Ambiguity in multi-label classification  

---

## 🧰 **Preprocessing**  
- Lowercasing, removing non-alphabetic characters, tokenization  
- Stopword removal (retaining WH-words), lemmatization  
- Label encoding using `LabelEncoder`

---

## 🛠 **Approaches Explored**  

### **Classical Machine Learning**  
- **TF-IDF + Logistic Regression**: Achieved 71% accuracy, but struggled with class imbalance.  
- **SMOTE Oversampling**: Improved weighted F1-score to 0.77.  
- **XGBoost**: Combined with SMOTE and hyperparameter tuning, achieved 77% accuracy.  
- **BOW + WordNet Synsets + SVM**: Best classical approach with 81% accuracy, leveraging semantic context.

### **Deep Learning**  
- **LSTM with Embedding Layer**: Baseline model achieved 57.6% accuracy but suffered from overfitting.  
  - **Mitigation**: L1/L2 regularization, dropout, class weights.  
- **Pretrained GloVe Embeddings**:  
  - GloVe 300d vectors achieved 68.2% accuracy.  
  - Larger embeddings (840B Common Crawl) improved results to 71.8% accuracy.

### **Transformer-Based Approach**  
- **Transformer Models**: Explored architectures like Transformer with attention mechanisms.  
- **Challenges**: High computational cost of large language models (LLMs) and the potential of smaller models like Phi-4 for specific tasks.

---

## 📊 **Results Summary**  

| Approach               | Best Model                         | Accuracy | F1-Score |
|------------------------|-------------------------------------|----------|----------|
| Classical ML           | BOW + WordNet Synsets + SVM        | 81%      | 0.80     |
| Deep Learning (LSTM)   | GloVe 300d + LSTM                  | 68.2%    | 0.70     |
| Deep Learning (GloVe)  | Common Crawl Embeddings            | 71.8%    | 0.70     |

---

## 🎯 **Challenges Addressed**  
- **Class Imbalance**: SMOTE, class weights, and `scale_pos_weight` in XGBoost.  
- **Overfitting in DL Models**: Dropout, regularization, and learning rate adjustments.  
- **Semantic Granularity**: Handled using WordNet Synsets and transformer attention mechanisms.

---

## 🚀 **Future Directions**  
- Exploring smaller, task-specific language models like Phi-4 to reduce computational costs.  
- Enhancing the explainability of transformer models.  
- Improving zero-shot/few-shot learning capabilities.
