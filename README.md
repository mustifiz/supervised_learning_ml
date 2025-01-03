# Hauspreisprognose - README

Dieses Projekt zielt darauf ab, ein Modell zur Vorhersage von Hauspreisen zu entwickeln. Es umfasst Schritte wie **EDA (Exploratory Data Analysis)**, Datenvorverarbeitung, Modellentwicklung und -bewertung. Überwachtes Lernen (**Supervised Learning**) wird genutzt, um ein präzises Prognosemodell zu erstellen.

---

## Projektphasen

### 1. Datenexploration (EDA - Exploratory Data Analysis)
Während der EDA werden folgende Analysen durchgeführt:
- Allgemeine Struktur der Daten überprüfen.
- Fehlende Werte analysieren und behandeln.
- Verteilung von numerischen und kategorialen Merkmalen analysieren.
- Korrelationsanalyse und Feature-Auswahl.

### 2. Datenvorverarbeitung
- Fehlende Werte auffüllen (z. B. mit Mittelwert, Median oder "None").
- Kodierung von kategorialen Merkmalen (Label Encoding, One-Hot Encoding).
- Skalierung der Daten (StandardScaler, MinMaxScaler).

### 3. Feature Engineering
- Neue Features erstellen (z. B. Berechnung von Alter, Zusammenführen von Kategorien).
- Unwichtige oder wenig relevante Features entfernen.

### 4. Modellierung
Die folgenden Algorithmen für überwachtes Lernen können in diesem Projekt verwendet werden:

#### 4.1 Einfache Modelle
- **Lineare Regression (Linear Regression)**:
  Sagt Hauspreise mit einem linearen Modell voraus.
  - Vorteil: Schnell und einfach.
  - Nachteil: Nicht geeignet für nicht-lineare Beziehungen.

- **Ridge- und Lasso-Regression**:
  Ergänzen die lineare Regression mit Regularisierung.
  - Vorteil: Reduziert Overfitting.
  - Nachteil: Begrenzte Fähigkeit, komplexe Beziehungen zu modellieren.

#### 4.2 Baumbasierte Modelle
- **Entscheidungsbaum (Decision Tree)**:
  Teilt die Daten anhand eines Baumdiagramms auf.
  - Vorteil: Modelliert komplexe Beziehungen.
  - Nachteil: Kann zum Overfitting neigen.

- **Random Forest**:
  Kombiniert mehrere Entscheidungsbäume und aggregiert die Ergebnisse.
  - Vorteil: Höhere Genauigkeit, geringere Varianz.
  - Nachteil: Langsamer und ressourcenintensiver.

- **XGBoost, LightGBM, CatBoost**:
  Optimierte Versionen von Gradient Boosting Algorithmen.
  - Vorteil: Hohe Leistung, schnelle Ergebnisse.
  - Nachteil: Komplexe Hyperparameter-Optimierung.

#### 4.3 Andere Modelle
- **Support Vector Regression (SVR)**:
  Trennt Daten mit Ebenen und sagt Werte voraus.
  - Vorteil: Effektiv bei kleinen Datensätzen.
  - Nachteil: Langsam bei großen Datensätzen.

- **K-Nearest Neighbors (KNN)**:
  Sagt Werte basierend auf den nächsten Nachbarn voraus.
  - Vorteil: Einfach und intuitiv.
  - Nachteil: Weniger effizient bei großen Datensätzen.

### 5. Modellbewertung
Verwendete Metriken:
- **MAE (Mean Absolute Error)**: Durchschnittlicher Vorhersagefehler.
- **RMSE (Root Mean Squared Error)**: Quadratwurzel des mittleren quadratischen Fehlers.
- **R² (R-Quadrat)**: Erklärungsgehalt des Modells.

---

## Nutzung
1. Laden Sie die Daten und wenden Sie die Vorverarbeitungsschritte an.
2. Trainieren Sie das Modell mit einem oder mehreren der oben genannten Algorithmen.
3. Bewerten Sie die Leistung und wählen Sie das beste Modell aus.
4. Verwenden Sie den Testdatensatz, um Vorhersagen zu treffen, und speichern Sie die Ergebnisse im Format von `sample_submission.csv`.

---

## Voraussetzungen
- **Python-Bibliotheken**:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - xgboost, lightgbm, catboost (optional)

---

## Beispielbefehle
### Training
```python
from sklearn.ensemble import RandomForestRegressor
model = RandomForestRegressor()
model.fit(X_train, y_train)
