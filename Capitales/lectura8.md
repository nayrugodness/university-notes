# 1. Mercado de Opciones: El poder de decidir

A diferencia de los forwards o futuros, las **opciones** otorgan un **derecho, no una obligación**.  
Funciona como un seguro: pagas hoy para cubrirte ante escenarios adversos.

## Conceptos fundamentales

- **Prima**  
  Costo del “seguro”.  
  - Se paga por anticipado  
  - No es reembolsable  

- **Strike Price (Precio de ejercicio)**  
  Precio pactado al que puedes comprar o vender.

- **Call (Opción de compra)**  
  - Uso: importadores  
  - Derecho a **comprar divisas** a precio fijo  
  - Se activa si el mercado sube  

- **Put (Opción de venta)**  
  - Uso: exportadores  
  - Derecho a **vender divisas** a precio fijo  
  - Se activa si el mercado baja  

## Escenarios al vencimiento

- **Mercado favorable**
  - No ejerces la opción  
  - Operas en mercado spot  
  - Pérdida: solo la prima  

- **Mercado desfavorable**
  - Ejerces la opción  
  - Ejecutas al strike  
  - Proteges margen / rentabilidad  

---

# 2. Swaps de Divisas: Permuta Financiera

Un **swap** es un acuerdo de intercambio de flujos de dinero en diferentes monedas durante un período.

## Objetivo

- Optimizar costo de financiamiento  
- Convertir exposición cambiaria  
  - Ej: deuda en USD → deuda en COP  

## Funcionamiento

- Intercambio inicial de monedas  
- Pagos periódicos (intereses / capital)  
- Reversión futura bajo condiciones pactadas  

## Diferencia clave vs Forward

- **Forward** → intercambio único al vencimiento  
- **Swap** → múltiples flujos en el tiempo  

---

# 3. Resumen Ejecutivo de Coberturas

| Instrumento | ¿Obligatorio? | Costo Inicial | Uso Principal |
|------------|--------------|--------------|--------------|
| Forward | Sí | $0 | Fijar precio exacto (custom) |
| Futuro | Sí | Garantía | Fijar precio en mercado organizado |
| Opción | No | Prima | Cobertura flexible (downside protegido, upside abierto) |
| Swap | Sí | $0 | Gestión de deuda / flujos a largo plazo |

---

# Takeaway estratégico

- **Opciones** → hedge asimétrico (protección + upside)  
- **Swaps** → gestión estructural de balance  
- **Forwards/Futuros** → cobertura directa de precio  

👉 Traducción ejecutiva:  
- Si priorizas **flexibilidad** → opciones  
- Si priorizas **certeza total** → forwards/futuros  
- Si gestionas **estructura financiera** → swaps  
