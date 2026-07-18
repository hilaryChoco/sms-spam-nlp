# Détection de SMS Spam — NLP

Projet de classification de texte pour détecter les SMS spam
en utilisant le traitement du langage naturel (NLP) et le Machine Learning.

## Résultats

| Métrique | Ham | Spam |
|---|---|---|
| Accuracy globale | 98% | — |
| Precision | 97% | 100% |
| Recall | 100% | 83% |
| F1-score | 99% | 91% |

## Stack technique

- **Python 3.11**
- **pandas** — manipulation des données
- **nltk** — nettoyage du texte (stopwords)
- **scikit-learn** — TF-IDF, Naive Bayes
- **matplotlib** — visualisations
- **joblib** — sauvegarde du modèle

## Structure du projet
sms-spam-nlp/
│
├── spam.csv                    # Dataset (Kaggle - UCI SMS Spam Collection)
├── sms_spam.ipynb              # Notebook principal
├── naive_bayes_spam.pkl        # Modèle sauvegardé
├── tfidf_vectorizer.pkl        # Vectoriseur TF-IDF sauvegardé
└── README.md                   # Ce fichier

## Étapes du projet

1. **Chargement et nettoyage** — suppression des colonnes inutiles
2. **EDA** — distribution spam/ham, longueur des messages
3. **Nettoyage du texte** — minuscules, ponctuation, stopwords
4. **Vectorisation TF-IDF** — transformation du texte en chiffres
5. **Modélisation** — Naive Bayes MultinomialNB
6. **Évaluation** — accuracy, precision, recall, F1-score
7. **Visualisation** — top 10 mots spam vs ham
8. **Tests** — prédictions sur des SMS personnalisés

## Points clés

- Dataset déséquilibré : 87% ham vs 13% spam → le **recall spam (83%)** est la métrique la plus importante
- Mots les plus caractéristiques du spam : `call`, `free`, `txt`, `mobile`, `claim`
- Limite identifiée : le modèle hésite sur les spams de type phishing (`URGENT: Your account has been compromised`) car ce vocabulaire est rare dans le dataset d'entraînement

## Lancer le projet

```bash
# Cloner le repo
git clone https://github.com/hilaryChoco/sms-spam-nlp.git
cd sms-spam-nlp

# Créer l'environnement
conda create -n ml-pratique python=3.11
conda activate ml-pratique
pip install numpy pandas scikit-learn matplotlib seaborn nltk jupyterlab joblib

# Lancer le notebook
jupyter lab
```
