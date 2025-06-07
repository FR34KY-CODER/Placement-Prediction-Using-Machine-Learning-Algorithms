# 🎓 Placement Predictor

![Banner Image](https://source.unsplash.com/1600x400/?data,machine-learning)

*“From Jupyter experiments to a live Streamlit app — what a ride!”*  
[🚀 Live Demo](https://placement-prediction-using-machine-learning-algorithms-cmy2s3s.streamlit.app/)

---

## 📌 Table of Contents

- [About the Project](#about-the-project)  
- [Model Journey & Challenges](#model-journey--challenges)  
- [Features](#features)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Deployment](#deployment)  
- [Screenshots & Memes](#screenshots--memes)  
- [Acknowledgements](#acknowledgements)

---

## 📖 About the Project

This repo contains a **Placement Predictor** web app built with **Streamlit**.  
Given a student’s academic profile, it predicts whether they will get placed in campus recruitment.

Under the hood:
- 📦 Preprocessing + Model are wrapped in a single `sklearn` **Pipeline**
- 📊 Logistic Regression with `class_weight='balanced'` powers the prediction
- ✨ Custom dark-themed UI with purple-orange gradient

---

## 🔍 Model Journey & Challenges

1. **Initial Prototype in Jupyter Notebook**
   - Tried an **SVM (linear kernel)** — it actually outperformed Logistic Regression in terms of accuracy.
   - However:
     - SVM with `probability=True` is **slow**
     - It returned **extreme probability scores (0% or 100%)**
     - Couldn’t interpret middle confidence scores reliably

2. **Switch to Logistic Regression**
   - Provided smoother and **more calibrated probabilities**
   - Supported `class_weight='balanced'` to handle imbalance in “Placed” vs “Not Placed”
   - More compatible with web deployment due to lighter model size and better performance on new inputs

3. **Streamlit Integration**
   - Built a three-column form layout
   - Used `@st.cache_resource` instead of deprecated `@st.cache`
   - Removed aggressive outlier filtering to keep students with high scores (90%+)

4. **Deployment Woes & Wins**
   - Resolved local Python path issues using: `python -m streamlit run streamlit_app.py`
   - Fixed CSS for dark mode gradient
   - Resized header banner to avoid pushing the UI down
   - Successfully deployed to Streamlit Cloud 🎉

---

## ✨ Features

- 📈 End-to-end ML pipeline using `scikit-learn`
- 🧠 Predicts placement based on academic background
- 🎨 Dark-themed UI with modern styling
- 🔁 Cached model for fast prediction
- 🚀 Deployed app ready for real-world use

---

## 🛠️ Installation

1. **Clone the repo**
   ```bash
   git clone https://github.com/yourusername/placement-predictor.git
   cd placement-predictor
   ```

2. **(Optional) Setup a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate     # macOS/Linux
   venv\Scripts\activate        # Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

---

## 🚦 Usage

1. **Train or retrain the model**
   ```bash
   python train_and_save_model.py
   ```
   This generates `placement_pipeline.pkl`.

2. **Launch the Streamlit app**
   ```bash
   python -m streamlit run streamlit_app.py
   ```

3. **Visit** `http://localhost:8501` in your browser.

---

## 🌐 Deployment

This project is deployed on **Streamlit Cloud**  
👉 [**Live Demo**](https://placement-prediction-using-machine-learning-algorithms-cmy2s3s.streamlit.app/)

To deploy it yourself:

1. Push this repo to GitHub  
2. Go to [Streamlit Cloud](https://streamlit.io/cloud) → **New app**  
3. Choose your repo → Main file: `streamlit_app.py` → Deploy  
4. Done. 🎉

---

## 📸 Screenshots & Memes

### Dark Theme Vibes
![Dark UI](https://source.unsplash.com/800x400/?dark,code)

### When your model *finally* predicts “PLACED”
![Success Kid](https://media.giphy.com/media/111ebonMs90YLu/giphy.gif)

### Watching SVM model eat your RAM:
![SVM Meltdown](https://media.giphy.com/media/TilmLMmWrRYYHjLfub/giphy.gif)

### Me, waiting for deployment to finish:
![Waiting GIF](https://media.giphy.com/media/3o7TKrjz5Tx5ZS6bGM/giphy.gif)

---

## 🙌 Acknowledgements

- Built with ❤️ by **FR34K (Ojasvi Goyal)**
- Thanks to:
  - **Streamlit** for the lightning-fast app framework
  - **Scikit-learn**, **Pandas**, and **Matplotlib** for model building
  - **GIPHY** and **Unsplash** for visual content

---

> _“Machine Learning is like teenage sex: everyone talks about it, nobody really knows how to do it, everyone thinks everyone else is doing it, so everyone claims they are doing it…”_ 😄

---
