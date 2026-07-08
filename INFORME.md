# 📋 Informe de Desarrollo

## 🐧 Streamlit Penguins Dashboard

### Análisis de Datos con Streamlit aplicando Gitflow

<p align="center">
  <img src="img/dashboard-graficos.png" alt="Streamlit Penguins Dashboard" width="750">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Streamlit-Dashboard-red?style=for-the-badge&logo=streamlit">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-purple?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Charts-orange?style=for-the-badge&logo=plotly">
  <img src="https://img.shields.io/badge/Pytest-Testing-green?style=for-the-badge&logo=pytest">
  <img src="https://img.shields.io/badge/Gitflow-Version%20Control-black?style=for-the-badge&logo=git">
</p>

---

## 👥 Integrantes

| 👤 Nombre            | 🎓 Carrera             | 🏫 Institución |
| -------------------- | ---------------------- | -------------- |
| **Andre Yamada**     | Ingeniería en Software | ESPOCH         |
| **Ruperto Cisneros** | Ingeniería en Software | ESPOCH         |

---

## 📌 1. Objetivo del Proyecto

Desarrollar una aplicación web interactiva utilizando **Streamlit** para realizar el análisis exploratorio del dataset **Palmer Penguins**, incorporando funcionalidades de carga de archivos CSV, visualización gráfica, consulta tabular y validación mediante pruebas unitarias.

Además, el desarrollo del proyecto se gestionó mediante el flujo de trabajo **Gitflow**, con el propósito de aplicar buenas prácticas de control de versiones, separación de funcionalidades por ramas y publicación controlada de una versión estable.

---

## 🧭 2. Descripción General del Proyecto

El proyecto **Streamlit Penguins Dashboard** consiste en una aplicación web orientada al análisis de datos, que permite al usuario cargar un archivo CSV desde el navegador y visualizar información relevante mediante gráficos interactivos.

La solución fue construida con una arquitectura sencilla y modular, separando la aplicación principal de las funciones utilitarias y las pruebas unitarias.

### Funcionalidades principales

| Módulo                       | Descripción                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------ |
| 📂 **Carga de CSV**          | Permite cargar archivos `.csv` desde la interfaz web                           |
| ✅ **Validación de datos**    | Verifica extensión, lectura y estructura del archivo                           |
| 📊 **Gráficos interactivos** | Genera gráficos de barras, líneas y dispersión                                 |
| 📋 **Visualización tabular** | Permite mostrar los primeros o últimos registros del dataset                   |
| 🧪 **Pruebas unitarias**     | Valida las funciones principales con pytest                                    |
| 🌿 **Gitflow**               | Organiza el desarrollo mediante ramas `feature`, `develop`, `release` y `main` |

---

## 🗺️ 3. Flujo Gitflow Utilizado

El proyecto fue desarrollado siguiendo el modelo **Gitflow**, utilizando ramas independientes para cada funcionalidad. No se aplicó resolución de conflictos ni uso de ramas `hotfix`, conforme a los requerimientos establecidos para la tarea.

```text
main ─────────────────────────────────────────────── ● v1.0.0
                                                    ↑
release/1.0.0 ───────────────────────────────────── ●
                                                    ↑
develop ── ● ── ● ── ● ── ● ── ● ───────────────── ●
            ↑    ↑    ↑    ↑
            │    │    │    └── feature/pruebas-pytest
            │    │    └─────── feature/visualizacion-tabular
            │    └──────────── feature/app-principal
            └───────────────── feature/validacion
```

### Descripción del flujo aplicado

| Rama                            | Propósito                                                      |
| ------------------------------- | -------------------------------------------------------------- |
| `main`                          | Rama estable del proyecto. Contiene la versión final publicada |
| `develop`                       | Rama de integración de funcionalidades                         |
| `feature/validacion`            | Desarrollo de funciones de validación y utilidades de datos    |
| `feature/app-principal`         | Desarrollo de la aplicación principal en Streamlit             |
| `feature/visualizacion-tabular` | Desarrollo de la sección de visualización de datos             |
| `feature/pruebas-pytest`        | Implementación de pruebas unitarias                            |
| `release/1.0.0`                 | Preparación de la versión final antes de publicarla en `main`  |

