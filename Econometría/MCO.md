# Mínimos cuadrados Ordinarios

    Imagina que tienes una nube de puntos en un plano 
    (tus datos históricos). Quieres trazar una única línea 
    recta que pase lo más cerca posible de todos esos puntos a la vez.

    El "Para qué": Sirve para crear una regla de predicción. 
        Si la línea dice que por cada año de experiencia ($X$) el salario ($Y$) sube 500 USD, 
        esa "regla" es tu modelo.Cómo funciona (La lógica): La fórmula de MCO calcula la distancia
        vertical entre cada punto real y la línea que intentas dibujar. 
        Como algunas distancias son positivas (puntos arriba) y otras negativas 
        (puntos abajo), se elevan al cuadrado para que todas sean positivas y luego se suman.

    El objetivo: El algoritmo busca los valores de $\beta_0$ y $\beta_1$ que 
    hagan que esa suma sea lo más pequeña (mínima) posible.
    
    En resumen: MCO es un optimizador que busca la "recta del menor error".

    Ejemplo con código:

    import { linearRegression } from 'simple-statistics';

    // Datos: [x, y] -> [Experiencia, Salario]
    const data = [[1, 2000], [2, 2500], [3, 2800]];
    const line = linearRegression(data);

    console.log(line.m); // Esto es tu Beta 1 (Pendiente)
    console.log(line.b); // Esto es tu Beta 0 (Intercepto)