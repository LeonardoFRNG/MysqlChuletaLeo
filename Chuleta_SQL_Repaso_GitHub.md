# Chuleta SQL (MySQL) -- Repaso rápido

## 1. Orden básico

``` sql
CREATE DATABASE empresa;
USE empresa;
```

## 2. Tipos de datos

  Tipo            Uso
  --------------- -----------------------------------------
  TINYINT         Valores pequeños, estados, IDs pequeños
  SMALLINT        Números medianos
  INT             IDs principales
  BIGINT          Valores muy grandes
  DECIMAL(10,2)   Dinero (nunca FLOAT para dinero)
  FLOAT/DOUBLE    Medidas aproximadas
  CHAR(n)         Longitud fija (ej. sexo, código)
  VARCHAR(n)      Texto variable (nombres, correos)
  TEXT            Textos largos
  DATE            YYYY-MM-DD
  DATETIME        Fecha y hora
  TIME            Hora
  BOOLEAN         TRUE/FALSE (0/1)

## 3. Crear tabla

``` sql
CREATE TABLE clientes(
 id INT AUTO_INCREMENT PRIMARY KEY,
 nombre VARCHAR(100) NOT NULL,
 correo VARCHAR(100) UNIQUE,
 edad TINYINT,
 fecha_registro DATE
);
```

## 4. Restricciones

-   PRIMARY KEY: identifica registros.
-   FOREIGN KEY: relaciona tablas.
-   NOT NULL: obligatorio.
-   UNIQUE: no se repite.
-   DEFAULT: valor por defecto.
-   AUTO_INCREMENT: aumenta solo.
-   CHECK: validar datos (según versión).

## 5. CRUD

``` sql
INSERT INTO tabla(col1,col2) VALUES(...);

SELECT * FROM tabla;

UPDATE tabla
SET campo='nuevo'
WHERE id=1;

DELETE FROM tabla
WHERE id=1;
```

**Nunca olvides el WHERE** en UPDATE y DELETE.

## 6. ALTER TABLE

``` sql
ALTER TABLE clientes ADD telefono VARCHAR(20);
ALTER TABLE clientes MODIFY telefono VARCHAR(30);
ALTER TABLE clientes CHANGE telefono celular VARCHAR(30);
ALTER TABLE clientes DROP COLUMN celular;
ALTER TABLE clientes RENAME TO personas;
```

## 7. Eliminar

``` sql
DROP TABLE clientes;
DROP DATABASE empresa;
TRUNCATE TABLE clientes;
```

-   DELETE: elimina filas.
-   TRUNCATE: vacía tabla y reinicia AUTO_INCREMENT.
-   DROP: elimina el objeto completo.

## 8. Consultas

``` sql
SELECT nombre,edad FROM clientes;

WHERE edad>=18
AND ciudad='Barranquilla'
OR ciudad='Bogotá';

ORDER BY nombre ASC;
ORDER BY edad DESC;

LIMIT 10;
```

## 9. Búsquedas

``` sql
LIKE 'A%'
LIKE '%ez'
LIKE '%an%'
IN ('A','B')
BETWEEN 18 AND 30
IS NULL
IS NOT NULL
```

## 10. Agregación

``` sql
COUNT(*)
SUM(total)
AVG(precio)
MAX(precio)
MIN(precio)
```

``` sql
GROUP BY ciudad
HAVING COUNT(*)>5;
```

## 11. JOIN (muy importante)

``` sql
INNER JOIN
LEFT JOIN
RIGHT JOIN
```

Ejemplo:

``` sql
SELECT c.nombre,p.nombre
FROM categorias c
INNER JOIN productos p
ON c.id=p.categoria_id;
```

## 12. Claves foráneas

``` sql
FOREIGN KEY(cliente_id)
REFERENCES clientes(id)
```

## 13. Normalización

-   1FN: sin grupos repetidos.
-   2FN: depende de toda la clave.
-   3FN: sin dependencias transitivas.

## 14. Orden de ejecución mental

FROM → JOIN → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT

## 15. Errores comunes

-   Olvidar WHERE.
-   Comparar NULL con = (usar IS NULL).
-   Usar FLOAT para dinero.
-   No definir PRIMARY KEY.
-   Confundir DELETE, TRUNCATE y DROP.

## 16. Antes del examen

-   Identifica entidades.
-   Define PK.
-   Crea relaciones.
-   Define FK.
-   Escoge tipos de datos adecuados.
-   Normaliza hasta 3FN.
-   Verifica cardinalidades.

Tipos de datos
INT: IDs.
TINYINT: edades/estados.
DECIMAL(10,2): dinero.
VARCHAR: texto variable.
CHAR: longitud fija.
TEXT: texto largo.
DATE/DATETIME/TIME: fechas y horas.
BOOLEAN: 0/1.
DDL
CREATE DATABASE, USE, CREATE TABLE, ALTER TABLE (ADD, MODIFY, CHANGE, DROP COLUMN, RENAME), DROP TABLE, TRUNCATE.
DML
INSERT, SELECT, UPDATE, DELETE. Nunca UPDATE o DELETE sin WHERE salvo que quieras afectar toda la tabla.
Restricciones
PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT, AUTO_INCREMENT.
Consultas
WHERE, AND, OR, NOT, LIKE, IN, BETWEEN, IS NULL, ORDER BY, LIMIT.
Agregación
COUNT, SUM, AVG, MAX, MIN, GROUP BY, HAVING.
JOIN
INNER: coincidencias. LEFT: todo izquierda. RIGHT: todo derecha.
Normalización
1FN: datos atómicos. 2FN: depende de toda la PK. 3FN: eliminar dependencias transitivas.
Orden SQL
FROM -> JOIN -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY -> LIMIT.
Checklist
Entidades, PK, FK, tipos de datos, relaciones, cardinalidad, 3FN, probar SELECT.