> 🔑 Cada funcionalidad se desarrolló en su propia rama `feature/*`, posteriormente se integró a `develop` mediante merge y finalmente se publicó en `main` a través de la rama `release/1.0.0`.

---

# 🔧 4. Procedimiento de Desarrollo

---

## 🟢 4.1 Preparación del Entorno

Se creó el directorio principal del proyecto, se inicializó el repositorio Git, se configuró un entorno virtual de Python y se instalaron las dependencias necesarias.

```bash
mkdir streamlit-penguins-dashboard
cd streamlit-penguins-dashboard
git init
python3 -m venv dash
source dash/bin/activate
pip install streamlit pandas plotly pytest
```

### Dependencias instaladas

| Paquete       | Propósito                                 |
| ------------- | ----------------------------------------- |
| **Streamlit** | Creación de la aplicación web interactiva |
| **Pandas**    | Manipulación, lectura y análisis de datos |
| **Plotly**    | Generación de gráficos interactivos       |
| **Pytest**    | Ejecución de pruebas unitarias            |

Posteriormente, se realizó el primer commit en la rama `main` y se creó la rama `develop`.

```bash
git add .
git commit -m "chore: estructura inicial del proyecto"
git checkout -b develop
```

---

## 🔵 4.2 Feature 1: Funciones de Validación

### Rama utilizada

```text
feature/validacion
```

En esta etapa se implementó el archivo `src/data_utils.py`, encargado de centralizar las funciones auxiliares para la carga, validación y filtrado de datos.

### Funciones desarrolladas

| # | Función                          | Descripción                                                                 |
| - | -------------------------------- | --------------------------------------------------------------------------- |
| 1 | `validar_extension_csv()`        | Verifica que el archivo cargado tenga extensión `.csv`                      |
| 2 | `cargar_csv()`                   | Carga archivos CSV considerando codificaciones `utf-8`, `latin1` y `cp1252` |
| 3 | `obtener_columnas_numericas()`   | Identifica las columnas numéricas del dataset                               |
| 4 | `obtener_columnas_categoricas()` | Identifica columnas categóricas o de texto                                  |
| 5 | `filtrar_registros()`            | Permite obtener los primeros o últimos registros del dataset                |

### Comandos ejecutados

```bash
git checkout -b feature/validacion

# Desarrollo del archivo src/data_utils.py

git add .
git commit -m "feat: crear funciones de validacion CSV y utilidades de datos"
git checkout develop
git merge feature/validacion
```

### Resultado obtenido

Se obtuvo un módulo reutilizable para validar y procesar archivos CSV, mejorando la organización del código y facilitando la implementación posterior de pruebas unitarias.

---

## 🟣 4.3 Feature 2: Aplicación Principal Streamlit

### Rama utilizada

```text
feature/app-principal
```

En esta fase se desarrolló el archivo `app.py`, correspondiente a la aplicación principal del dashboard.

### Funcionalidades implementadas

| Funcionalidad                | Descripción                                                  |
| ---------------------------- | ------------------------------------------------------------ |
| 📁 **Carga de archivos CSV** | Permite seleccionar y cargar archivos desde la barra lateral |
| 📊 **Gráfico de barras**     | Agrupa una categoría y suma valores numéricos                |
| 📈 **Gráfico de líneas**     | Visualiza el comportamiento de una variable numérica         |
| 🔎 **Gráfico de dispersión** | Muestra la relación entre dos variables numéricas            |

### Captura del dashboard

<p align="center">
  <img src="img/dashboard-graficos.png" alt="Dashboard con gráficos" width="750">
</p>

### Captura del gráfico de dispersión

<p align="center">
  <img src="img/grafico-dispersion.png" alt="Gráfico de dispersión" width="750">
</p>

### Comandos ejecutados

```bash
git checkout -b feature/app-principal

# Desarrollo del archivo app.py

git add .
git commit -m "feat: crear aplicacion principal Streamlit con carga CSV y graficas"
git checkout develop
git merge feature/app-principal
```

### Resultado obtenido

Se construyó una aplicación funcional en Streamlit que permite cargar datos y generar visualizaciones interactivas para facilitar el análisis exploratorio del dataset.

---

## 🟠 4.4 Feature 3: Visualización Tabular

