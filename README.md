# reviewsentimentscript
A movie review sentiment script with small LLM generator


# Sentiment Analysis Project

This project performs sentiment analysis on movie reviews by combining **VADER sentiment analysis** and a custom-built **sentiment lexicon**. It also cleanses the input text and visualizes the sentiment distribution for various movies.

---

## Features

1. **Custom Lexicon**: A manually curated sentiment lexicon with support for French language:
   - Handles **lemmatization** and **word variations** (plural and gender forms).
2. **Dynamic Lexicon Expansion**: Automatically identifies unknown words from reviews and classifies them as positive, negative, or neutral using VADER.
3. **Sentiment Analysis**:
   - VADER analysis for overall sentiment scoring.
   - Lexicon-based word count for detailed sentiment classification.
4. **Data Visualization**: Generates bar plots of sentiment distribution for individual movies.

---

## Prerequisites

To run the project, you need the following Python libraries:

- `nltk`
- `transformers`
- `matplotlib`
- `string`
- `re`

Install the necessary packages using:
pip install nltk transformers matplotlib
nltk.download('vader_lexicon')
nltk.download('stopwords')
nltk.download('wordnet')

The dataset should be a JSON file containing movie reviews with the structure:
[
    {"titre": "Movie Title", "avis": "Review text here...", ...},
    {"titre": "Another Movie", "avis": "Another review...", ...}
]

## Code Structure

## Main Functions
lemmatize_words(word_list): Lemmatizes a list of words.
get_females_and_plurals(word): Generates feminine and plural forms for a given word.
lemmatize_and_add_plurals_and_females(word_list): Combines lemmatization with feminine/plural transformations.
clean_avis(avis): Cleanses text by removing stopwords, punctuation, and short words.
determine_sentiment_vader(avis, sentiment_lexicon): Determines the sentiment using VADER and the custom lexicon.
calculate_average_sentiment(data, sentiment_lexicon): Aggregates sentiment scores for each movie.
visualize_sentiments(movie_sentiments): Generates bar charts for sentiment distribution.
Dynamic Lexicon Expansion
The add_unknown_words_to_lexicon(avis, sentiment_lexicon) function automatically updates the lexicon by analyzing new words using VADER.

## Future Improvements
Support for more advanced natural language processing techniques (e.g., BERT embeddings).
Enhanced visualization, including sentiment trends over time.
Interactive web interface for real-time sentiment analysis.


# FRANCAIS

# Projet d'Analyse de Sentiment

Ce projet réalise une analyse de sentiment sur des avis de films en combinant **l'analyse de sentiment VADER** et un **lexique de sentiment personnalisé**. Il comprend également un nettoyage des textes et une visualisation de la répartition des sentiments pour différents films.

---

## Fonctionnalités

1. **Lexique Personnalisé** : Un lexique de sentiment conçu manuellement avec prise en charge de la langue française :
   - Gestion de la **lemmatisation** et des **variations de mots** (formes plurielles et féminines).
2. **Extension Dynamique du Lexique** : Identification automatique des mots inconnus dans les avis, classés comme positifs, négatifs ou neutres grâce à VADER.
3. **Analyse de Sentiment** :
   - Analyse avec VADER pour des scores globaux de sentiment.
   - Comptage basé sur le lexique pour une classification détaillée.
4. **Visualisation des Données** : Génération de graphiques en barres montrant la répartition des sentiments par film.

---

## Prérequis

Pour exécuter le projet, les bibliothèques Python suivantes sont nécessaires :

- `nltk`
- `transformers`
- `matplotlib`
- `string`
- `re`

Installez les dépendances avec la commande suivante :

pip install nltk transformers matplotlib
nltk.download('vader_lexicon')
nltk.download('stopwords')
nltk.download('wordnet')

Le jeu de données doit être un fichier JSON structuré comme suit :
[
    {"titre": "Titre du film", "avis": "Texte de l'avis ici..."},
    {"titre": "Autre film", "avis": "Un autre avis ici..."}
]

## Structure du Code
## Fonctions Principales
lemmatize_words(word_list) : Lemmatisation d'une liste de mots.
get_females_and_plurals(word) : Génération des formes féminines et plurielles d'un mot.
lemmatize_and_add_plurals_and_females(word_list) : Combine la lemmatisation et les transformations féminines/plurielles.
clean_avis(avis) : Nettoie les textes en supprimant les stopwords, la ponctuation et les mots courts.
determine_sentiment_vader(avis, sentiment_lexicon) : Détermine le sentiment à l'aide de VADER et du lexique personnalisé.
calculate_average_sentiment(data, sentiment_lexicon) : Agrège les scores de sentiment pour chaque film.
visualize_sentiments(movie_sentiments) : Génère des graphiques en barres pour la répartition des sentiments.
Extension Dynamique du Lexique
La fonction add_unknown_words_to_lexicon(avis, sentiment_lexicon) met à jour automatiquement le lexique en analysant de nouveaux mots grâce à VADER.

## Améliorations Futures
Prise en charge de techniques avancées de traitement du langage naturel (ex. : embeddings BERT).
Visualisation améliorée, y compris les tendances des sentiments au fil du temps.
Interface web interactive pour une analyse en temps réel.
