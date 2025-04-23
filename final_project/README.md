# 🎧 Spotify Music Recommendation Chatbot

This project performs data analysis on a Spotify dataset and implements a simple AI chatbot that recommends songs based on user mood.

## 📁 Dataset
- **Source**: [Hugging Face - maharshipandya/spotify-tracks-dataset](https://huggingface.co/datasets/maharshipandya/spotify-tracks-dataset)
- Contains Spotify track metadata including audio features like danceability, energy, valence, and popularity.

## 🛠️ Technologies Used
- **Language**: Python
- **Notebook**: Jupyter
- **Libraries**: pandas, numpy, seaborn, matplotlib, scikit-learn, torch (optional), datasets

## 📊 Project Structure
- **Data Loading**: Loads dataset using HuggingFace or CSV.
- **Data Cleaning**: Drops duplicates, handles missing values.
- **Exploratory Data Analysis (EDA)**: Descriptive statistics, correlations, visualizations.
- **Feature Engineering**: Scales selected audio features.
- **Model**: Recommends songs using cosine similarity on mood-based feature vectors.
- **Chatbot**: User interface to interactively receive recommendations.

## 🧪 Key Visualizations
- Heatmap of feature correlations
- Bar chart: Top 10 most and least popular genres
- Bar chart: Average duration by genre

## 🧠 Example Code Snippet
```python
def recommend_songs(mood_vector, top_pool=50, select_n=5):
    mood_df = pd.DataFrame([mood_vector], columns=feature_names)
    scaled_mood = scaler.transform(mood_df)
    sims = cosine_similarity(scaled_mood, X)
    top_indices = np.argsort(sims[0])[::-1][:top_pool]
    selected_indices = np.random.choice(top_indices, size=min(select_n, len(top_indices)), replace=False)
    return df.iloc[selected_indices][['track_name', 'artists', 'track_genre', 'popularity']]
```

## 🧩 How to Run the Project
1. Clone this repository
2. Install requirements using `pip install -r requirements.txt`
3. Open `final_project.ipynb` in Jupyter Notebook or JupyterLab
4. Run cells step by step to explore data and interact with the chatbot

## 👨‍💻 Author
- Lukas Volf

## 📜 License
- MIT
