# 🛠️ PY - Corrección de Objetos tras Cambio de Nombre de Base de Datos

Este proyecto automatiza la **actualización de referencias a una base de datos antigua** dentro de objetos SQL como procedimientos almacenados, vistas y funciones. Es especialmente útil tras la **restauración o migración** de bases de datos en entornos SQL Server, donde los nombres pueden cambiar pero las referencias internas siguen apuntando al nombre anterior.

---

## 🧩 Contexto

En entornos de desarrollo, testing o preproducción es común restaurar una base de datos bajo un nombre diferente al de producción (por ejemplo: `ProduccionDB` → `DesarrolloDB`). Sin embargo, muchos objetos SQL pueden contener referencias explícitas al nombre antiguo, generando errores de ejecución o resultados inconsistentes.

Ejemplo de referencia problemática:

```sql
SELECT * FROM ProduccionDB.dbo.usuarios