### Rama utilizada

```text
feature/visualizacion-tabular
```

En esta etapa se agregó una sección para visualizar los datos en formato tabular, permitiendo al usuario revisar el contenido del dataset de forma dinámica.

### Opciones implementadas

| Opción                       | Descripción                                    |
| ---------------------------- | ---------------------------------------------- |
| 🔢 **Cantidad de registros** | Permite seleccionar cuántas filas mostrar      |
| ⬆️ **Inicio del dataset**    | Muestra los primeros registros                 |
| ⬇️ **Final del dataset**     | Muestra los últimos registros                  |
| 📋 **Tabla dinámica**        | Presenta los datos cargados en formato tabular |

### Comandos ejecutados

```bash
git checkout -b feature/visualizacion-tabular

# Desarrollo de la sección tabular en app.py

git add .
git commit -m "feat: agregar visualizacion tabular con filtro de registros"
git checkout develop
git merge feature/visualizacion-tabular
```

### Resultado obtenido

La aplicación permite consultar los datos cargados en una tabla interactiva, brindando al usuario mayor control sobre la exploración del dataset.

---

## 🔴 4.5 Feature 4: Pruebas Unitarias con Pytest

### Rama utilizada

```text
feature/pruebas-pytest
```

Se implementaron pruebas unitarias en el archivo `tests/test_data_utils.py`, con el objetivo de validar el correcto funcionamiento de las funciones desarrolladas en `src/data_utils.py`.

### Pruebas implementadas

| # | Prueba                                     | Qué valida                                  | Resultado |
| - | ------------------------------------------ | ------------------------------------------- | --------- |
| 1 | `test_validar_extension_csv_correcta`      | Acepta archivos con extensión `.csv`        | ✅ PASSED  |
| 2 | `test_validar_extension_csv_mayuscula`     | Acepta archivos con extensión `.CSV`        | ✅ PASSED  |
| 3 | `test_validar_extension_csv_incorrecta`    | Rechaza archivos con extensión `.xlsx`      | ✅ PASSED  |
| 4 | `test_columnas_numericas_penguins`         | Detecta correctamente columnas numéricas    | ✅ PASSED  |
| 5 | `test_columnas_categoricas_penguins`       | Detecta correctamente columnas categóricas  | ✅ PASSED  |
| 6 | `test_filtrar_registros_inicio_penguins`   | Filtra correctamente los primeros registros | ✅ PASSED  |
| 7 | `test_filtrar_registros_final_penguins`    | Filtra correctamente los últimos registros  | ✅ PASSED  |
| 8 | `test_filtrar_registros_cantidad_invalida` | Lanza error cuando la cantidad es inválida  | ✅ PASSED  |
| 9 | `test_filtrar_registros_posicion_invalida` | Lanza error cuando la posición no es válida | ✅ PASSED  |

### Captura de ejecución de pruebas

<p align="center">
  <img src="img/pytest-resultados.png" alt="Resultados pytest" width="750">
</p>

### Comandos ejecutados

```bash
git checkout -b feature/pruebas-pytest

# Desarrollo de tests/test_data_utils.py

git add .
git commit -m "test: agregar pruebas unitarias con pytest para validaciones"
git checkout develop
git merge feature/pruebas-pytest
```

### Resultado obtenido

Se ejecutaron correctamente las 9 pruebas unitarias, confirmando que las funciones principales del proyecto cumplen con los resultados esperados.

---

# 🏁 5. Release 1.0.0

Una vez integradas todas las funcionalidades en `develop`, se creó la rama `release/1.0.0` para preparar la versión final del proyecto.

Posteriormente, se realizó el merge hacia `main`, se generó el tag `v1.0.0` y se volvió a integrar la rama release hacia `develop`.

### Comandos ejecutados

```bash
git checkout develop
git checkout -b release/1.0.0
git commit --allow-empty -m "release: version 1.0.0"

# Merge hacia main y creación del tag
git checkout main
git merge release/1.0.0
git tag -a v1.0.0 -m "Release version 1.0.0"
git push origin main
git push origin v1.0.0

# Merge de retorno hacia develop
git checkout develop
git merge release/1.0.0
git push origin develop
```

### Captura del historial Git

