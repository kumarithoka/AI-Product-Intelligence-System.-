
# 🛍️ AI-Powered Product Intelligence System

An enterprise-grade, multi-modal e-commerce intelligence system built using OpenAI's **CLIP (Contrastive Language-Image Pre-training)** model and vector similarity search. 

This project bridges visual and semantic text concepts into a shared 512-dimensional vector embedding space to solve three major e-commerce catalog challenges: intelligent outfit recommendations, multi-seller catalog deduplication, and natural language reverse product search.

---

## 🚀 Key Features Built

### 1. 🎯 Smart Complementary Recommendation Engine
* **The Challenge:** Traditional recommendation engines only suggest visually identical items (e.g., showing more shirts when viewing a shirt).
* **The Solution:** Implemented a hybrid **Rule-Based + AI Vector** approach that maps categories to logical companion accessories (e.g., pairing running shoes with socks, fitness watches, and gym bags).
* **Demographic & Occasion Locking:** Features strict metadata filtering (`gender`, `usage`) before applying vector math to prevent incompatible pairing (e.g., ensuring men's formal attire is not paired with women's athletic wear).
* **Style Alignment:** Utilizes Cosine Similarity across image embeddings to ensure recommended outfit pieces match the color palette and aesthetic vibe of the input item.

### 2. 🧹 Automated Catalog Deduplication
* **The Challenge:** Multi-seller marketplaces suffer from catalog clutter caused by identical or slightly modified product image uploads across different seller accounts.
* **The Solution:** Computed a full pairwise cosine similarity matrix across product embeddings to measure exact mathematical visual distances.
* **Threshold Clustering:** Applied an automated threshold algorithm ($\ge 0.92$ similarity score) to autonomously detect near-duplicate images, isolate redundant seller listings, and generate a clean, unique canonical product catalog.

### 3. 🔍 Reverse Product Search (Text-to-Image)
* **The Challenge:** Standard keyword searches fail when sellers omit crucial metadata tags or descriptions.
* **The Solution:** Leveraged CLIP's multi-modal architecture to project natural language text queries (e.g., *"blue casual shirt"* or *"sporty running shoes"*) directly into the visual vector space.
* **Semantic Retrieval:** Calculates cross-modal cosine similarity between the text query vector and pre-computed product image vectors, ranking and retrieving the most relevant visual products instantly without relying on text tags.

---

## 🛠️ Technical Stack
* **Language:** Python 3
* **AI / Deep Learning:** `sentence-transformers`, OpenAI CLIP (`clip-ViT-B-32`)
* **Data Manipulation & Math:** `pandas`, `numpy`, `scikit-learn` (Cosine Similarity, Agglomerative Clustering)
* **Visualization & Image Processing:** `matplotlib`, `PIL` (Pillow)
* **Environment:** Google Colab / Jupyter Notebook

---

## 📁 Repository Structure
* **`Gen_AI_Bootcamp_Day2_Source_Code.ipynb`**: Complete executable Python notebook containing dataset ingestion, vector embedding generation, and all three task pipelines.
* **`Gen_AI_Bootcamp_Day2_Homework_Report.pdf`**: Comprehensive technical documentation detailing architecture design, mathematical formulas, and visual proof/screenshots of all outputs.

---

## 💡 How to Run Locally or in Colab
1. Clone this repository or open the `.ipynb` notebook in Google Colab.
2. Install the required libraries:
   ```bash
   pip install sentence-transformers pandas numpy scikit-learn matplotlib pillow
