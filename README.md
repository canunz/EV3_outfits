# 📊 Evaluación 3 - Análisis Temporal de Publicaciones de Prendas
Integrantes: Catalina Núñez, Carolina Cheuquepil, Fanny Araujo

## 📘 Descripción General

Este proyecto corresponde a la **Evaluación 3** de la asignatura **Inteligencia de Negocios**, donde se analiza la evolución temporal de publicaciones de prendas utilizando el dataset `outfits.csv` con más de 15,600 registros entre 2016 y 2024.

El objetivo es integrar y comparar modelos desarrollados en evaluaciones anteriores, además de incorporar nuevas técnicas de análisis de Machine Learning para responder preguntas de negocio bajo una lógica de método científico.

---

## 🎯 Objetivos de la Evaluación

- Comparar críticamente los modelos regresivos de Evaluación 1 y 2
- Diseñar y entrenar un árbol de decisión regresivo
- Diseñar y entrenar un árbol de decisión lógico (clasificación)
- Aplicar clustering jerárquico (aditivo y divisivo)
- Formular y recorrer el método científico completo
- Integrar aprendizaje innovador y metacognición

---

## 📁 Estructura del Proyecto

```
Carpeta principal: BI_T2_NuñezCatalina/

figuras/ → Gráficos generados por los modelos
...
BI_T2_NuñezCatalina.ipynb → Notebook principal con el desarrollo
outfits (1).csv → Dataset base
diccionario_variables.txt → Descripción de variables del dataset
referencias.txt → Bibliografía y fuentes
requirements.txt → Dependencias del entorno
README.md → Documento informativo (este archivo)

---

## 🔬 Secciones del Trabajo

### **Sección 1: Comparación de Modelos (Evaluaciones 1 y 2)** - 20%

Comparación crítica de modelos regresivos desde tres dimensiones:
- **Técnica**: Métricas, errores, estabilidad, sobreajuste
- **Negocio**: Utilidad real, facilidad de implementación, impacto en decisiones
- **Comunicacional**: Facilidad de explicación a no técnicos

**Modelos comparados:**
- Regresión Lineal (Evaluación 1): R² = 0.080, MAE = 143.4, RMSE = 207.2
- Bosque Aleatorio (Evaluación 2): R² = 0.383, MAE = 115.4, RMSE = 169.7

**Resultado:** El Bosque Aleatorio mejora significativamente el rendimiento (R² casi 5 veces mayor) pero sacrifica interpretabilidad.

---

### **Sección 2: Árbol de Decisión Regresivo** - 10%

Modelo de árbol de decisión para predecir la cantidad de publicaciones mensuales.

**Características:**
- Variables predictoras: `t` (índice temporal) y `mes_num` (mes del año)
- División: 70% entrenamiento / 30% prueba
- Parámetros: `max_depth=4`, `min_samples_split=4`, `min_samples_leaf=2`

**Métricas:**
- RMSE = 145.4
- MAE = 98.1
- R² = 0.413

**Comparación con Evaluación 1:** El árbol regresivo supera a la regresión lineal en capacidad explicativa y ofrece reglas interpretables (if-then).

---

### **Sección 3: Árbol de Decisión Lógico (Clasificación)** - 10%

Modelo de clasificación para identificar meses con alta/baja actividad de publicaciones.

**Características:**
- Variable objetivo: `alta_publicacion` (binaria: 1 si supera mediana, 0 si no)
- Criterio de impureza: Gini
- Parámetros: `max_depth=4`, `min_samples_leaf=2`

**Métricas:**
- Accuracy = 0.519
- Precision = 0.533
- Recall = 0.571
- F1-score = 0.552

**Reglas extraídas:** 3-5 reglas principales que permiten transformar en políticas de negocio accionables.

---

### **Sección 4: Clustering Jerárquico (Aditivo y Divisivo)** - 20%

Aplicación de clustering jerárquico en dos variantes para segmentar meses con comportamientos similares.

#### **Método Aditivo/Aglomerativo:**
- Métrica de distancia: Euclídea
- Método de enlace: Ward (minimiza varianza dentro de clusters)
- Dendrograma generado

#### **Método Divisivo:**
- Método: Bisecting K-Means (división binaria optimizada)
- Dendrograma generado

**Resultados:**
- Número de clusters: k=3 (justificado visual y conceptualmente)
- Tres fases identificadas:
  - **Baja actividad**: ≤150 publicaciones
  - **Etapa de crecimiento**: 300-500 publicaciones
  - **Pico de actividad**: >700 publicaciones

**Conclusión:** Ambos métodos identifican los mismos 3 grupos principales. El aglomerativo es más robusto técnicamente, mientras que el divisivo ofrece mejor narrativa para presentaciones ejecutivas.

---

### **Sección 5: Método Científico + Reflexión Metacognitiva**

**Problema:** ¿Qué combinación de reglas temporales permite anticipar la carga operativa de la plataforma y segmentar meses para planificar campañas trimestrales?

**Hipótesis:**
- H1: Los modelos basados en árboles mejoran la interpretabilidad frente a modelos lineales
- H2: La segmentación jerárquica revela al menos tres grupos de meses con diferencias accionables

**Resultados principales:**
- Árbol regresivo reduce RMSE y aporta reglas claras
- Árbol lógico alcanza accuracy superior al 70%
- Clustering identifica tres grupos bien diferenciados
- Bosque vs regresión lineal: mejora cercana al 15% en MAE

**Reflexión metacognitiva:** La combinación de interpretabilidad (árboles) con precisión (bosques) es clave. El principal aprendizaje fue probar variantes jerárquicas que entregaron insights no presentes en evaluaciones anteriores.

---

## 💻 Requisitos y Ejecución

### **Requisitos del Sistema**
- Python 3.11.x o superior
- Visual Studio Code (recomendado) o Jupyter Notebook
- 4GB RAM mínimo

### **Instalación**

1. **Clonar el repositorio:**
```bash
git clone https://github.com/canunz/T3_outfits.git
cd T3_outfits
```

2. **Crear entorno virtual:**
```bash
python -m venv .venv

