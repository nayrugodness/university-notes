# 📊 Arquitectura de la Valoración (DCF)

## 1. Fundamentos de la Valoración

La valoración es el proceso de cuantificar:

- Activos  
- Patrimonio  
- Potencial futuro  

### Idea clave:
> **Valor ≠ Precio**
- **Valor**: resultado técnico  
- **Precio**: resultado de negociación  

---

### Metodologías

#### Valor Sustancial
- Fórmula base:
  - Activos - Pasivos  
- Representa:
  - Precio mínimo (piso)  

---

#### Utilidades Descontadas
- Enfoque en:
  - Utilidad neta futura  

---

#### Flujo de Caja Libre Descontado (DCF)
- Estándar actual  
- Evalúa:
  - Capacidad real de generar efectivo  

---

## 2. Método DCF (Flujo operativo)

### A. Flujo de Caja Libre (FCL)

Representa el efectivo disponible después de operar y reinvertir:

:contentReference[oaicite:0]{index=0}

**Notas:**
- No se incluyen intereses  
- La deuda se refleja en la tasa de descuento  

---

### B. Tasa de Descuento (WACC)

Es el costo promedio del capital:

:contentReference[oaicite:1]{index=1}

**Componentes:**

- **Kd**: costo de la deuda  
- **Ke**: costo del equity  
  - Calculado con CAPM  
  - Incluye:
    - Beta (riesgo sectorial)  

---

### C. Valor Terminal (Perpetuidad)

Se usa para capturar el valor más allá del horizonte proyectado:

:contentReference[oaicite:2]{index=2}

**Donde:**

- **g (gradiente)**:
  - Crecimiento a largo plazo  
  - Aproximación:
    - Inflación + crecimiento del PIB  

---

## 3. Relevancia práctica (2026)

### NIIF y Justo Valor de Mercado

- Las NIIF (IFRS):
  - Estandarizan la información financiera  
  - Permiten comparabilidad  
  - Aumentan confianza en modelos de valoración  

**Implicación técnica:**
- Sistemas backend deben garantizar:
  - Integridad de datos  
  - Trazabilidad  
  - Consistencia contable  

---

### Escenarios de Valoración

Para negociación se construyen rangos:

#### Escenario Optimista
- Incluye crecimiento (**g**)  
- Supone expansión con la economía  

---

#### Escenario Moderado
- Sin crecimiento  
- Supone estabilidad operativa  

---

## 🎯 Claves prácticas

- DCF = estándar dominante  
- FCL = métrica central (cash real)  
- WACC = riesgo + costo de capital  
- g = driver crítico de largo plazo  
- Valoración = rango, no punto exacto  