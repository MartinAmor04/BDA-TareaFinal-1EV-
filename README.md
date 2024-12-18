# BDA-TareaFinal-1EV

Este repositorio contiene los recursos necesarios para la entrega final de la evaluación del módulo de Bases de Datos Avanzadas.

## Instrucciones para Configurar el Entorno e Instalar las Dependencias

Sigue estos pasos para configurar un entorno virtual y preparar el proyecto:

### 1. Crear y Activar el Entorno Virtual
Usaremos Conda para gestionar el entorno. Ejecuta los siguientes comandos en tu terminal:

```bash
conda create --name rag python=3.13.1 
conda activate rag
conda install pip 
```
Con el entorno activado, instala todas las librerías necesarias desde el archivo requirements.txt:
```bash
pip install -r requirements.txt
```
# Desarrollo de un Sistema RAG

El objetivo de este ejercicio es crear un sistema **RAG (Retrieved Augmented Generation)**. Este tipo de sistema combina un **modelo de lenguaje grande (LLM)** con una base de datos propia para responder preguntas realizadas por el usuario, proporcionando respuestas fundamentadas en los datos disponibles.

## Apartados del Ejercicio

A continuación, se describen los diferentes apartados que se desarrollarán para implementar el sistema RAG:

### 1. RAG en Inglés con Datos de una Página Web
En este apartado, se desarrollará un sistema RAG que construye una **base de datos vectorial** utilizando datos extraídos de una página web. Este sistema será capaz de procesar el contenido recuperado y responder preguntas basándose en dicha información.

### 2. RAG en Español con Datos de uno o Varios Archivos PDF
Se creará un RAG que utiliza archivos PDF como fuente de datos. El sistema dividirá el texto de los documentos en fragmentos, los almacenará en una **base de datos vectorial** y generará respuestas basadas en ellos, en español.

### 3. Crear una Interfaz Gráfica (GUI) para uno de los RAGs
Se desarrollará una interfaz gráfica de usuario (GUI) para interactuar con uno de los sistemas RAG creados anteriormente. La GUI permitirá que los usuarios formulen preguntas y reciban respuestas de una manera sencilla e intuitiva.

### 4. RAG Dockerizado contra Mongo Atlas
Se implementará un RAG dockerizado que utiliza **Mongo Atlas** como base de datos para almacenar y gestionar la vector store. Este sistema ofrecerá una solución robusta y escalable para el manejo de datos y consultas.

---