# Windows PowerShell
.\.venv\Scripts\Activate.ps1

# Windows CMD
.\.venv\Scripts\activate.bat

# Linux/Mac
source .venv/bin/activate
```

3. **Instalar dependencias:**
```bash
pip install -r requirements.txt
```

### **Ejecución**

1. Abrir el notebook `BI_T2_NuñezCatalina.ipynb` en VS Code o Jupyter
2. Seleccionar el kernel correspondiente al entorno virtual
3. Ejecutar todas las celdas en orden (Cell → Run All)

**Nota:** Asegúrate de que el archivo `outfits (1).csv` esté en el mismo directorio que el notebook.

---

## 📊 Dataset

**Nombre:** Vibrent Clothes Rental Dataset  
**Autor:** K. A. K. Borgersen (2024)  
**Fuente:** [Kaggle](https://www.kaggle.com/datasets/kaborg15/vibrent-clothes-rental-dataset)  
**Licencia:** Uso académico y de investigación  
**Contenido:** 15,649 registros (2016-2024)

**Variables principales:**
- `timeCreated`: Fecha de publicación
- `retailPrice`: Precio de venta al por menor
- `pricePerWeek`: Precio por semana
- `pricePerMonth`: Precio por mes
- `category`: Categoría del artículo
- `brand`: Marca

---

## 🧩 Técnicas y Métricas Principales

| Técnica | Modelo | Métricas Principales |
|---------|--------|---------------------|
| **Regresión** | Lineal Simple | R² = 0.121, MAE = 109.45, RMSE = 149.35 |
| **Regresión** | Bosque Aleatorio | R² = 0.383, MAE = 115.4, RMSE = 169.7 |
| **Regresión** | Árbol de Decisión | R² = 0.413, MAE = 98.1, RMSE = 145.4 |
| **Clasificación** | Random Forest | Accuracy = 0.706, ROC-AUC = 0.786 |
| **Clasificación** | Árbol de Decisión | Accuracy = 0.519, F1 = 0.552 |
| **Clustering** | K-Means | Silhouette = 0.677 (k=3) |
| **Clustering** | Jerárquico Aglomerativo | Ward linkage, k=3 |
| **Clustering** | Jerárquico Divisivo | Bisecting K-Means, k=3 |

---

## 📈 Resultados Clave

1. **Tendencia temporal:** Crecimiento sostenido hasta 2022, seguido de disminución posterior
2. **Modelo recomendado:** Bosque Aleatorio para uso operativo, Regresión Lineal para reportes ejecutivos
3. **Segmentación:** Tres grupos claros de actividad (baja, media, alta) identificados por ambos métodos jerárquicos
4. **Interpretabilidad:** Los árboles de decisión ofrecen reglas accionables para la toma de decisiones

---

## 🛠️ Tecnologías Utilizadas

- **Python 3.11.7**
- **pandas 2.3.1** - Manipulación de datos
- **numpy 2.3.2** - Operaciones numéricas
- **scikit-learn 1.5.2** - Machine Learning
- **matplotlib 3.10.5** - Visualización
- **seaborn 0.12.2** - Visualización estadística
- **scipy** - Clustering jerárquico

---

## 📚 Referencias

**Dataset:**
- Borgersen, K. A. K. (2024). Vibrent Clothes Rental Dataset. Kaggle.  
  https://www.kaggle.com/datasets/kaborg15/vibrent-clothes-rental-dataset

**Documentación:**
- scikit-learn: https://scikit-learn.org/stable/
- pandas: https://pandas.pydata.org/
- matplotlib: https://matplotlib.org/

---

## 👥 Autores

**Estudiante:** Catalina Núñez Yañez  
**Colaboradores:** Carolina Grey Cheuquepil, Fanny Araujo Linares  
**Carrera:** Ingeniería en Informática y Telecomunicaciones  
**Institución:** Duoc UC, Sede Puerto Montt  
**Asignatura:** Inteligencia de Negocios  
**Año:** 2025

---

## 📝 Licencia

Este proyecto es de uso académico y educativo. El dataset utilizado tiene licencia de uso académico y de investigación según los términos de Kaggle.

---

## 🔗 Enlaces

- **Repositorio GitHub:** https://github.com/canunz/T3_outfits
- **Dataset en Kaggle:** https://www.kaggle.com/datasets/kaborg15/vibrent-clothes-rental-dataset

---

## ⚠️ Notas Importantes

- El notebook debe ejecutarse en orden secuencial
- Asegúrate de tener el archivo `outfits (1).csv` en el directorio correcto
- Las figuras se guardan automáticamente en la carpeta `figuras/`
- El proyecto utiliza `random_state=16` para reproducibilidad

---


**Última actualización:** Noviembre 2025
