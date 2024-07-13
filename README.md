# NLP-Project 2: Sentiment Analysis and Modeling for Amazon Reviews to Increase Sales (Kozmos Dataset)

## Projektübersicht
Kozmos ist ein Unternehmen, das Heimtextilien und Alltagskleidung herstellt und über Amazon verkauft. Um die Kundenzufriedenheit zu verbessern und die Verkaufszahlen zu steigern, wurde ein Sentiment-Analyse-Projekt durchgeführt. Das Ziel war es, Kundenbewertungen zu analysieren, Produktmerkmale auf Basis von Feedback zu verbessern und die Kundenbindung zu stärken.

## Datensatz
Der Datensatz enthält Bewertungen zu einer bestimmten Produktgruppe, einschließlich der eigentlichen Bewertung, des Titels der Bewertung, der Anzahl der Sterne und der Anzahl der Nutzer, die die Bewertung als hilfreich markiert haben.

- **Review:** Bewertung des Produkts

- **Title:** Titel oder Zusammenfassung der Bewertung

- **Helpful:** Anzahl der Personen, die die Bewertung als hilfreich empfunden haben

- **Star:** Anzahl der Sterne, die das Produkt erhalten hat

## Schritte für die Sentiment-Analyse
### 1. Vorverarbeitung:
  
- Eine benutzerdefinierte Funktion text_preprocessing wurde entwickelt, um die Bewertungstexte vorzubereiten. Dies umfasste die Umwandlung von Text in Kleinbuchstaben, das Entfernen von Satzzeichen, Zahlen, Stoppwörtern und seltenen Wörtern sowie die Lemmatisierung.


### 2. Textvisualisierung:

- Implementierung einer Funktion tf_visual, um ein Balkendiagramm der häufigsten Wörter in den vorverarbeiteten Bewertungen zu erstellen.
  
- Generierung einer Wordcloud mit der Funktion word_cloud, um die am häufigsten verwendeten Wörter grafisch darzustellen.

  
### 3. Sentiment-Analyse:

- Verwendung des SentimentIntensityAnalyzer aus NLTK zur Berechnung der Sentiment-Polarität für jede Bewertung.
  
- Kategorisierung jeder Bewertung als positiv oder negativ basierend auf den Compound-Scores und Hinzufügen einer sentiment_label-Spalte zum DataFrame.

- Umwandlung des ursprünglich unsupervised learning Datasets in ein supervised learning Dataset durch die Erstellung der neuen Variablen df["sentiment_label"].

  
## Maschinelles Lernen
### 1. Datenaufteilung:

- Aufteilung der Daten in Trainings- und Testsets, um sicherzustellen, dass die Modelle auf unabhängigen Daten evaluiert werden.
  
### 2. Merkmalsrepräsentation - TF-IDF-Vektorisierung:

- Umwandlung der Textdaten in df["Review"] mit dem TfidfVectorizer in numerische Formate, damit Maschinenlernmodelle sie verarbeiten können. Der TfidfVectorizer erstellt TF-IDF-Matrizen aus den Textdaten, die die Wichtigkeit von Wörtern in einem Dokument relativ zu ihrer Häufigkeit in der gesamten Textsammlung berücksichtigen.
  
### 3. Modellierung - Logistische Regression:

- Training eines Logistischen Regressionsmodells auf den TF-IDF transformierten Daten zur Klassifikation der Sentiments (positiv oder negativ) der Bewertungen.

### 4. Modellbewertung:

- Bewertung der Modellleistung anhand von Metriken wie Genauigkeit, Präzision, Recall und F1-Score. Die Kreuzvalidierung wurde verwendet, um eine robuste Leistung über verschiedene Datensätze sicherzustellen.

### 5. Alternatives Modell - Random Forest:

- Untersuchung der Anwendung eines Random Forest Klassifikators für die Sentiment-Klassifikation unter Verwendung sowohl von Count-Vektorisierung als auch von TF-IDF-Vektorisierung. Kreuzvalidierungs-Scores wurden berechnet, um die Leistung zu bewerten.

### 6. Hyperparameter-Optimierung:

- Einsatz von GridSearchCV zur Optimierung der Hyperparameter für das Random Forest Modell, um die Vorhersagegenauigkeit zu verbessern.

## Ergebnisse und Bewertung
Die Modelle zeigen eine robuste Leistung bei der Klassifizierung der Sentiments von Kundenbewertungen, was Kozmos wertvolle Einblicke zur Verbesserung der Produktqualität und Kundenzufriedenheit liefert. Es ist wichtig anzumerken, dass das Datenset unausgeglichen ist, was die Interpretation der Metriken wie Precision (Genauigkeit), Recall (Rückruf) und F1-Score beeinflussen kann. Detaillierte Analysen der Ergebnisse einschließlich Visualisierungen und Modellbewertungen sind in den zugehörigen Code-Dateien und visuellen Ausgaben zu finden.
