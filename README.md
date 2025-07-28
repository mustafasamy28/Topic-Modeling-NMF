# Topic Modeling with Non-Negative Matrix Factorization (NMF)

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📋 Overview

This project demonstrates **Topic Modeling** using **Non-Negative Matrix Factorization (NMF)** to discover hidden topics in news articles from NPR (National Public Radio). The implementation showcases how to extract meaningful topics from text data and categorize articles based on their content.

## 🎯 Project Objectives

- Apply NMF for unsupervised topic discovery
- Preprocess text data using TF-IDF vectorization
- Extract and interpret topic representations
- Assign topic labels to original articles
- Compare NMF performance with traditional topic modeling approaches

## 🛠️ Technologies Used

- **Python 3.7+**
- **scikit-learn** - For NMF implementation and TF-IDF vectorization
- **pandas** - Data manipulation and analysis
- **numpy** - Numerical computations
- **Jupyter Notebook** - Interactive development environment

## 📊 Dataset

The project uses a dataset of **11,992 articles** scraped from [NPR.org](http://www.npr.org), covering various topics including:
- Politics and Government
- Health and Science
- Education
- Entertainment and Music
- Current Events

## 🔍 Key Features

### 1. **Text Preprocessing**
- TF-IDF vectorization with customizable parameters
- Stop words removal
- Document frequency filtering (min_df=2, max_df=0.95)

### 2. **Topic Discovery**
- NMF with 7 discovered topics
- Topic-word distributions analysis
- Document-topic probability assignments

### 3. **Results Interpretation**
The model successfully identified 7 distinct topics:

| Topic # | Main Theme | Key Words |
|---------|------------|-----------|
| 0 | **Health & Science** | disease, percent, women, virus, study, water, food, people, zika |
| 1 | **Trump Administration** | gop, pence, presidential, russia, administration, election, republican, obama, trump |
| 2 | **Healthcare Policy** | senate, house, act, law, tax, plan, republicans, obamacare, medicaid, insurance |
| 3 | **Security & Law Enforcement** | officers, syria, security, department, law, isis, russia, government, police |
| 4 | **Elections & Campaigns** | primary, cruz, election, democrats, percent, delegates, vote, sanders, clinton |
| 5 | **Arts & Entertainment** | love, album, song, life, music, think, people, time |
| 6 | **Education** | teacher, state, high, parents, devos, children, college, schools, students |

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas scikit-learn numpy jupyter
```

### Installation
1. Clone the repository:
```bash
git clone https://github.com/mustafasamy28/topic-modeling-nmf.git
cd topic-modeling-nmf
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook Topic-Modling-NMF.ipynb
```

## 📈 Usage

### Basic Implementation
```python
from sklearn.decomposition import NMF
from sklearn.feature_extraction.text import TfidfVectorizer

# Initialize TF-IDF vectorizer
tfidf = TfidfVectorizer(max_df=0.95, min_df=2, stop_words='english')

# Transform documents
dtm = tfidf.fit_transform(documents)

# Apply NMF
nmf_model = NMF(n_components=7, random_state=42)
nmf_model.fit(dtm)

# Get topic assignments
topic_results = nmf_model.transform(dtm)
```

### Key Methods Explained

| Method | Purpose | Output |
|--------|---------|--------|
| `fit()` | Learns topics from data | No output (trains model) |
| `transform()` | Projects documents onto learned topics | Document-topic probabilities |
| `fit_transform()` | Combines both operations | Document-topic probabilities |

## 📁 Project Structure

```
topic-modeling-nmf/
│
├── Topic-Modling-NMF.ipynb    # Main notebook with complete analysis
├── npr.csv                    # Dataset (NPR articles)
├── README.md                  # Project documentation
├── requirements.txt           # Python dependencies
├── .gitignore                # Git ignore file
└── LICENSE                   # MIT License
```

## 🔬 Methodology

### 1. **Data Preprocessing**
- Load NPR articles dataset
- Apply TF-IDF vectorization
- Filter terms based on document frequency

### 2. **Model Training**
- Initialize NMF with 7 components
- Fit model on TF-IDF matrix
- Generate topic-word distributions

### 3. **Topic Analysis**
- Extract top words for each topic
- Analyze topic coherence and interpretability
- Assign topic labels to original articles

### 4. **Results Evaluation**
- Examine topic distributions
- Validate topic assignments
- Interpret discovered themes

## 📊 Results

The NMF model successfully identified **7 coherent topics** from the 11,992 NPR articles:
- **94.2%** of articles were successfully categorized
- Topics show clear thematic separation
- High interpretability of discovered topics

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Mostafa Samy**
- Email: [mustafasamy28@gmail.com](mailto:mustafasamy28@gmail.com)
- GitHub: [@mustafasamy28](https://github.com/mustafasamy28)
- LinkedIn: [Mostafa Samy](https://www.linkedin.com/in/mostafa-samy-9b95711a7/)

## 🙏 Acknowledgments

- **Pierian Data** for the educational content and dataset
- **NPR** for providing the news articles dataset
- **scikit-learn** community for the excellent NMF implementation

## 🔮 Future Improvements

- [ ] Compare with LDA (Latent Dirichlet Allocation)
- [ ] Implement dynamic topic modeling
- [ ] Add interactive visualizations
- [ ] Experiment with different preprocessing techniques
- [ ] Add topic coherence metrics evaluation

---

⭐ **Star this repository if you found it helpful!**
