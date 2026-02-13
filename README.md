# 🧬 Ensemble Algorithms: Random Forest, AdaBoost & XGBoost
### Detección de Cáncer de Mama - Análisis Comparativo con Desbalanceo de Clases

[![📄 Documentación Completa](https://img.shields.io/badge/Documentación-GitHub%20Pages-2ea44f?style=for-the-badge)](https://alej2andro.github.io/Random-Forest-Adaboost-XGboost-comparison/)
[![📊 Blog RPubs](https://img.shields.io/badge/Blog-RPubs-ff6600?style=for-the-badge&logo=r)](https://rpubs.com/Alej5ndro)

---

## 🎯 Sobre Este Proyecto

Análisis matemático riguroso de tres algoritmos de ensamble aplicados al dataset **Wisconsin Breast Cancer**, explorando cómo diferentes técnicas manejan desbalanceo de clases y optimizan el trade-off crítico entre sensitivity y specificity en diagnóstico clínico.

**Motivación**: Como autodidacta apasionado por las matemáticas, la ciencia de datos y el machine learning, este proyecto profundiza en los fundamentos teóricos y aplicaciones prácticas de algoritmos de ensamble, demostrando cómo la teoría estadística se traduce en soluciones reales de IA.

## 📐 Fundamentos Matemáticos Implementados

### Random Forest (Bagging)
- Reducción de varianza mediante bootstrap aggregation
- Decorrelación de árboles con selección aleatoria de features ($m = \lfloor\sqrt{p}\rfloor$)
- Ecuación de varianza: $\text{Var}(\hat{f}_{rf}) = \rho\sigma^2 + \frac{1-\rho}{B}\sigma^2$

### AdaBoost (Boosting Adaptativo)
- Minimización de pérdida exponencial: $L(y, f(x)) = \exp(-yf(x))$
- Pesos adaptativos: $\alpha_m = \log\left(\frac{1 - \text{err}_m}{\text{err}_m}\right)$
- Corrección secuencial de errores mediante reasignación de pesos

### XGBoost (Gradient Boosting con Regularización)
- Aproximación de Taylor de segundo orden (gradiente + Hessiano)
- Regularización explícita: $\Omega(f) = \gamma T + \frac{1}{2}\lambda\sum_{j=1}^T w_j^2$
- Optimización de ganancia por split con penalización de complejidad

## 📊 Resultados & Métricas

| Algoritmo | Accuracy | Sensitivity | F1-Score | AUC-ROC | Generalización |
|-----------|----------|-------------|----------|---------|----------------|
| **Random Forest** | 0.9569 | 0.9444 | 0.9379 | 0.9919 | ⭐ **Mejor** (-0.010) |
| **AdaBoost** | 0.9569 | 0.9583 | 0.9388 | 0.9901 | Buena (-0.016) |
| **XGBoost** | **0.9665** | **0.9861** | **0.9530** | **0.9934** | Moderada (-0.030) |

### 🔍 Hallazgos Clave

**XGBoost** → Mejor rendimiento en test (98.6% sensitivity, solo 1 FN)  
**Random Forest** → Superior generalización en datos nuevos (F1=0.984)  
**AdaBoost** → Máxima detección en screening (99.5% sensitivity)

### 💡 Insights de Machine Learning

1. **Trade-off Optimización vs Generalización**: XGBoost maximiza métricas en test pero Random Forest mantiene estabilidad en producción
2. **Manejo de Desbalanceo**: Class weights (RF/XGBoost) y pesos adaptativos (AdaBoost) logran sensitivity >94% sin sacrificar specificity
3. **Importancia de Features**: Consistencia cross-algoritmo en variables nucleares (Bare.nuclei, Cell.shape) valida relevancia clínica

## 🛠️ Stack Técnico

**Lenguaje**: R 4.x  
**ML Frameworks**: `randomForest`, `adabag`, `xgboost`  
**Evaluación**: `caret`, `pROC`, `PRROC`  
**Visualización**: `ggplot2` (curvas ROC, matrices de confusión, fronteras de decisión)  
**Documentación**: Quarto + GitHub Pages

## 🚀 Reproducibilidad
```r
# Instalar dependencias
install.packages(c("mlbench", "randomForest", "xgboost", "caret", 
                   "pROC", "PRROC", "ggplot2", "adabag", "reshape2"))

# Renderizar análisis
quarto::quarto_render("Randomforest_adaboost_xgboost.qmd")
```

## 📚 Fundamentos Teóricos Aplicados

- **Teoría de Ensambles**: Sesgo-Varianza, Decorrelación de Predictores
- **Optimización Numérica**: Descenso de Gradiente, Aproximación de Taylor
- **Teoría de la Información**: Impureza de Gini, Ganancia de Información
- **Estadística Bayesiana**: Pesos posteriores en clasificadores secuenciales

## 🎓 Contexto de Aprendizaje

Este proyecto representa mi camino autodidacta en **ciencia de datos, machine learning e inteligencia artificial**, donde las matemáticas son el lenguaje fundamental para entender algoritmos más allá de librerías black-box. Cada línea de código refleja comprensión teórica traducida a implementación práctica.

**Áreas de Especialización**:
- Fundamentos matemáticos de ML (álgebra lineal, cálculo, probabilidad)
- Algoritmos de ensamble y optimización
- Evaluación de modelos en contextos de alta criticidad (medicina, finanzas)
- Visualización de decisiones algorítmicas

## 📖 Referencias

- Breiman, L. (2001). *Random Forests*. Machine Learning, 45(1), 5-32
- Freund & Schapire (1997). *A Decision-Theoretic Generalization of On-Line Learning*
- Chen & Guestrin (2016). *XGBoost: A Scalable Tree Boosting System*
- Hastie et al. (2009). *The Elements of Statistical Learning*

---

## 👨‍💻 Autor

**Alejandro Figueroa Rojas**  
*Apasionado autodidacta en Matemáticas, Ciencia de Datos, Machine Learning e IA*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alejandrofigueroarojas)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:alejandro.figueroa.rojas@gmail.com)
[![RPubs](https://img.shields.io/badge/RPubs-75AADB?style=flat&logo=r&logoColor=white)](https://rpubs.com/Alej5ndro)

---

⭐ **Si este proyecto te resulta útil o inspira tu aprendizaje en ML/IA, considera darle una estrella**
