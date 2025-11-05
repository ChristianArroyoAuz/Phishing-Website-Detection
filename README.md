# Phishing Website Detection

## Descripción del Proyecto
Este proyecto implementa un sistema de detección de sitios web de phishing utilizando técnicas de machine learning y análisis de características de URLs. El modelo clasifica URLs como legítimas o maliciosas basándose en patrones específicos.

## 🎯 Características Extraídas

| Característica | Descripción | Clasificación |
|----------------|-------------|---------------|
| **Longitud de URL** | Analiza el tamaño de la URL | <54 chars: Legítimo<br>54-75 chars: Sospechoso<br>>75 chars: Phishing |
| **Símbolo @** | Detecta presencia de "@" en la URL | Con @: Phishing<br>Sin @: Legítimo |
| **Redirección "//"** | Identifica redirecciones después del protocolo | Con "//": Phishing<br>Sin "//": Legítimo |
| **Guiones en dominio** | Detecta uso de guiones en nombre de dominio | Con "-": Phishing<br>Sin "-": Legítimo |
| **Subdominios** | Analiza número de subdominios | <3: Legítimo<br>3: Sospechoso<br>>3: Phishing |

## 🛠 Tecnologías Utilizadas

- **Python 3.11.7**
- **Pandas** - Procesamiento de datos
- **Scikit-learn** - Machine Learning
- **Random Forest** - Algoritmo de clasificación
- **Jupyter Notebook** - Entorno de desarrollo

## 📊 Metodología

1. **Preprocesamiento**
   - División de URLs en componentes (protocolo, dominio, dirección)
   - Limpieza y normalización de datos

2. **Extracción de Características**
   - Aplicación de reglas heurísticas
   - Transformación de características categóricas

3. **Modelado**
   - Entrenamiento con Random Forest (100 estimadores)
   - Validación cruzada
   - Optimización de hiperparámetros

4. **Evaluación**
   - Matriz de confusión
   - Métricas de precisión
   - Análisis de importancia de características

## 📈 Resultados

El modelo demostró alta efectividad en la clasificación con:
- **Alta precisión** en la detección de URLs phishing
- **Matriz de confusión** balanceada
- **Características relevantes** identificadas correctamente

## 📁 Estructura del Proyecto

```
Phishing-Detection/
├── dataset2.csv              # Datos de entrenamiento
├── dataset3.csv              # Datos de prueba
├── Modified Phishing Website Detection.ipynb
└── README.md
```

## 🚀 Uso

El notebook Jupyter incluye el flujo completo:

```python
# Carga de datos
data = pd.read_csv("dataset2.csv")

# Entrenamiento del modelo
clf = RandomForestClassifier(n_estimators=100)
clf.fit(training_features, labels)

# Predicción
predictions = clf.predict(test_features)
```

## 💡 Aplicaciones

- **Protección de usuarios** contra sitios web maliciosos
- **Filtrado automático** de URLs sospechosas
- **Educación en ciberseguridad**
- **Sistemas de detección temprana**

## 🔍 Insights

- Las URLs largas con múltiples subdominios son indicadores fuertes de phishing
- El uso de guiones en el dominio es una táctica común en ataques
- La combinación de múltiples características mejora la detección

---

*Proyecto educativo para aplicaciones de machine learning en ciberseguridad*
