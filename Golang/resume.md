# Go Backend — Puntos Clave que Debo Recordar

## 1. Filosofía de Go
Go prioriza:

- simplicidad
- claridad
- rendimiento
- control explícito

Evita sistemas complejos como:

- ORMs pesados
- magia en runtime
- metaprogramación excesiva

La idea central es **"simple, explícito y predecible"**.

---

# 2. sqlc

Herramienta que **genera código Go a partir de SQL**.

Flujo:

SQL escrito por el desarrollador → sqlc → código Go tipado.

Ejemplo:

```sql
SELECT * FROM users WHERE id = $1;

Principios clave

SQL real (no query builders)
genera algo como 
func (q *Queries) GetUser(ctx context.Context, id int64) (User, error) ` ``` `


    tipos seguros en compilación
    evita errores en runtime
    alto rendimiento

Por qué se usa en Go

    control total sobre queries
    rendimiento de SQL directo
    seguridad de tipos
    evita ORMs complejos

