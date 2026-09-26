# Credit Scoring y Gestión del Riesgo de Crédito mediante Aprendizaje Sensible a Costes

Desarrollo y evaluación de modelos de clasificación supervisada en `R` orientados a la toma de decisiones en la concesión de préstamos bancarios, abordando el problema de la asimetría de costes entre falsos negativos (conceder crédito a un cliente que entra en *default*) y falsos positivos (rechazar a un cliente solvente).

## 📋 Características del Estudio
* **Dataset y Análisis Exploratorio (EDA):** Estudio de una cartera de **1.000 préstamos** descritos por **21 variables** financieras y demográficas, con una estructura desbalanceada (70% *No-Default* vs. 30% *Default*).
* **Modelización Incremental:**
  1. **Modelo Base (`C5.0`):** Árbol de decisión interpretable evaluado frente al umbral de precisión esperada por azar ($58\%$), identificando el sesgo inicial hacia la clase mayoritaria (*Accuracy* del $67\%$, especificidad del $79,41\%$ pero sensibilidad al *Default* de solo el $40,62\%$).
  2. **Modelos con Boosting:** Incorporación de iteraciones de *Boosting* adaptativo para reducir el error de clasificación en los prestatarios de alto riesgo.
  3. **Aprendizaje Sensible a Costes (*Cost-Sensitive Learning*):** Penalización explícita en la matriz de costes sobre los falsos negativos para proteger el capital de la entidad financiera.
* **Estrategia de Negocio Bancario y Optimización del *Threshold*:** Diseño de guías operativas para alinear el ajuste del modelo y el umbral de probabilidad de corte (*threshold*) según el apetito de riesgo de la entidad (**estrategia comercial agresiva vs. estrategia conservadora de preservación de capital**).
