# 🐧📊 Streamlit Penguins Dashboard

<p align="center">
  <img src="img/dashboard-principal.png" alt="Dashboard Streamlit Penguins" width="750">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Streamlit-Dashboard-red?style=for-the-badge&logo=streamlit">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-purple?style=for-the-badge&logo=pandas">
  <img src="https://img.shields.io/badge/Plotly-Interactive%20Charts-orange?style=for-the-badge&logo=plotly">
  <img src="https://img.shields.io/badge/Pytest-Unit%20Testing-green?style=for-the-badge&logo=pytest">
</p>

---

## 🌟 Descripción General

**Streamlit Penguins Dashboard** es una aplicación web interactiva desarrollada con **Streamlit** para realizar análisis exploratorio de datos sobre el dataset **Palmer Penguins**.

El sistema permite cargar archivos CSV, visualizar datos de forma dinámica, generar gráficos interactivos y validar el funcionamiento del código mediante pruebas unitarias con **pytest**.

Este proyecto fue desarrollado como parte de la asignatura de **Control de Versiones**, aplicando el flujo de trabajo **Gitflow** con ramas `feature/*`, `develop`, `release/*` y `main`.

---

## 🎯 Propósito

Herramienta de análisis de datos que permite cargar archivos CSV, generar visualizaciones automáticas y explorar los datos de forma tabular, orientada al estudio de las características físicas de tres especies de pingüinos antárticos.

---

## 📂 Estructura del Proyecto

```
streamlit-penguins-dashboard/
├── app.py                      # Aplicación principal Streamlit
├── src/
│   ├── __init__.py
│   └── data_utils.py           # Funciones de validación y utilidades
├── tests/
│   └── test_data_utils.py      # Pruebas unitarias (9 tests)
├── data/
│   └── penguins.csv            # Dataset Palmer Penguins
├── img/                        # Capturas de pantalla
├── requirements.txt            # Dependencias
├── INFORME.md                  # Informe de desarrollo
└── README.md
```

---

## 🛠️ Stack Tecnológico

| Tecnología | Uso |
|---|---|
| Python 3.12 | Lenguaje principal |
| Streamlit | Dashboards interactivos |
| Pandas | Manipulación de datos |
| Plotly | Gráficos interactivos |
| Pytest | Pruebas unitarias |
| Git + Gitflow | Control de versiones |

---

## 📊 Funcionalidades

| Funcionalidad | Descripción |
|---|---|
| Carga de CSV | Validación de extensión, codificación y estructura |
| Gráfico de barras | Suma de valores numéricos por categoría |
| Gráfico de líneas | Evolución de variables numéricas |
| Gráfico de dispersión | Relación entre dos variables |
| Vista tabular | Primeros o últimos N registros del dataset |
| Pruebas unitarias | 9 tests que validan las funciones del sistema |

---

## 🔄 Flujo Gitflow

```
main ← release/1.0.0 ← develop ← feature/validacion
                                 ← feature/app-principal
                                 ← feature/visualizacion-tabular
                                 ← feature/pruebas-pytest
```

| Rama | Propósito |
|---|---|
| `main` | Código estable en producción |
| `develop` | Integración de features |
| `feature/validacion` | Funciones de validación CSV |
| `feature/app-principal` | Dashboard con gráficos |
| `feature/visualizacion-tabular` | Tabla de datos con filtros |
| `feature/pruebas-pytest` | Pruebas unitarias |
| `release/1.0.0` | Versión estable publicada |

---

## 👥 Integrantes

| Nombre | Rol |
|---|---|
| Andre Yamada | Desarrollo y configuración |
| Ruperto Cisneros | Desarrollo y documentación |

---



