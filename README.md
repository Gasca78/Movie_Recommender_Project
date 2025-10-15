# Sistema de Recomendación de Películas con Python

![Python](https://img.shields.io/badge/Python-3.9-blue.svg)
![Jupyter Notebook](https://img.shields.io/badge/Notebook-Jupyter-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Este proyecto fue desarrollado en equipo como parte del bootcamp Xperience, donde lideré un equipo multicultural (Argentina, Perú, México) durante un mes para su realización.

---

### 📖 Índice

1.  [Resumen del Proyecto](#-resumen-del-proyecto)
2.  [Objetivo de Negocio](#-objetivo-de-negocio)
3.  [Dataset](#-dataset)
4.  [Metodología y Modelos Implementados](#-metodología-y-modelos-implementados)
5.  [Tecnologías Utilizadas](#-tecnologías-utilizadas)
6.  [Cómo Ejecutar el Proyecto](#-cómo-ejecutar-el-proyecto)
7.  [Conclusiones](#-conclusiones)

---

### 🎯 Resumen del Proyecto

Este repositorio contiene el desarrollo de un sistema de recomendación de películas utilizando Python y el ecosistema de Data Science. El objetivo es analizar los datos de la plataforma MovieLens para construir tres tipos de motores de recomendación que mejoren la experiencia del usuario, ofreciendo sugerencias precisas y relevantes.

---

### 💼 Objetivo de Negocio

En la era del streaming, la capacidad de retener usuarios es clave. Un sistema de recomendación efectivo aumenta el *engagement* y la satisfacción del cliente al ayudarle a descubrir contenido nuevo y afín a sus gustos. Este proyecto simula el desafío de una plataforma de streaming para personalizar su oferta de contenido.

---

### 📊 Dataset

Se utilizó el dataset público de **MovieLens (25M)**, que contiene millones de calificaciones de miles de películas por parte de miles de usuarios. Los ficheros principales utilizados son:
* `movies.csv`: Información de las películas (ID, título, géneros).
* `ratings.csv`: Calificaciones de los usuarios a las películas (ID de usuario, ID de película, rating, timestamp).

---

### 🤖 Metodología y Modelos Implementados

Se implementaron tres estrategias de recomendación, desde la más simple a la más compleja:

1.  **Recomendador No Personalizado (Top 10 Global):**
    * **Técnica:** Se utiliza un **promedio Bayesiano** para rankear las películas. Este método balancea la calificación promedio con el número de votos, evitando que películas con pocas pero muy buenas calificaciones aparezcan injustamente en el top.
    * **Resultado:** Ofrece un top 10 de películas populares y aclamadas, ideal para nuevos usuarios.

2.  **Recomendador Basado en Contenido (Content-Based Filtering):**
    * **Técnica:** Se calcula la similitud entre películas basándose en sus géneros. Se vectorizan los géneros utilizando **TF-IDF** y luego se calcula la **similitud de coseno** entre todas las películas.
    * **Resultado:** Dado un film, el sistema recomienda las 10 películas más similares en términos de contenido (género).

3.  **Recomendador con Filtro Colaborativo (Collaborative Filtering):**
    * **Técnica:** "Usuarios a los que les gustó X, también les gustó Y". Se implementa un modelo **K-Nearest Neighbors (KNN)** para encontrar a los usuarios con patrones de calificación más similares a un usuario dado.
    * **Resultado:** Se recomiendan películas que estos "vecinos" o usuarios similares han calificado positivamente y que el usuario objetivo aún no ha visto.

---

### 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3.9
* **Análisis de Datos:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (TfidfVectorizer, linear_kernel, NearestNeighbors)
* **Visualización:** Matplotlib, Seaborn
* **Entorno:** Google Colab / Jupyter Notebook
* **APIs:** Se utilizó la API de TMDB para enriquecer los datos de las películas (pósters, descripciones).

---

### 🚀 Cómo Ejecutar el Proyecto

1.  Clonar el repositorio:
    ```bash
    git clone [https://github.com/Gasca78/Movie_Recommender_Project.git](https://github.com/Gasca78/Movie_Recommender_Project.git)
    ```
2.  Navegar al directorio del proyecto:
    ```bash
    cd Movie_Recommender_Project
    ```
3.  Instalar las dependencias (se recomienda crear un entorno virtual):
    ```bash
    pip install -r requirements.txt
    ```
4.  Abrir y ejecutar el notebook `nombre_del_notebook.ipynb` en Jupyter.

---

### ✅ Conclusiones

Este proyecto permitió aplicar y comparar tres técnicas fundamentales de los sistemas de recomendación. Se demostró cómo, a través del análisis de datos y el machine learning, es posible generar un valor tangible para el negocio al personalizar la experiencia del usuario y fomentar el descubrimiento de contenido.
