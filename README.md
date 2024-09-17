# Aplicación Flask con Integración de Seguridad en CI/CD

## Descripción

Este proyecto es una aplicación web sencilla construida con **Flask**. El objetivo principal es demostrar cómo integrar herramientas de seguridad en un pipeline CI/CD utilizando **GitHub Actions**. El pipeline automatiza la construcción, pruebas y análisis de seguridad del código antes de que llegue a producción, asegurando así que el código sea de alta calidad y esté libre de vulnerabilidades conocidas.

## Tabla de Contenidos

1. [Instalación](#instalación)
   - [Requisitos Previos](#requisitos-previos)
   - [Clonar el Repositorio](#clonar-el-repositorio)
   - [Instalar Dependencias](#instalar-dependencias)
2. [Ejecución](#ejecución)
3. [Pipeline CI/CD](#pipeline-cicd)
   - [Archivo de Configuración del Pipeline](#archivo-de-configuración-del-pipeline)
4. [Análisis Estático (SAST) con SonarCloud](#análisis-estático-sast-con-sonarcloud)
   - [Configuración](#configuración-sonarcloud)
5. [Análisis de Dependencias con Snyk](#análisis-de-dependencias-con-snyk)
   - [Configuración](#configuración-snyk)
6. [Análisis Dinámico (DAST) con OWASP ZAP](#análisis-dinámico-dast-con-owasp-zap)
   - [Consideraciones](#consideraciones)
   - [Configuración en el Pipeline](#configuración-en-el-pipeline)
7. [Tecnologías Utilizadas](#tecnologías-utilizadas)
8. [Licencia](#licencia)

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

### 2. Ejecución

Para ejecutar la aplicación localmente, utiliza el siguiente comando:
```bash 
python app.py
```
