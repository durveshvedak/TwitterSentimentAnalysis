# 💬 TwitterSentimentAnalysis

> Real-time Twitter sentiment analysis pipeline powered by AWS SNS, Lambda, and Elasticsearch — streaming, processing, and indexing tweet sentiment at scale.

![Python](https://img.shields.io/badge/Python-3.6+-3776AB?style=flat-square&logo=python&logoColor=white)
![AWS SNS](https://img.shields.io/badge/AWS-SNS-FF9900?style=flat-square&logo=amazonaws&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-indexing-005571?style=flat-square&logo=elasticsearch&logoColor=white)
![Twitter API](https://img.shields.io/badge/Twitter-Streaming_API-1DA1F2?style=flat-square&logo=twitter&logoColor=white)

---

## 📖 Overview

This project builds a fully cloud-native real-time sentiment analysis pipeline for Twitter data. Tweets are streamed live, published to AWS SNS for decoupled processing, and then indexed into Elasticsearch for querying, dashboarding, and analysis — all in near real-time.

## 🏗️ Architecture

```
[Twitter Streaming API]
        │
        ▼
[tweetStream.py]  ──►  Stream & filter tweets
        │
        ▼
[publishsns.py]   ──►  Publish to AWS SNS topic
        │
        ▼
[sns2es.py]       ──►  Subscribe SNS → Elasticsearch index
        │
        ▼
[Kibana Dashboard] ──►  Visualize sentiment in real-time
```

## ✨ Features

- **Live tweet streaming** — Real-time ingestion via Twitter Streaming API
- **AWS SNS pub/sub** — Decoupled, scalable message distribution
- **Elasticsearch indexing** — Full-text search and analytics on tweet data
- **Sentiment scoring** — Classify tweets as positive, negative, or neutral
- **Kibana-ready** — Index structure designed for Kibana dashboard visualization

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Streaming | Python, Twitter API (Tweepy) |
| Message Queue | AWS SNS |
| Search & Analytics | Elasticsearch |
| Visualization | Kibana |

## 🚀 Quick Start

```bash
# Install dependencies
pip install tweepy boto3 elasticsearch

# Configure AWS credentials
aws configure

# Start the tweet streamer
python tweetStream.py

# Publish tweets to SNS
python publishsns.py

# Bridge SNS to Elasticsearch
python sns2es.py
```

## 📂 Repo Structure

```
├── tweetStream.py    # Twitter Streaming API consumer
├── publishsns.py     # AWS SNS publisher
└── sns2es.py         # SNS to Elasticsearch bridge
```

---

<p align="center">Made with ❤️ by <a href="https://github.com/durveshvedak">Durvesh Vedak</a></p>
