# Social Media Analytics

---

## Topics

- Data Collection
- Event Detection and Trend Analysis
- User and Community Analysis
- Multimedia and Content Analysis
- Ethics and Privacy

---

## Why Social Media Analytics?

- Social media platforms are a rich source of data
- Applications in marketing, public health, politics, etc.
- Challenges: data volume, velocity, variety, veracity

---

## Data Collection

- APIs: Twitter, Facebook, Instagram, etc.
  - Mostly paid
  - Scraping is an alternative

---

## Noisy User-Generated Text

- Spelling mistakes
- Slang and abbreviations
- Emojis and emoticons
- URLs and hashtags

---

## Approaches to Noisy Text

- Lexicon-based normalisation
- Spell checking
- Slang dictionaries
- Seq2seq models

---

## Event Detection and Trend Analysis

- Event detection: identifying significant events
  - Topics
  - Breaking news
- Trend analysis: identifying patterns in data
  - Sentiment
  - Interest

---

## Unsupervised Event Detection

- Associate posts into topics
  - Latent Dirichlet Allocation: topic modelling based on word frequencies
  - BERTopic: topic modelling based on embeddings
  - Factorization to find latent topics
  - Clustering using k-Means or DBSCAN

---

## Supervised Event Detection

- Train a classifier to detect events
  - Use labelled data
  - Features: text, time, user, etc.
  - Models: SVM, Random Forest, deep learning, etc.

---

## User and Community Analysis

- User sentiment analysis
    - [Google Trends](https://trends.google.com/trends/explore?date=now%201-d&q=artificial%20intelligence&hl=en-GB)
    - [Twitter](https://x.com/explore/tabs/trending)
- Case studies:
    - Disaster monitoring
    - Pandemic prevention
    - Fake news/politics

---

## Social Network Analysis

- Identify communities
- Intersects with graph-based methods
    - Graph Neural Networks

---

## Bot Detection 

- Identify bots in social media
- Use machine learning to detect linguistic and behavioural patterns
- Case studies:
    - [Twitter bots](https://www.pewresearch.org/internet/2018/04/09/bots-in-the-twittersphere/)
    - [Reddit bots](https://www.reddit.com/r/botwatch/)

---

## Stance and Political Discourse Analysis

- Identify political leanings
- Detect hate speech and toxicity
- Explainability is important to guide users to less toxic content

---

## Multimedia and Content Analysis

- Multimedia content types:
    - Textual
    - Image
    - Video
    - Audio

---

## Multimodal Representation Learning

- Learn embeddings of both text and image
- Examples:
    - CLIP: Contrastive Language-Image Pre-training
    - ViLBERT: Vision-and-Language BERT
    - ALIGN: Aligning Latent and Explicit Features for Cross-Modal Retrieval

---

## Multimedia Content Analysis

- The meaning of content cannot be captured by text alone
- Combined analysis of text, image, and video
- Example of this is memes

---

<!-- .slide: data-background="#ccc" -->
![Meme 1](img/meme1.jpeg)

---

<!-- .slide: data-background="#ccc" -->
![Meme 2](img/meme2.webp)

---

<!-- .slide: data-background="#ccc" -->
![Meme 3](img/meme3.jpg)

---

## Ethics and Privacy

- Privacy
    - Exposure of personal information, including medical and financial data
    - Consent and data sharing
- Bias
    - Biased data leads to biased models
    - Fairness and transparency

---

## Ethics and Privacy

- Misinformation
    - Fake news and propaganda
    - Detection and prevention
- Surveillance and Free Speech
    - Monitoring and censorship
    - Balancing free speech and harmful content

---

## NLP Techniques for Ethical Data Processing

- Differential Privacy: adding noise to data to protect privacy
- Federation: apply models on user devices
- Data minimization: collect only necessary data
- Explainability: understand model decisions

---

## Conclusion

- Social media analytics has many applications
- Challenges include data quality and privacy
- NLP techniques can be used to process social media data
- Ethical considerations are important



