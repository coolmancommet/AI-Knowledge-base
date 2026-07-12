# Recommendation System Design – Interview Preparation Roadmap

## 1. Fundamentals of Recommendation Systems

### What is a Recommendation System?
A system that predicts user preferences and recommends relevant items.

[good but not that informative in matrix and jacard similarity](https://medium.com/double-pointer/system-design-interview-recommendation-system-design-as-used-by-youtube-netflix-etc-c457aaec3ab)

[better explaination of simple reco sys](https://milvusio.medium.com/accelerating-candidate-generation-in-recommender-systems-using-milvus-paired-with-paddlepaddle-88335a5eacc2)

[good simple model explanation of recosys](https://bytebytego.com/courses/machine-learning-system-design-interview/video-recommendation-system)

### Core Objectives
- Personalization  
- Relevance  
- Engagement optimization  
- Long-term retention  

---

## 2. Types of Recommenders

### 2.1 Content-Based Filtering

**Idea**  
Recommend items similar to what the user liked in the past.

**Uses**
- User features (demographics, behavior)  
- Item features (text, category, metadata)  
- Similarity metrics (cosine similarity, dot product)  

**Common Techniques**
- TF-IDF + cosine similarity  
- Word2Vec / Doc2Vec  
- BERT embeddings  
- Feature engineering + logistic regression  

**Pros**
- No need for other users  
- Easy cold start for items  
- Interpretable  

**Cons**
- Limited discovery  
- Over-specialization  
- Requires rich item features  

**Learn From**
- Google ML Crash Course  
- Hands-On ML with Scikit-Learn  
- sklearn documentation  

---

### 2.2 Collaborative Filtering

**Idea**  
Users who behaved similarly in the past will behave similarly in the future.

**User-Based CF**
- Find similar users  
- Recommend items liked by similar users  

**Item-Based CF**
- Find similar items  
- Recommend items co-interacted with  

**Pros**
- No manual feature engineering  
- Captures collective intelligence  

**Cons**
- Cold start problem  
- Sparse matrices  
- Scalability issues  

**Learn From**
- Surprise Library documentation  
- Stanford CS246  

---

## 3. Matrix Factorization

**Core Idea**

R ≈ U × Vᵀ  
U = user embeddings  
V = item embeddings  

### SVD
- Works well for dense matrices  
- Used in Netflix Prize  

### ALS
- Better for sparse implicit feedback  
- Scales well in distributed systems (Spark MLlib)  

**Why Important**
- Foundation for embedding-based models  
- Leads to Two-Tower architecture  

**Learn From**
- Stanford notes on matrix factorization  
- Spark MLlib ALS docs  
- Netflix Prize papers  

---

## 4. Deep Learning Recommenders

### 4.1 Two-Tower Model

**Architecture**
User features → User tower → User embedding  
Item features → Item tower → Item embedding  
Dot product → Score  

**How It Works**
- Two separate neural networks  
- Embeddings stored in vector database  
- Retrieval via ANN search  

**At Scale**
- Precompute item embeddings  
- Store in FAISS, ScaNN, Milvus  
- Use approximate nearest neighbor search  

**Learn From**
- Eugene Yan’s blog  
- TensorFlow Recommenders  
- YouTube DNN recommendation paper  

---

### 4.2 Neural Collaborative Filtering
- Replaces dot product with MLP  
- Learns non-linear interactions  

Reference: Neural Collaborative Filtering (He et al., 2017)

---

### 4.3 Sequential Recommendation

**Problem**  
Order of interactions matters.

**Models**
- RNN / LSTM  
- GRU4Rec  
- Transformers (SASRec, BERT4Rec)  

---

## 5. Ranking Pipeline Architecture

Typical production pipeline:

User request  
→ Candidate generation  
→ Ranking model  
→ Re-ranking  
→ Final recommendations  

### Candidate Generation
- Two-Tower model  
- ANN search  
- Collaborative filtering  

Goal: Reduce millions of items to a few hundred candidates.

### Ranking
- Gradient boosted trees (XGBoost)  
- Deep neural networks  
- Wide & Deep model  

Optimizes CTR, watch time, conversion.

### Re-Ranking
- Diversity injection  
- Freshness boosting  
- Business constraints  
- Fairness adjustments  

---

## 6. Cold Start Problem

### New User
- Popularity-based fallback  
- Onboarding questionnaire  
- Context-based recommendations  
- Demographic features  
- Session-based recommendations  

### New Item
- Content embeddings  
- Metadata features  
- Hybrid systems  
- Exploration traffic (multi-armed bandits)  

---

## 7. Evaluation Metrics

### Offline Metrics
- Precision@K  
- Recall@K  
- MAP  
- NDCG  
- AUC  

Reference: NDCG Explained (Towards Data Science) [ndcg](https://towardsdatascience.com/demystifying-ndcg-bee3be58cfe0/)

### Online Metrics
- CTR  
- Watch time  
- Conversion rate  
- Retention  
- Revenue per user  

**Common Interview Question**  
Why might offline metrics improve while online metrics drop?

Possible reasons:
- Offline data bias  
- Feedback loops  
- Exploration vs exploitation mismatch  
- Metric misalignment  
- Distribution shift  

---

## 8. Scalability and Infrastructure

### ANN Search
- FAISS  
- ScaNN  
- HNSW  [vid](https://www.youtube.com/watch?v=77QH0Y2PYKg&t=12s)
- Annoy  

### Vector Databases
- Pinecone  
- Milvus  
- Weaviate  
- Elasticsearch  

### Caching
- Redis  
- Memcached  

### Distributed Training
- Spark  
- PyTorch DDP  
- Parameter servers  

### Streaming Pipelines
- Kafka  
- Flink  
- Beam  
- Real-time feature stores  

---

## 9. Advanced Topics

### Hybrid Recommenders
Combine content-based and collaborative methods.

### Multi-Armed Bandits
- Exploration vs exploitation  
- Thompson sampling  
- UCB  

### Reinforcement Learning
- Long-term reward optimization  
- Session-level optimization  

### Diversity and Fairness
- Filter bubbles  
- Bias mitigation  
- Exposure fairness  

### Feature Engineering
- Crossed features  
- Temporal decay features  
- Interaction frequency  
- Context features (device, time, location)  

---

## 10. Must-Know Interview Questions

1. How do you solve cold start for new users and new items?  
2. Explain the Two-Tower architecture. Where are embeddings stored? How is dot product computed at scale?  
3. Difference between offline and online metrics?  
4. Design a YouTube or Netflix recommender system.  
5. How do you handle data sparsity?  
6. How do you introduce diversity?  

---

## 11. Best Learning Resources

### Fundamentals
- Google ML Crash Course  
- Stanford CS246  
- Fast.ai Collaborative Filtering  

### Blogs
- Eugene Yan  
- Netflix Tech Blog  
- YouTube Engineering Blog  
- Pinterest Engineering Blog  

### Libraries
- Surprise  
- LightFM  
- TensorFlow Recommenders  
- implicit (ALS)  
- FAISS  

GitHub resource:  
https://github.com/ashishps1/awesome-system-design-resources