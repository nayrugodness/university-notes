# 📉 CreditMetrics: Modelación de Riesgo de Crédito

## 1. El Concepto: Del "Default" a la "Migración"

A diferencia de los modelos tradicionales (Default vs. No Default), CreditMetrics se enfoca en **migraciones de calidad crediticia**.

- Un cambio de calificación (ej: AA → BBB) implica una **caída en el valor de mercado** del crédito, incluso sin incumplimiento.
- El modelo calcula el valor del portafolio bajo **todos los escenarios posibles de calificación**.

---

## 2. Los Tres Pilares de Entrada (Inputs)

### Matriz de Transición

- Tabla de probabilidades de cambio de rating  
- Ejemplo:  
  - 80% probabilidad de permanecer en A  
  - 2% probabilidad de caer a B  

### Curvas de Rendimiento (Yield Curves)

- Permiten descontar flujos de caja futuros  
- Ajustadas según el nivel de riesgo del deudor  

### Tasas de Recuperación (LGD - Loss Given Default)

- Porcentaje recuperado en caso de quiebra  
- Input clave para estimación de pérdidas  

---

## 3. Proceso de Cálculo

### Paso A: Evaluación Inicial

- Identificación de la calificación actual de cada crédito  

### Paso B: Proyección de Escenarios

- Valoración del crédito bajo distintos escenarios:  
  - Mejora (AAA)  
  - Deterioro (CCC)  
  - Default  

### Paso C: Correlación de Activos

- Modelación de dependencia entre deudores  
- Ejemplo: deterioro macroeconómico impacta múltiples créditos simultáneamente  

---

## 4. Resultado: Credit Value at Risk (VaR)

El modelo genera una **distribución de pérdidas y ganancias**.

- Métrica clave: **Credit VaR**  
- Interpretación:  
  - *"Con un 99% de confianza, la pérdida no superará $X en un horizonte de 1 año"*  

---

## 💻 Aplicación Profesional

### Desde Ingeniería

- Implementación de motores de cálculo  
- Manejo eficiente de matrices de transición y correlaciones  
- Integración con servicios de tasas en tiempo real  

### Desde Economía

- Validación de supuestos del modelo  
- Ajuste de matrices según ciclo económico  
- Análisis de sensibilidad del portafolio  

---

## ⚖️ Diferenciación vs Otros Modelos

- Modelos tradicionales: enfoque en **pérdida esperada (determinista)**  
- CreditMetrics: enfoque en **valoración de mercado (estocástico)**  

👉 No solo mide pérdidas por default, sino la **desvalorización del activo** ante cambios en el riesgo crediticio  