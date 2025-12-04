# 🧥 AI Fashion Recommendation System  
**Image Similarity • Text Search • Upload Search • Vibe Matching**  
Built with **FastAI, ResNet18, Annoy, PIL, Gradio**

---

## 🚀 Overview

This project is an **AI-powered Fashion Recommendation System** that finds visually similar fashion products using deep learning and vector similarity search.

The system supports **four powerful recommendation modes**:

1. **Search by Index** — Select any dataset image index to view similar items  
2. **Search by Text** — Search via subcategory names (e.g., "shoes", "bags")  
3. **Search by Image Upload** — Upload your own image and get similar recommendations  
4. **Vibe Match** — Enter multiple indices or keywords and get items matching the combined “vibe”

This project uses:

- **FastAI + ResNet18** for feature extraction  
- **Annoy (Approximate Nearest Neighbor)** for fast vector search  
- **PIL** for image handling  
- **Gradio** for an interactive UI  

---

## 📦 Features

### ✅ **1. Image-Based Similarity Search**  
Extract embeddings from the penultimate layer of ResNet18 and retrieve visually similar images using Annoy.

### ✅ **2. Text-Based Search**  
Enter text like `"shirts"`, `"jeans"`, `"watches"` to retrieve related items using semantic search.

### ✅ **3. Image Upload Search**  
Upload an image → embedding is generated → system returns similar fashion items.

### ✅ **4. Vibe Matcher**  
Combine multiple items or keywords to generate a **blended style vibe**.

Examples:

- Indices: `10, 25, 87`  
- Keywords: `shoes, blue shirt, backpack`

---

## 📁 **Project Structure**

```
Project1/
│── fashion_rec.ipynb       # Main notebook (training + ANN + UI)
│── app/                    # Optional UI code
│── models/                 # Saved ANN index / intermediate models
│── data/                   # Dataset folder (ignored by git)
│── requirements.txt        # Dependencies
│── README.md               # This file
│── LICENSE                 # MIT License
```

---

## 📥 **Dataset**

This project uses the **Fashion Product Images (Small)** dataset:

📌 **Kaggle:**  
https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-small

After extraction, your dataset should look like:

```
fashion_data/
│── images/
│     ├── 10001.jpg
│     ├── 10002.jpg
│     ├── ...
│── styles.csv
```

---

## 🧠 **Model & Embeddings**

- **Model:** ResNet18 (FastAI)  
- **Embedding Dimension:** 512  
- **ANN Index:** Annoy (Euclidean distance)  
- **Trees:** 10  

### Example embedding extraction:

```python
penultimate = learn.model[1][-2]
hook = FeatureHook(penultimate)
```

### Saved Annoy index:

```
fashion_annoy.ann
```

---

## 🖥️ **How to Run (Local or Colab)**

### 🔹 1. Clone the Repository

```bash
git clone https://github.com/Harru95/Project1
cd Project1
```

### 🔹 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 🔹 3. Open the Notebook

Open `fashion_rec.ipynb` in:

- Google Colab  
- VS Code  
- Jupyter Notebook  

Run all cells.

### 🔹 4. Launch the Gradio App

```python
demo.launch()
```

You will see a URL like:

```
Running on public URL: https://xxxx.gradio.live
```

---

## 🧪 **Sample Inputs for Testing**

### 🔸 Index Search  
```
Index: 50
Recommendations: 5
```

### 🔸 Text Search  
```
shoes
tshirts
bags
```

### 🔸 Vibe Match (Indices)  
```
10, 25, 87
```

### 🔸 Vibe Match (Text)  
```
shoes, blue, backpack
formal shirt, watch
```

### 🔸 Image Upload  
Upload any fashion image (shirt, shoe, watch, bag, etc).

---

## 📝 **License**

This project is released under the **MIT License**.  
You may freely use, modify, and distribute it.

---

## 🙌 **Author**

**Harsh Soni**  
GitHub: https://github.com/Harru95  
LinkedIn: https://linkedin.com/in/harsh-soni-7819522a41

⭐ *If you found this project helpful, please give it a star on GitHub!*
