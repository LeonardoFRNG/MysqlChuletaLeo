# 📌 <Nombre del Proyecto>

Breve descripción del proyecto.

## 📖 Descripción

Este proyecto tiene como objetivo <explicar qué hace el proyecto o cuál fue el propósito de la actividad>.

---

## 🛠️ Tecnologías utilizadas

- MySQL
- SQL
- MySQL Workbench
- Git
- GitHub

---

## 📂 Estructura del proyecto

```
📁 proyecto/
│── 📄 README.md
│── 📄 script.sql
│── 📄 modelo_relacional.png
│── 📄 diagrama_er.png
│── 📄 datos.csv
│── 📁 backups/
└── 📁 evidencias/
```

---

## 🚀 Cómo ejecutar el proyecto

### 1. Clonar el repositorio

```bash
git clone https://github.com/<usuario>/<repositorio>.git
```

### 2. Entrar a la carpeta

```bash
cd <repositorio>
```

### 3. Abrir MySQL Workbench

Crear una nueva base de datos.

```sql
CREATE DATABASE nombre_bd;
USE nombre_bd;
```

### 4. Ejecutar el archivo SQL

Abrir `script.sql` y ejecutarlo.

---

## 🗄️ Base de datos

Nombre de la base de datos:

```sql
nombre_bd
```

---

## 📊 Modelo Relacional

Agregar aquí una imagen del modelo relacional.

```text
docs/modelo_relacional.png
```

---

## 📌 Diagrama Entidad-Relación

Agregar aquí el diagrama ER.

```text
docs/diagrama_er.png
```

---

## 📥 Importación de datos

Si el proyecto utiliza archivos CSV:

1. Abrir MySQL Workbench.
2. Clic derecho sobre la tabla.
3. Table Data Import Wizard.
4. Seleccionar el archivo CSV.
5. Importar los datos.

---

## 📄 Consultas importantes

Ejemplo:

```sql
SELECT *
FROM clientes;
```

```sql
SELECT nombre, correo
FROM clientes
WHERE edad >= 18;
```

```sql
SELECT COUNT(*)
FROM pedidos;
```

---

## 📷 Evidencias

Agregar capturas de:

- Base de datos creada.
- Tablas.
- Consultas.
- Resultados.
- Modelo relacional.

---

## 👨‍💻 Autor

**Nombre:** <Tu nombre>

GitHub: https://github.com/<usuario>

---

## 📜 Licencia

Proyecto con fines académicos.
