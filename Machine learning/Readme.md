# Machine Learning Study Guide & Checklist

## Module 1: Core ML Concepts & Evaluation

### Checklist

* [ ] **Supervised vs. Unsupervised vs. Reinforcement Learning**
* [ ] **Classification vs. Regression**
* [ ] **Bias-Variance Tradeoff**
* [ ] **Overfitting vs. Underfitting**
* [ ] **Cross Validation**
* [ ] **Feature Engineering**
* [ ] **Evaluation Metrics:**
* [ ] Accuracy
* [ ] Precision / Recall
* [ ] F1 Score
* [ ] ROC-AUC
* [ ] RMSE / MAE



### 📖 Core Explanations

#### Bias-Variance Tradeoff

The bias-variance tradeoff is the balancing act between a model being too simple (high bias) and too complex (high variance). The goal is to find the optimal point of model complexity that minimizes total error, allowing the model to accurately predict unseen data.

* **Bias:** The error caused by overly simplistic assumptions in the learning algorithm. A model with high bias pays little attention to the training data, consistently missing the true underlying pattern (leading to **underfitting**).
* **Variance:** The error caused by the model being overly sensitive to small fluctuations in the training data. A model with high variance essentially memorizes the training data—including noise—but fails to generalize to new, unseen data (leading to **overfitting**).
* **The Dilemma:** You cannot simultaneously minimize both. As you increase model complexity to learn deeper patterns (reducing bias), the model becomes more susceptible to data noise (increasing variance).

Mathematically, the total generalization error of a machine learning model is broken down as follows:


$$\text{Total Error} = \text{Bias}^2 + \text{Variance} + \text{Irreducible Error}$$

* **$\text{Bias}^2$:** Measures how far the model's predictions are from the correct values on average.
* **$\text{Variance}$:** Measures how much the predictions fluctuate around the average when trained on different datasets.

#### Cross-Validation

The goal of cross-validation isn't to build your final model. The goal is to evaluate how well your chosen algorithm and hyperparameters generalize to unseen data. Once you are satisfied with your cross-validation score, you usually create one final, brand-new model and train it on the entire 100% of the dataset before deploying it.

### 📍 Where to Learn

* **Concepts:** *StatQuest with Josh Starmer (YouTube)* – The best resource for breaking down Bias-Variance, ROC-AUC, and Cross-Validation.
* **Reading:** *An Introduction to Statistical Learning (ISLR)* (Free PDF available online) for fundamental math and intuition.
* **Metrics:** *Scikit-Learn Metrics Documentation* – Excellent explanations of when to use which metric.
* Medium articles :
  * https://medium.com/@bensalemh300/supervised-vs-unsupervised-vs-reinforcement-learning-a3e7bcf1dd23
  * https://www.ibm.com/think/topics/classification-vs-regression
  * https://medium.com/image-processing-with-python/theoretical-basis-of-ml-model-evaluation-metrics-summary-3cae19129679
### ❓ Must-Know Interview Questions

1. How do you handle a highly imbalanced dataset (e.g., 99% negative, 1% positive)?
2. When would you prioritize Recall over Precision, and vice versa? Give real-world examples.
3. Explain the Bias-Variance tradeoff. What happens to bias and variance as you increase the depth of a Decision Tree?
4. What is data leakage in cross-validation, and how do you prevent it?

---

## Module 2: Important Algorithms

### Checklist

* **Linear Models**
* [ ] Linear Regression 
  * https://machinelearningmastery.com/linear-regression-for-machine-learning/
* [ ] Logistic Regression
  * https://christophm.github.io/interpretable-ml-book/logistic.html


* **Tree-Based Models**
* [ ] Decision Trees
  * https://medium.com/@abhishekjainindore24/all-about-decision-trees-80ea55e37fef
* [ ] Random Forest
* [ ] XGBoost / LightGBM / CatBoost


* **Clustering**
* [ ] K-Means
  * https://medium.com/@laakhanbukkawar/understanding-k-means-and-k-means-a-comprehensive-guide-4b288a6bf218
* [ ] DBSCAN
  * https://medium.com/@kaleemullahyounas123/dbscan-another-clustering-algorithm-for-machine-learning-89885f555a2e
* [ ] Hierarchical Clustering


* **Dimensionality Reduction**
* [ ] PCA
  * https://www.youtube.com/watch?v=FgakZw6K1QQ
* [ ] t-SNE
* [ ] UMAP
  * https://pair-code.github.io/understanding-umap/

* **Neural Networks**
* [ ] MLP
* [ ] CNN
* [ ] RNN / LSTM
* [ ] Transformers



### 📍 Where to Learn

* **Trees & Ensembles:** *XGBoost Documentation* (Read the "Introduction to Boosted Trees").
* **Dimensionality Reduction:** *StatQuest* on PCA and t-SNE vs *UMAP visualizer* by Google.
* **Clustering:** *Scikit-Learn's clustering guide* provides great visual comparisons of K-Means vs. DBSCAN.

### ❓ Must-Know Interview Questions

1. What is the fundamental difference between Bagging (Random Forest) and Boosting (XGBoost)?
2. Walk me through the math of Logistic Regression. What is the output strictly representing?https://medium.com/analytics-vidhya/the-math-behind-logistic-regression-c2f04ca27bca
3. Why does K-Means struggle with non-spherical clusters, and how does DBSCAN solve this?
4. In PCA, what are eigenvalues and eigenvectors, and what do they represent physically in the data?