<p align="center">
  <img src="img/gitflow-log.png" alt="Historial Gitflow" width="750">
</p>

### Resultado obtenido

Se publicó la versión estable del proyecto en la rama `main` y se etiquetó correctamente como `v1.0.0`.

---

# 📊 6. Resumen de Ramas y Commits

| Rama                            | Commit principal                                                      | Tipo de cambio              |
| ------------------------------- | --------------------------------------------------------------------- | --------------------------- |
| `main`                          | `chore: estructura inicial del proyecto`                              | Inicialización del proyecto |
| `feature/validacion`            | `feat: crear funciones de validacion CSV y utilidades de datos`       | Nueva funcionalidad         |
| `feature/app-principal`         | `feat: crear aplicacion principal Streamlit con carga CSV y graficas` | Nueva funcionalidad         |
| `feature/visualizacion-tabular` | `feat: agregar visualizacion tabular con filtro de registros`         | Nueva funcionalidad         |
| `feature/pruebas-pytest`        | `test: agregar pruebas unitarias con pytest para validaciones`        | Pruebas unitarias           |
| `release/1.0.0`                 | `release: version 1.0.0`                                              | Publicación de versión      |

---

# 📁 7. Estructura Final del Proyecto

```bash
streamlit-penguins-dashboard/
├── app.py
├── src/
│   ├── __init__.py
│   └── data_utils.py
├── tests/
│   └── test_data_utils.py
├── data/
│   └── penguins.csv
├── img/
│   ├── dashboard-graficos.png
│   ├── grafico-dispersion.png
│   ├── pytest-resultados.png
│   └── gitflow-log.png
├── requirements.txt
├── README.md
└── INFORME.md
```

---

# 🧪 8. Evidencia de Pruebas

Para validar el correcto funcionamiento del proyecto, se ejecutó el siguiente comando:

```bash
python -m pytest -v
```

Resultado obtenido:

```bash
9 passed
```

Este resultado confirma que las funciones de validación, detección de columnas y filtrado de registros funcionan correctamente.

---

# 🧠 9. Conclusiones

## 📍 Conclusión 1: Aislamiento de funcionalidades mediante ramas feature

El uso de Gitflow permitió desarrollar cada funcionalidad de manera independiente mediante ramas `feature/*`. Esto evitó que los cambios en desarrollo afectaran directamente a las ramas principales del proyecto.

En este caso, las funciones de validación, la aplicación principal, la visualización tabular y las pruebas unitarias fueron desarrolladas en ramas separadas e integradas posteriormente a `develop`. Este enfoque mejora el orden del trabajo, reduce riesgos y facilita la revisión de cambios.

---

## 📍 Conclusión 2: Trazabilidad y control del historial de cambios

La utilización de nombres de ramas claros, junto con mensajes de commit descriptivos bajo una convención como `feat:`, `test:` y `release:`, permitió mantener un historial de cambios entendible y ordenado.

Esto facilita identificar qué funcionalidad fue agregada en cada etapa del proyecto, cuándo se integró y cuál fue su propósito dentro del desarrollo general.

---

## 📍 Conclusión 3: Separación entre desarrollo y versión estable

La rama `develop` funcionó como un espacio de integración para reunir todas las funcionalidades antes de publicarlas en `main`.

La rama `release/1.0.0` permitió preparar la versión final del sistema, verificar el estado del proyecto y publicar una versión estable identificada con el tag `v1.0.0`.

Este proceso garantiza que la rama `main` conserve únicamente código estable, organizado y listo para entrega.

---

# 🔗 10. Repositorios del Proyecto

| Integrante           | URL del Repositorio                                                   |
| -------------------- | --------------------------------------------------------------------- |
| **Andre Yamada**     | https://github.com/and95yam/streamlit-penguins-dashboard              |
| **Ruperto Cisneros** | https://github.com/srcisneros/streamlit-penguins-dashboard-Public.git |

---

# 📅 11. Fecha de Entrega

**8 de julio de 2026**

---

<p align="center">
  <b>🐧 Proyecto académico desarrollado con Python, Streamlit, Pytest y Gitflow 🐧</b>
</p>

<p align="center">
  <b>Ingeniería en Software — ESPOCH</b>
</p>
