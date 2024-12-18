# BDA-TareaFinal-1EV

Este repositorio contiene los recursos necesarios para la entrega final de la evaluación del módulo de Bases de Datos Avanzadas.

## Instrucciones para Configurar y Ejecutar el Modelo Llama 3.2
### 1. Crear la Red de Docker
Primero, crea una red dedicada para el proyecto, que conectará los servicios necesarios:
```bash
docker network create ollama_network 
```
### 2. Ejecutar el Contenedor de Ollama 
Inicia el contenedor de Ollama, que es el servicio que gestionará el modelo de lenguaje. Usa el siguiente comando para ejecutarlo sin GPU:
```bash
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama --net=ollama_network ollama/ollama 
```
### 3. Verificar que Ollama Está en Funcionamiento
Confirma que el servicio está activo ejecutando:
```bash
curl http://localhost:11434
```
Si todo está correcto, deberías ver la respuesta:
```bash
Ollama is running
```
### 4. Configurar Open-WebUI
Open-WebUI proporciona una interfaz gráfica para gestionar los modelos y permite interactuar con ellos mediante un chat.

Ejecuta el contenedor de Open-WebUI usando el siguiente comando:
```bash
docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=http://ollama:11434 -v open-webui:/app/backend/data --name open-webui --net=ollama_network --restart always ghcr.io/open-webui/open-webui:main
```
### 5. Descargar un Modelo de Lenguaje
Inicia sesión en Open-WebUI. Busca y descarga el modelo  **llama3.2**.
Una vez completada la descarga, verifica que el modelo aparece en la lista de modelos instalados.

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





