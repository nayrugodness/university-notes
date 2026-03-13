# ¿Qué es un Proceso Estocástico?
    Imagina que tienes una función en tu código, 
    pero no es determinista (como 2 + 2 = 4). 
    
    Es una función que, cada vez que la ejecutas, 
    te devuelve un valor diferente basado en una distribución de probabilidad.

    El **Proceso Estocástico** es la "clase" o el "modelo teórico" (el código que genera los números).

    **La Serie de Tiempo** es el "log" o el "archivo JSON" de los resultados 
    que ya ocurrieron y guardaste en tu base de datos. Es la realización práctica.

    Explicación técnica:

    - Un proceso estocástico es el concepto teórico 
    (un conjunto de variables aleatorias indexadas en el tiempo),
    mientras que la serie de tiempo es la observación real o el
    registro de esos datos (la "realización").

## Tiempos y frecuencias

    - Tiempo Discreto: 
        El índice t pertenece a los enteros (ej. días, meses, años).

    - Tiempo Continuo: El índice t pertenece a un intervalo real 
    (flujo ininterrumpido).
    
    - Importancia de la Frecuencia: Para el análisis estadístico, 
    el intervalo entre observaciones debe ser constante (mensual, 
    trimestral, etc.). Si la frecuencia cambia, el modelo pierde validez.

## Tipos de Estructuras de Datos en Economía

    - Corte Transversal:
        Foco: Diferentes individuos en un único momento (t es fijo).
        Supuesto: Independencia entre observaciones.
        Uso: Censos y caracterización de poblaciones.
        
    - Series de Tiempo:
        Foco: Una variable (o agregados) observada en varios momentos (N es 1 o un promedio).
        Supuesto: Continuidad (el pasado influye en el futuro).
        Uso: Pronósticos de PIB, inflación o métricas de servidores.
    
    - Datos Panel (Mixtos):
        Foco: Los mismos individuos seguidos en el tiempo (N individuos y T periodos).
        Tipos:

            Micro (N > T):
                Muchos individuos, poco tiempo (ej. encuestas a familias).

            Macro (T > N): Pocas unidades, mucho tiempo (ej. PIB de los países de la OCDE).
                Balanceado: Todos tienen datos en todos los periodos.
                Ventaja: Captura la dinámica individual y grupal simultáneamente.

## Análisis Descriptivo y Estrategia de Validación
    Para modelar una serie de tiempo, no basta con graficar; 
    se debe aplicar una estrategia de validación cruzada para 
    asegurar que el modelo sea útil en el futuro:

        - Visualización Inicial: Las observaciones deben ser consecutivas 
        y los puntos se unen con líneas para detectar patrones de corto, 
        mediano y largo plazo (tendencias, ciclos, estacionalidad).

        - División de los Datos:

            Entrenamiento: Datos históricos usados para ajustar los parámetros del modelo.

            Prueba: Segmento de datos conocidos, pero reservados, para medir la capacidad
            predictiva. El modelo "compite" aquí para ver cuál tiene menos error.

            Futuro (Pronóstico): El horizonte de tiempo donde ya no hay registros
            y el modelo debe operar solo.

            Criterio de Selección: El mejor modelo no es necesariamente el que mejor
             explica el pasado (overfitting), sino el que mejor predice el conjunto de prueba.

## Componentes y Estructura de las Series de Tiempo
    - Componentes:
        Tendencia: Movimiento de largo plazo (creciente/decreciente).
        Estacionalidad: Patrón repetitivo en periodos fijos (intraanuales).
        Ciclo: Oscilaciones de largo plazo sin periodo fijo.
        Error (Ruido Blanco): Variaciones erráticas, aleatorias, 
        con media cero y varianza constante.

    - Modelos de Integración:
        Aditivo: Variación constante (paralela a la tendencia). 
        Útil cuando los cambios son absolutos.
        
        Multiplicativo: Variación proporcional (aumenta con la tendencia). 
        Útil cuando los cambios son porcentuales. 
        Requiere Mínimos Cuadrados No Lineales si es mixta.
        
        Estacionariedad: >     * Una serie es estacionaria si su media y varianza 
        son constantes en el tiempo.La mayoría de las series económicas
        (como la inflación) no son estacionarias, lo que obliga a transformarlas 
        (ej. mediante diferencias) antes de modelar.
    
    - Descomposición: Proceso de separar , S y E para entender qué parte
     del dato es patrón y qué parte es azar. En R, se usan filtros como LOESS para este fin.

### Ejemplos
    Los 4 Componentes (La "Anatomía" de la Serie)
    
        Tendencia ($T_t$): El movimiento de fondo.
            Tech: El crecimiento de usuarios en tu base de datos a largo plazo.Hogar:
            El aumento gradual del costo de vida (inflación) en tus recibos.
        Estacionalidad (S y t): Lo que se repite cada año.
            Tech: Tu API recibe más tráfico de lunes a viernes (8 AM - 5 PM) que los fines de semana.
            Hogar: El gasto en regalos en diciembre o uniformes en enero.
        
        Ciclo (C_t): Ondas de largo plazo, pero impredecibles (no tienen fecha fija).
            Econ: Un ciclo económico de recesión (puede durar 2 años o 5).
            Error o Ruido Blanco ($\epsilon_t$): Lo aleatorio, lo que no puedes controlar
            Tech: Un pico de tráfico porque un influencer mencionó tu proyecto hoy por azar.

## ¿Cómo?
Estructura: ¿Sumamos o Multiplicamos?
    Esta parte es vital para programar el modelo
    :Aditiva ($Y = T + S + E$): Los picos de estacionalidad siempre miden lo mismo 
    (ej. cada diciembre gastas exactamente $200.000 más). 
    Las líneas de máximos y mínimos son paralelas.
    
    Multiplicativa ($Y = T * S * E$): Los picos crecen a medida que la tendencia sube. 
    Entre más ganas, más gastas en vacaciones. Las líneas se abren como un abanico.