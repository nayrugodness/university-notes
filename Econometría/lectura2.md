# Repaso de los conceptos y propiedades en el modelo clásico de regresión lineal (MCRL)

    Modelar la relación funcional entre dos variables para entender la variable de interés.
    
    Variables:

        Yi: Variable dependiente, respuesta o endógena.
        Xi: Variable independiente, explicativa, covariable o exógena.

    El Modelo (Ecuación):
        Yi = B0 + B1Xi  + ui
                    1

    B0 B1 : Parámetros desconocidos (efectos a estimar)
    ui: Término de error o perturbación.

## Métodos de estimación
    Para hallar los valores de B, los métodos más empleados son:
    
    - MCO (Mínimos cuadrados Ordinarios): Busca minimizar la suma de los cuadrados de los residuos.

    - MV(Máxima Verosimilitud): Busca los valores de los parámetros que maximizan la probabilidad de observar los datos actuales.

    - Supuestos críticos del modelo

    Para que el model de regresión lineal simple sea válido, se asumen las siguientes condiciones sobre el error (ui) y la variable (Yi):

    Media Cero: E(ui) = 0
    Homocedasticidad: La varianza es constante (Var(ui) = sigma a la 2)
    Independencia: Las observaciones no están correlacionadas entre sí (supuesto clave que revisa con cuidado en series de tiempo)

    Normalidad: Yi ~ N($Y_i \sim N(mu, sigma a la 2), donde la media está definida por la recta de regresión (B0 + B1Xi1)

## Aplicación en series de tiempo 

    - Contexto: Se usan estos modelos para identificar la tendencia (dirección a largo plazo) y la estacionalidad (patrones que se repiten).

Nota importante: Aunque la regresión nace para datos de corte transversal, es perfectamente aplicable a series temporales siempre que se ajusten los modelos para capturar la evolución del tiempo.

## Regresión Linear Múltiple

La Regresión Lineal Múltiple es la herramienta estadística para entender cómo un conjunto de variables
independientes ($X$) explican los cambios en una variable dependiente ($Y$).1. 

La Estructura del Modelo se define mediante la ecuación:

    Yi = B0 + B1Xi1 + B2Xi2 + ..... + BpXip + ui

    Yi (Endógena): El resultado que queremos predecir (ej. consumo de mercado).

    B0 (Intercepto): El valor constante cuando todos los predictores son cero.

    Bj (Coeficientes): El peso de cada variable. Indica cuánto cambia Y por cada unidad que aumenta Xj, manteniendo todo lo demás constante (Ceteris Paribus).

    Ui (Error/Perturbación): Lo que el modelo no logra explicar (el "ruido" del sistema).

##  Los 4 "Unit Tests" (Supuestos de Gauss-Markov)

Para que las estimaciones sean confiables (insesgadas y eficientes), los errores (Ui) deben pasar estas pruebas:

    1 Normalidad: Los errores deben distribuirse con una campana de Gauss 
    2 Media Cero : E(Ui) = 0 . En el largo plazo los errores se compensan.
    3 Homocedasticidad: Varianza es constante. El nivel de incertidumbre no debería cambiar según el tamaño de las variables.
    4 Indepencia: Los errores no deben estar correlacionados entre sí (no hay "herencia" de errores de un dato a otro)

## Datos atípicos
      Outliers (Valores Atípicos): Observaciones donde el valor de Y es extremadamente inusual para los valores de X que tiene.

      Puntos de apalancamiento(Leverage): Observaciones con valores de X muy extremos 

## Detractores

    Independencia: Si se rompe, hay Autocorrelación (común en series de tiempo). 
    El modelo se vuelve "mentiroso" sobre su propia precisión.

    Varianza Constante: Si se rompe, hay Heterocedasticidad. 
    El modelo no sabe manejar que la incertidumbre crezca con el tiempo o el volumen.

    Conclusión: Los asumimos para poder usar la fórmula de MCO básica. 
    Si no se cumplen, debemos aplicar "parches" (transformaciones matemáticas o modelos más avanzados).

## ¿Cómo pruebo si mi predicción es acertada o es de la verga?

Diagnóstico de Errores (p-valor > 0.05 es ✅)

Homocedasticidad: Test de Breush-Pagan. (Varianza constante).

Independencia: Test de Durbin-Watson. (Errores no relacionados).

El Modelo con Dummies (Sucursales)
    Ecuación: $Ingresos = 64.3 + 21.2(Tamaño) + 72.0(S2) - 58.9(S3)$
    Si es Sucursal 1: $S2=0, S3=0 \rightarrow Ingresos = 64.3 + 21.2(T)$
    Si es Sucursal 2: $S2=1, S3=0 \rightarrow Ingresos = (64.3 + 72.0) + 21.2(T)$
    
    Interpretación: La Sucursal 2 gana 72 unidades más que la 1 por el simple hecho de ser la Sucursal 2.
    
    Regresión Polinómica e Interpretación
        Objetivo: Mejorar la capacidad predictiva.
        R² (R-Cuadrado): Indica qué porcentaje de la variabilidad explica el modelo. 
        (En el ejemplo, subió de 71% a 86% al usar curvas).
        Parsimonia: Si un modelo grado 3 y uno grado 10 tienen errores
        similares, elige siempre el más simple (grado 3). Menos código, menos problemas.

Pipeline: Datos Sucios → Transformación (log) → Estimación (MCO) → Tests (BP y DW).

MCO en código: Es una función de agregación sobre un array de objetos.

Elasticidad: Es el nombre elegante para la pendiente cuando usas logaritmos.