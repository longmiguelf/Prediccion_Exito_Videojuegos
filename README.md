# Predicción del Éxito de Videojuegos mediante ML y NLP

Este repositorio contiene el desarrollo del Trabajo de Fin de Máster (TFM) para el Máster en Big Data y Ciencia de Datos de la **Universidad Internacional de Valencia (VIU)**.

## 🎮 Descripción del Proyecto
El proyecto aborda la predicción de éxito de videojuegos de **Steam®**, mediante el análisis de reseñas y redes sociales. Con ello,se pretende proporcionar una herramienta de apoyo a la toma de decisiones mediante un modelo de **Machine Learning** capaz de predecir si un título será exitoso basándose en su recepción temprana (primeros 30 días).

## 🛠️ Metodología y Datos
Se ha seguido una metodología inspirada en el estándar **CRISP-DM**:
* **Fuentes de datos:** Metadatos de Steam®, reseñas de usuarios (+32 millones) y métricas de visibilidad en Twitch®.
* **Definición de Éxito:** Todo título que, entre los días 31 y 180 post-lanzamiento, supere las 50 reseñas totales y mantenga un ratio de valoraciones positivas superior al 80%.
* **Ingeniería de Características:** * Uso de **NLP (VADER)** para cuantificar el sentimiento de las reseñas.
    * Creación de la variable *bug_mention_ratio* para detectar fallos técnicos reportados por usuarios.
    * Integración de métricas de redes sociales (aparición en el Top 200 de Twitch®).

## 🚀 Modelado y Resultados
Se evaluaron algoritmos de ensamblaje, siendo **XGBoost** el que ofreció el mejor rendimiento global.

| Métrica | Resultado |
| :--- | :--- |
| **ROC-AUC** | 0,8552 |
| **Precision-Recall AUC** | 0,7360 |
| **Sensibilidad (Recall)** | 75% |

**Conclusión principal:** El primer mes de vida de un juego define su futuro. Las variables de recepción temprana (volumen de reseñas y sentimiento inicial) son los predictores más críticos para la sostenibilidad a largo plazo.

## 📦 Requisitos
Para replicar el entorno de este proyecto, es necesario contar con Python 3.x y las siguientes librerías:
* `xgboost`
* `scikit-learn`
* `pandas`
* `nltk`
* `vaderSentiment`
* `sentence-transformers`

## 📂 Estructura del Dataset Maestro
El modelo final utiliza un conjunto de 11,371 videojuegos con 71 variables predictoras, incluyendo:
* **Metadatos:** Precio, género, etiquetas (tags), idiomas.
* **NLP:** Puntuación de sentimiento media y desviación, longitud de reseñas, ratio de quejas técnicas.
* **Social:** Indicador binario de tracción en Twitch®.

---
**Autor:** Miguel Alexander Long Ferreira  
