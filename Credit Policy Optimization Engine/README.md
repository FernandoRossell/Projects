# Credit Portfolio Risk & Profit Optimization


**Caso de negocio:** From Credit Risk Modeling to Profit-Driven Decision Making

**Stack:** 

**Autor:** Abel Soto

---

## Visión general

En la banca minorista, las decisiones de aprobación de crédito suelen basarse exclusivamente en métricas de riesgo como la probabilidad de default. Sin embargo, esta aproximación ignora un aspecto crítico: **la rentabilidad esperada del portafolio**.

Este proyecto propone un **framework analítico de extremo a extremo** para optimizar decisiones de crédito, balanceando riesgo y retorno económico. El enfoque combina **machine learning, métricas financieras y simulación de políticas**, con el objetivo de maximizar el beneficio esperado bajo restricciones de riesgo.

El caso está diseñado para replicar desafíos reales enfrentados por equipos senior de analytics en instituciones financieras.

---

## Objetivos del proyecto

- Estimar la **Probability of Default (PD)** a nivel cliente utilizando modelos estadísticos y de machine learning, estableciendo un baseline interpretable y modelos no lineales avanzados.
- Calcular métricas financieras clave como:
  - Expected Loss (EL)
  - Expected Profit
- Diseñar y comparar **políticas de aprobación de crédito**:
  - Basadas exclusivamente en riesgo (PD)
  - Basadas en rentabilidad esperada del cliente y del portafolio
- Evaluar el impacto de dichas políticas sobre indicadores clave de negocio:
  - Approval rate
  - Default rate
  - Profit esperado del portafolio
- Implementar y evaluar **modelos de mayor complejidad** (por ejemplo, Support Vector Machines y Redes Neuronales) como modelos *challenger*, comparándolos contra enfoques tradicionales en términos de:
  - Performance predictiva
  - Calibración de probabilidades
  - Estabilidad temporal
  - Explicabilidad y gobernanza
- Justificar la **selección final del modelo** priorizando soluciones más simples y robustas cuando estas ofrecen un mejor balance entre desempeño, interpretabilidad y viabilidad operativa.
- Simular escenarios adversos y realizar stress testing para analizar la **robustez del sistema de decisión crediticia** bajo cambios macroeconómicos.
- Traducir resultados técnicos en **insights accionables para toma de decisiones ejecutivas**, enfocados en impacto económico y control de riesgo.

---

## Fuente de los datos

### Dataset principal

El proyecto utiliza el **Home Credit Default Risk Dataset**, un dataset público ampliamente usado para problemas de credit scoring.

- **Proveedor:** Home Credit Group  
- **Plataforma:** Kaggle  
- **Tipo de problema:** Clasificación binaria (default / no default)

El dataset incluye información como:
- Datos demográficos
- Ingresos
- Historial crediticio
- Comportamiento financiero

### Variables adicionales (sintéticas)

Para habilitar el análisis económico, se generan variables adicionales bajo supuestos realistas:

- Monto del crédito
- Tasa de interés
- Plazo del préstamo
- Loss Given Default (LGD)

> Estas variables sintéticas están documentadas y se utilizan exclusivamente para simular un entorno de decisión financiera realista.

### Datasets description (From kaggle)

 - **application_train.csv** 
 
 This is the main training dataset, containing demographic, financial, and credit data for loan applicants. It includes information such as income, loan details, payment history, and other financial indicators.

 - **bureau.csv** 
 
 This dataset contains credit history data sourced from external financial institutions. It provides historical credit data about customers, their loan applications, and repayment behaviors.

 - **bureau_balance.csv** 
 
 This file contains time-series information on credit balances for applicants based on bureau credit records. It tracks balances across time and provides insights into credit behavior patterns.

 - **credit_card_balance.csv** 
 
 This dataset contains credit card account balances for applicants. It includes details about spending, payment history, and credit utilization rates.

 - **installment_payments.csv** 
 
 Contains detailed installment payment information for previous loans. This dataset provides insights into payment patterns, delays, and repayment schedules.

 - **previous_application.csv** 
 
 This file provides historical data related to applicants' previous loan applications. It includes loan amounts, application status, payment delays, and other loan application attributes.

 - **POSH_CASH_balance.csv** 
 
 This dataset provides insights into the POSH_CASH financial behavior of loan applicants. It includes detailed financial account balances, which are critical for assessing spending habits, savings, and financial stability. This information can be used to evaluate repayment capabilities and risk factors associated with defaults.

 - **sample_submission.csv** 
 
 This is a template file for submission purposes. It contains the required format for submitting predictions to the competition.

 - **column_description.csv** 
 
 This dataset provides detailed explanations for the column names and features in other datasets. It serves as a reference for understanding variable meanings and data context.

 
---

## Enfoque analítico

### Modelado de riesgo crediticio
- Modelo baseline: Regresión logística
- Modelo principal: Gradient Boosting (XGBoost)
- Métricas de evaluación:
  - ROC-AUC
  - KS statistic
  - Calibration curves
- Interpretabilidad:
  - Feature importance
  - SHAP values

---

### Métricas financieras

Para cada solicitud de crédito se estiman:

- **Expected Loss (EL):**

\[
EL = PD \times LGD \times Exposure
\]

- **Expected Profit:**

\[
Expected\ Profit = Interest\ Income - Expected\ Loss
\]

Estas métricas permiten evaluar decisiones desde una perspectiva económica y no únicamente desde el riesgo.

---

### Políticas de aprobación

Se comparan distintas estrategias de decisión:

- Cut-off fijo por PD
- Cut-off basado en profit esperado
- Políticas segmentadas por perfil de cliente

Cada política es evaluada utilizando indicadores de negocio a nivel portafolio.

---

## Testing & Validación
*(Sección a completar)*

-  
-  
-  

---

## Análisis de Hot Spots del programa
*(Sección a completar)*

-  
-  
-  

---

## Supuestos asumidos
*(Sección a completar)*

-  
-  
-  

---

## ¿Dónde se rompen los supuestos?
*(Sección a completar)*

-  
-  
-  

---

## Posible implementación en producción
*(Sección a completar)*

**Arquitectura propuesta**
-  
-  
-  

**Consideraciones operativas**
-  
-  
-  

---

## Resultados esperados

El enfoque orientado a rentabilidad permite:

- Mejorar el profit esperado del portafolio
- Reducir rechazos innecesarios
- Controlar el riesgo bajo límites definidos
- Habilitar decisiones crediticias más informadas y explicables

> Los resultados finales dependen de los escenarios y parámetros simulados.

---

## Extensiones futuras

- Pricing dinámico basado en riesgo
- Modelado dinámico de EAD
- Análisis de fairness y bias
- Integración de aceptación del cliente (take-up rate)

---

## Conclusión

Este proyecto demuestra cómo un sistema tradicional de credit scoring puede evolucionar hacia un **motor de decisión financiera orientado a valor**, integrando análisis predictivo, métricas económicas y criterio de negocio.

El foco no está en maximizar métricas técnicas, sino en **optimizar decisiones reales con impacto económico**, reflejando el trabajo esperado de perfiles senior en analytics para banca.

---