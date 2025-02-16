# 🎬 The Blockbusters: A Data Story

This project is a **data-driven exploration of the movie industry**, visualized through an interactive web story.

🔗 **Live Website:** [The Blockbusters](https://ferioliste.github.io/theblockbusters-datastory/)  
📊 **Data Analysis:** Conducted in a separate repository (not publicly available).  

---

## 📖 Overview  
**The Blockbusters** is a storytelling project that seeks to uncover the key factors that contribute to a movie's success. We combine statistical analysis, data visualization, and interactive storytelling to present our findings in an engaging way.  

The website was built using [`beautiful-jekyll`](https://github.com/daattali/beautiful-jekyll), with extensive modifications to present our research effectively.

---

## 🎯 Research Questions  
### **Main Question:**  
*What factors contribute to the success of a movie?*  

### **Sub-Questions:**  
- 🎟️ *How do we measure success?* Is box office revenue the only metric? Are different metrics correlated?  
- 🎭 *How does the cast impact success?* Does the age or gender of actors and directors influence a movie's performance? Is diversity a factor?  
- 🎬 *Does the movie genre impact its financial or critical performance?*  
- 🌍 *Are certain countries more likely to produce successful movies?*  
- 💰 *How much does the budget and production company affect a film's success?*  

---

## 📊 Data Sources  
We incorporated data from three major sources:

### **1️⃣ The Movie Database (TMDB)**  
   - 📜 **Description:** Provides metadata such as revenue, budget, and genres.  
   - 📌 **Source:** Downloaded from Kaggle.  
   - 🔢 **Size:** ~1.07 million entries, manageable within memory.  

### **2️⃣ Internet Movie Database (IMDB)**  
   - 📜 **Description:** Offers comprehensive movie attributes such as ratings, number of ratings, and cast details.  
   - 📌 **Source:** IMDB Non-Commercial Datasets.  
   - 🔢 **Size:** Too large to fit into memory, so we preprocessed and filtered relevant movie entries.  
   - 📝 **Preprocessing Code:** [`src/scripts/imbd_dataset_filtering.ipynb`](src/scripts/imbd_dataset_filtering.ipynb)  

### **3️⃣ Wikidata**  
   - 📜 **Description:** We built a script using Wikidata Query Service to automatically retrieve extensive metadata on movies and cast members.  
   - 📝 **Preprocessing Code:** [`src/scripts/scrape_wikidata.ipynb`](src/scripts/scrape_wikidata.ipynb)  

---

## 🛠️ Methods & Analysis  
To answer our research questions, we applied the following methodologies:  

- **Statistical Tests**: Used independence tests and Z-tests to compare groups and determine significant differences.  
- **Regression Analysis**:  
  - *Linear Regression*: Assessed relationships between variables (e.g., budget, ratings, revenue, ROI).  
  - *Logistic Regression*: Modeled binary outcomes (e.g., predicting high vs. low success).  
- **Decision Trees**: Used for predictive modeling and explaining key factors influencing movie success.  
- **Data Visualization**: Trends, variability, and uncertainty were explored through detailed plots.  
- **Causal Analysis**:  
  - For U.S. productions, we computed **propensity scores** to control for confounding factors.  
