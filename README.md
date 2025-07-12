#  Movie Recommendation System

[![Made with Python](https://img.shields.io/badge/Made%20with-Python-blue)](https://www.python.org/)
[![Jupyter Notebooks](https://img.shields.io/badge/Notebook-Jupyter-orange)](https://jupyter.org/)

This repository contains two types of recommender systems built using Python and Jupyter Notebooks:  
- A **Knowledge-Based (Content-Based)** Recommender  
- An **Item-Based (Collaborative Filtering)** Recommender

---

##  Table of Contents
- [Overview](#overview)
- [Knowledge-Based Recommender](#knowledge-based-recommender-system)
- [Item-Based Recommender](#item-based-recommender-system)
- [Setup](#setup)
- [Development Utilities](#extracting-imports-from-notebooks)
---

## Overview

Recommender systems are algorithms that suggest relevant items to users based on various strategies such as user preferences, item similarity, or past behavior.  
This project explores two primary approaches:

1. **Knowledge-Based (Content-Based)** – for cold-start or new-user problems.  
2. **Item-Based Collaborative Filtering** – for existing users with sufficient interaction history.

---

## Knowledge-Based Recommender System

This is a **content-based** system suitable for new users.

- **User Popularity Filter:** Recommends movies that were:
  - Watched by **≥ 400 users**
  - Have a **rating ≥ 4.0**
- **Genre-Based Filter:** 
  - Selects the most popular movie per genre (total of 19 genres)
  - Based on highest user count and average rating

---

## Item-Based Recommender System

This is a **collaborative filtering** system based on item similarity.

- Assumes: *"Users who liked similar items in the past will continue to do so."*
- Uses:
  - **User-item rating matrix**
  - **Nearest Neighbors** approach (via `sklearn`)
- Recommends items by identifying similar users or items based on interaction patterns

---

## Setup

To run this project locally:

1. **Clone the repository**
   ```bash
   git clone https://github.com/ShashankMk031/Recommendation-system.git
   cd Recommendation-system
2. **Setup a venv**
   ```bash
   uv venv
   uv pip install -r requirements.txt
3. **Launch Jupyter notebook**
   ```bash
   uv pip install notebook  # if not already installed
   jupyter notebook

## Extracting Imports from Notebooks 
```bash
grep -oP '^(import|from)\s+\K\w+' *.ipynb | sort | uniq
