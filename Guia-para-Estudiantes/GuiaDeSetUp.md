# Guía de Setup CI/CD

## Introducción a CI/CD

CI/CD (Integración Continua y Despliegue Continuo) es una metodología que automatiza las fases de desarrollo de software, desde la integración de código hasta su despliegue en producción. Esta práctica surge como una respuesta a los problemas que enfrentan los equipos de desarrollo al integrar cambios frecuentes en el código base y garantizar que estos cambios no introduzcan errores.

## ¿Qué es CI (Integración Continua)?

La Integración Continua (CI) es el proceso de automatizar la incorporación de cambios de código en un repositorio central. Cada vez que un desarrollador sube nuevas modificaciones, estas se validan mediante una serie de pruebas automatizadas. Este enfoque permite detectar errores de manera temprana, ya que los cambios se integran con mayor frecuencia en lugar de esperar a que varias funcionalidades estén completas.

En un entorno con CI, el código es construido, probado y validado de forma automatizada, lo que mejora la calidad del software y asegura que cada modificación no rompa funcionalidades existentes. Además, se fomenta un flujo de trabajo más ágil donde los desarrolladores pueden colaborar con mayor eficiencia y confianza.

## ¿Qué es CD (Despliegue Continuo)?

El Despliegue Continuo (CD) extiende la Integración Continua al automatizar el proceso de entrega y, en algunos casos, el despliegue a entornos de producción. Una vez que el código ha pasado por las pruebas automatizadas, puede ser liberado de forma rápida y confiable. Esto reduce significativamente el tiempo que tarda una nueva característica o corrección en estar disponible para los usuarios.

En la práctica, el CD asegura que el software siempre esté en un estado que se pueda desplegar. Dependiendo de la estrategia adoptada, este proceso puede implicar Entrega Continua, donde el código está listo para desplegarse manualmente, o Despliegue Automático, donde los cambios se publican directamente en producción.

### Beneficios de CI/CD:

Los beneficios de implementar CI/CD son numerosos.

- Permite detectar errores de forma temprana gracias a la ejecución automática de pruebas en cada cambio de código.

- Se mejora la calidad del software y se reduce el tiempo que los desarrolladores gastan buscando y corrigiendo fallos. 

- Se minimizan los errores humanos al automatizar el proceso de despliegu, lo que resulta en lanzamientos más rápidos y fiables. 

- Se fomenta la colaboración entre los equipos y se estandariza la forma en la que se entrega el software, facilitando la escalabilidad y el mantenimiento a largo plazo.

## ¿Qué es un Pipeline y por qué es importante?

Un pipeline en el contexto de CI/CD es una secuencia automatizada de pasos que transforma el código fuente en un producto final listo para ser desplegado. Cada pipeline está compuesto por múltiples etapas (stages) como la compilación, ejecución de pruebas, validaciones de calidad y finalmente el despliegue.

El propósito principal de un pipeline es automatizar estos procesos para garantizar que cada cambio en el código pase por las mismas verificaciones antes de llegar a producción. Esto ayuda a mantener la calidad del software, reducir errores humanos y acelerar el tiempo de entrega.

La importancia de definir un pipeline radica en varios factores:

- Automatización y verificación consistente.

- Detección temprana de errores.

- Entrega rápida y con menos errores.

- Definir un flujo de trabajo para el equipo de desarrollo.

## Requisitos previos

Antes de empezar, asegúrate de tener lo siguiente:

- Una cuenta en **GitHub** o un servidor con **Jenkins** instalado.
- Un repositorio con tu código fuente.
- Conocimiento básico de **Git**.

## Configuración de CI/CD con GitHub Actions

### Crear el workflow

1. Ve a tu repositorio en **GitHub**.
2. Haz clic en la pestaña **Actions**.
3. Selecciona **New workflow** > **Set up a workflow yourself**.
4. Crea un archivo en **`.github/workflows/ci.yml`**.

### Definir las etapas del pipeline

Un workflow está dividido en **jobs** (trabajos) que pueden contener **steps** (pasos).

### Ejemplo de configuración

```yaml
name: Node.js CI/CD

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout del código
        uses: actions/checkout@v3

      - name: Instalar dependencias
        run: npm install

      - name: Ejecutar pruebas
        run: npm test

      - name: Desplegar
        if: github.ref == 'refs/heads/main'
        run: ./deploy.sh
```

Guarda el archivo y haz un **commit**.

## Configuración de CI/CD con Jenkins

### Instalación de Jenkins

1. Descarga Jenkins desde [jenkins.io](https://www.jenkins.io/download/).
2. Sigue las instrucciones de instalación para tu sistema operativo.
3. Accede a la interfaz web en `http://localhost:8080`.

### Crear un Pipeline

1. En Jenkins, selecciona **New Item**.
2. Elige **Pipeline** y asigna un nombre.
3. Configura el **Pipeline script**.

### Ejemplo de configuración

Pipeline básico en **Jenkinsfile**:

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh './deploy.sh'
            }
        }
    }
}
```

## Buenas prácticas en CI/CD

- **Automatiza todo:** Desde la construcción hasta el despliegue.
- **Ejecución paralela:** Ejecuta pruebas en paralelo para acelerar el pipeline.
- **Validación temprana:** Detecta errores en las primeras etapas.
- **Seguridad:** No expongas credenciales en el código.

## Recursos adicionales

- [Documentación oficial de GitHub Actions](https://docs.github.com/en/actions)
- [Guía de inicio de Jenkins](https://www.jenkins.io/doc/)
- [Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)

