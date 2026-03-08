# Mini Projekt 2 - Machine Learning (Bilpriser)

Dette projekt analyserer et datasæt over brugte biler i Danmark for at forudsige priser og gruppere bilerne i logiske segmenter ved hjælp af Linear Regression, KMeans Clustering og Random Forest Classification.

## Svar på opgavens spørgsmål

### 1) Hvad bestemmer prisen på en bil?
De mest afgørende faktorer for prisen i vores model er:
* **Kilometer (milage):** Jo mere en bil har kørt, jo lavere bliver prisen.
* **Alder:** Nyere biler er generelt dyrere, outliers her er eksempelvis antikke, unikke eller generelt specielle klassiske biler.
* **Motorstørrelse (ccm2):** En større motor hænger ofte sammen med en højere salgspris. Giver mening på baggrund af at produktionsprisen på kraftige motorer ofte er høj
* **Make and Model:** Bilmærke og modeller har ofte en påvirkning af pris. Eksempelvis hvis vi har en Ferrari med en 4L motor og en Ford 4L motor, så kan man snildt antage at Ferrarien er dyrere. Det samme med, hvis vi har en BMW 330i versus en BMW M3, så ved man at M3'en er deres premium modelklasse med større motor osv, så derfor dyrere.

### 2) Mest populære mærke og model
* **Mærke:** Ford er det mest populære mærke i data med 1.582 opslag.
* **Model:** Ford Fiesta 1.0 EcoBoost Titanium 5d er den mest hyppige enkeltmodel.
* **Teknik:** Den er kendt for sin lille 1.0L turbomotor og gode brændstoføkonomi.

### 3) Tendenser de sidste 5-10 år
Vi ser en klar tendens til, at de fleste biler i data er mellem 0-10 år gamle, som har en top omkring 3-7 år. Der er stor fokus på små, økonomiske biler som Ford Fiesta og Toyota Aygo, hvilket tyder på, at vi danskere prioriterer lave driftsomkostninger.

### 4) Store eller små biler i Danmark?
Data viser tydeligt, at danskere foretrækker små biler. De tre mest populære biler er Ford Fiesta, Toyota Aygo og Ford Focus. Desuden har 86% af bilerne 5 døre, hvilket er typisk for praktiske minibiler.

### 5) Hvor findes de dyre biler?
Der er en klar geografisk forskel på priserne:
* **Region Hovedstaden** har den højeste gennemsnitspris på 158.929 kr.
* **Region Nordjylland** ligger lavest med 135.132 kr.
Dette stemmer godt overens med de generelle indkomstniveauer i Danmark.

### 6) Valg af Machine Learning metoder
* **Task 2 (Regression):** Linear Regression, da vi skal forudsige en talværdi (pris).
* **Task 3 (Clustering):** KMeans til at finde naturlige grupper. Vi valgte k=3 ud fra silhouette-scores.
* **Task 4 (Classification):** Random Forest Classifier, da den er god til at håndtere forskellige datatyper og kategorisere præcist.

### 7) Hvor gode er modellerne?
* **Regression:** Vi har en R² på ca. 0,60, hvilket betyder, at modellen forklarer 60% af prisforskellene. Fejlmarginen (RMSE) ligger på ca. 65.000-70.000 kr..
* **Classification:** Modellen er meget præcis med en **accuracy på 91%**. Den rammer rigtigt på 9 ud af 10 biler, men er lidt svagere på luksusbiler, da vi har færre af dem i vores data.

### 8) Forbedringer af modellerne
For at gøre modellerne endnu bedre kunne man:
* Tilføje bilmærke og modelnavn som faste inputs til regressionen.
* Skaffe mere data på luksusbiler for at træne klassifikationen bedre. (Eksempelvis de nævnte sammenligninger i 1'eren).
* Optimere modellernes parametre (Hyperparameter tuning).

### 9) Udfordringer i projektet
* **Data-cleaning:** Der manglede værdier i `mpg` og `ccm2`, som vi udfyldte med medianen.
* **Fejl i data:** Nogle biler havde negativ alder (Vi antager det er biler der ikke er kommet på markedet endnu), som vi måtte fjerne for ikke at snyde modellen.
* **Encoding:** Vi skulle manuelt rense "doors" kolonnen for "d" og lave det til tal.

---
