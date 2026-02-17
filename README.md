# Stress Level Prediction: A Data Quality & Feature Engineering Study

## Project Overzicht

Dit project onderzoekt de relatie tussen digitale gewoonten (schermtijd, app-gebruik), levensstijl (slaap, cafeïne-inname) en het gerapporteerde stressniveau van gebruikers. Ondanks een rigoureuze data science-workflow, bleek de dataset een "nulkruising" te bevatten, wat leidde tot een diepgaande analyse van datakwaliteit en modelvalidatie.

## Gebruikte Technieken

* **Feature Engineering:** Ontwikkeling van complexe interactie-features zoals:
* *Jitter Factor*: Interactie tussen cafeïne en app-switching intensiteit.
* *Recovery Deficit*: De balans tussen totale schermtijd en hersteltijd (slaap).
* *Digital Silo*: Ratio tussen social media gebruik en werkproductiviteit.


* **Model Arena:** Vergelijking van verschillende algoritmes (**XGBoost**, **Random Forest**, **SVM**, en **Logistic Regression**).
* **Hyperparameter Tuning:** Geoptimaliseerd met `RandomizedSearchCV` (o.a. `max_depth`, `learning_rate` en `gamma`).
* **Classificatie Strategieën:** Geëxperimenteerd met 10-level regressie, 3-level categorisering (Low, Medium, High) en binaire classificatie.

## Resultaten & Analyse

Na uitgebreide tuning en feature engineering bleven de resultaten steken op:

* **3-Class Accuracy:** ~39% (vs. 33% toeval).
* **Binary Accuracy (High vs. Low):** ~50% (vs. 50% toeval).

### Conclusie: "The Signal vs. Noise Challenge"

De resultaten tonen aan dat de features in deze specifieke Kaggle-dataset (waarschijnlijk synthetisch van aard) geen statistisch significante correlatie vertonen met de target-variabele `Stress_Level`.

**Mijn belangrijkste conclusies:**

1. **Data over Algoritme:** Zelfs de meest geavanceerde modellen (XGBoost) kunnen geen patroon vinden in data waar geen 'signaal' aanwezig is.
2. **Kritische Validatie:** Het gebruik van een *Confusion Matrix* was essentieel om te ontdekken dat het model neigde naar het gemiddelde (bias), wat duidt op een gebrek aan onderscheidend vermogen in de data.
3. **Winst in Proces:** Hoewel de voorspellende waarde laag was, heeft het project geresulteerd in een robuuste pipeline voor feature engineering en model-evaluatie die direct toepasbaar is op real-world (biometrische) datasets.
