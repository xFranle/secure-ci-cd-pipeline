# Implementación de Pipeline CI/CD Seguro para una Aplicación Flask utilizando GitHub Actions

## Descripción

Este proyecto demuestra la implementación de un pipeline de Integración Continua y Despliegue Continuo (CI/CD) seguro utilizando GitHub Actions, integrado con una aplicación web sencilla construida en Flask. El objetivo principal es mostrar cómo integrar herramientas de seguridad en un pipeline CI/CD para automatizar la construcción, pruebas y análisis de seguridad del código antes de su despliegue a producción. Esto asegura que el código sea de alta calidad y esté libre de vulnerabilidades conocidas, manteniendo así la integridad y seguridad de la aplicación.

---

## Tabla de Contenidos

1. [Instalación](#1-instalaci%C3%B3n)
   - [Requisitos Previos](#11-requisitos-previos)
   - [Clonar el Repositorio](#12-clonar-el-repositorio)
   - [Instalar Dependencias](#13-instalar-dependencias)
2. [Ejecución](#2-ejecuci%C3%B3n)
3. [Pipeline CI/CD](#3-pipeline-cicd)
   - [Archivo de Configuración del Pipeline](#archivo-de-configuraci%C3%B3n-del-pipeline)
4. [Análisis Estático (SAST) con SonarCloud](#4-an%C3%A1lisis-est%C3%A1tico-sast-con-sonarcloud)
   - [Configuración](#configuraci%C3%B3n-sonarcloud)
5. [Análisis de Dependencias con Snyk](#5-an%C3%A1lisis-de-dependencias-con-snyk)
   - [Configuración](#configuraci%C3%B3n-snyk)
6. [Análisis Dinámico (DAST) con OWASP ZAP](#6-an%C3%A1lisis-din%C3%A1mico-dast-con-owasp-zap)
   - [Consideraciones](#consideraciones)
   - [Configuración en el Pipeline](#configuraci%C3%B3n-en-el-pipeline)
7. [Tecnologías Utilizadas](#7-tecnolog%C3%ADas-utilizadas)
8. [Licencia](#8-licencia)

---

## 1. Instalación

Sigue los siguientes pasos para configurar el proyecto en tu máquina local.

### 1.1 Requisitos Previos

- Python
- pip (se instala junto con Python)
- Git

### 1.2 Clonar el Repositorio

```bash 
git clone https://github.com/xFranle/secure-ci-cd-pipeline
```

### 1.3 Instalar Dependencias

```bash 
pip install --upgrade pip
pip install -r requirements.txt
```

---

### 2. Ejecución

Para ejecutar la aplicación localmente, utiliza el siguiente comando:
```bash 
python app.py
```
La aplicación estará disponible en http://localhost:5000.

---

### 3. Pipeline CI/CD
El proyecto utiliza GitHub Actions para automatizar el pipeline CI/CD, que incluye:

1. Chequeo del Código Fuente: Clona el repositorio y prepara el entorno.
2. Análisis Estático (SAST) con SonarCloud: Detecta vulnerabilidades y problemas de calidad en el código.
3. Instalación de Dependencias: Instala las dependencias especificadas en requirements.txt.
4. Análisis de Dependencias con Snyk: Identifica vulnerabilidades en las dependencias del proyecto.
5. Ejecución de Pruebas Unitarias: Verifica que la aplicación funcione como se espera.
6. Análisis Dinámico (DAST) con OWASP ZAP: Realiza pruebas de penetración automatizadas en la aplicación en ejecución.

#### Archivo de Configuración del Pipeline
El pipeline está definido en el archivo .github/workflows/ci-cd.yml.

---

### 4. Análisis Estático (SAST) con SonarCloud
SonarCloud analiza el código fuente para detectar:

- Vulnerabilidades de seguridad
- Bugs
- Code Smells

#### Configuración SonarCloud
1. Cuenta en SonarCloud: Regístrate en SonarCloud.
2. Vinculación con GitHub: Conecta tu cuenta de SonarCloud con GitHub.
3. Creación del Proyecto: Crea un nuevo proyecto y obtén el projectKey y organization.
4. Token de Autenticación: Genera un token en SonarCloud y configúralo como SONAR_TOKEN en los secretos del repositorio.

---

### 5. Análisis de Dependencias con Snyk
Snyk analiza las dependencias especificadas en requirements.txt para encontrar vulnerabilidades conocidas.

#### Configuración Snyk
1. Cuenta en Snyk: Regístrate en Snyk.
2. Integración con GitHub: Autoriza a Snyk a acceder a tus repositorios.
3. Token de Autenticación: Genera un token en Snyk y configúralo como SNYK_TOKEN en los secretos del repositorio.

---
   
### 6. Análisis Dinámico (DAST) con OWASP ZAP
OWASP ZAP realiza pruebas de seguridad dinámicas en la aplicación en ejecución.

#### Consideraciones
- Accesibilidad: La aplicación debe estar desplegada y accesible públicamente para que OWASP ZAP pueda realizar el escaneo.
#### Configuración en el Pipeline
En el archivo de configuración, reemplaza 'http://your_app_url' con la URL real de tu aplicación.

---

### 7. Tecnologías Utilizadas
- Python
- Flask: Microframework web para Python.
- GitHub Actions: Plataforma de CI/CD.
- SonarCloud: Servicio de análisis estático de código.
- Snyk: Herramienta de seguridad para análisis de dependencias.
- OWASP ZAP: Herramienta para pruebas de penetración automatizadas.

---

### 8. Licencia
Este proyecto está bajo la Licencia MIT.
