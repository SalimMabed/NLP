# NLP — Chatbot conversationnel BERT × GPT-2

Projet universitaire (Université Mouloud Mammeri de Tizi-Ouzou, 2023) : comparaison de trois approches de classification d'intentions pour un agent conversationnel, et une expérience de dialogue autonome entre deux chatbots — l'un généraliste (GPT-2) qui génère des questions, l'autre spécialisé (BERT) qui y répond.

## Contenu

| Fichier | Description |
|---|---|
| `chatbot_TFIDF.ipynb` | Approche de référence : vectorisation TF-IDF + similarité cosinus. |
| `chatbot_Sequential.ipynb` | Réseau de neurones séquentiel (Keras) entraîné sur un sac de mots. |
| `chatbot_BERT.ipynb` | Fine-tuning de BERT pour la classification d'intentions (PyTorch / Transformers), puis discussion simulée entre deux chatbots : GPT-2 génère des questions, BERT y répond. |
| `intents.json` | Jeu de données d'intentions (patterns de phrases → tag → réponses). |
| `rapport chatbot_nlp.pdf` | Rapport complet : état de l'art, méthodologie, mise en œuvre des trois approches, comparaison, conclusion. |
| `chatbot_model.h5`, `words.pkl`, `classes.pkl` | Modèle entraîné et artefacts du réseau séquentiel. |

## Approche

Les trois notebooks répondent à la même tâche — classifier l'intention d'une phrase à partir de `intents.json` — avec trois méthodes différentes, comparées sur le temps d'exécution, l'interprétabilité, l'usage de ressources et la capacité à généraliser (détail dans le rapport, section *Comparaison des méthodes*).

Le notebook BERT ajoute une démonstration additionnelle, `chat_between_bots()` : deux agents dialoguent tour à tour, l'un s'appuyant sur GPT-2 pour générer une question à partir des patterns du jeu de données, l'autre sur BERT fine-tuné pour classer l'intention et sélectionner une réponse.

## Résultat

Les métriques (accuracy, precision, recall, F-score) sont restées modestes et proches entre les trois méthodes, la taille du jeu de données utilisé étant limitée — un constat assumé dans le rapport plutôt qu'un score mis en avant. L'intérêt du projet est la comparaison méthodologique entre TF-IDF, réseau de neurones et BERT, et la démonstration d'un dialogue autonome entre deux modèles de nature différente (compréhension/classification vs génération).

## Contexte

Réalisé dans le cadre d'un cursus à l'Université Mouloud Mammeri de Tizi-Ouzou, ce projet a servi de base à une présentation DevFest sur le NLP (2023).
