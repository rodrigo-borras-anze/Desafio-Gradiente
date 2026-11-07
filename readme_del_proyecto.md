# Desafío Académico de Métodos Numéricos: GCP en Finanzas

Este repositorio contiene la implementación de una aplicación web interactiva desarrollada para el Desafío Académico de Métodos Numéricos. El proyecto aplica el **Método de Gradientes Conjugados Precondicionado (GCP)** para resolver problemas de planificación financiera y distribución de recursos organizacionales.

**Mención Académica:** Ingeniería de Sistemas
**Área:** Finanzas (Asignación de presupuestos y flujos interdepartamentales)

## Descripción del Proyecto

El sistema modela y resuelve interactivamente un sistema lineal de ecuaciones $Ax = b$ de tamaño $n=4$. La matriz $A$ (simétrica y definida positiva) representa el flujo de caja interdepartamental y las reglas de negocio entre cuatro proyectos tecnológicos. El vector $b$ representa el valor organizacional esperado.

El objetivo de la aplicación es contrastar la eficiencia algorítmica del Gradiente Conjugado simple frente al precondicionado (utilizando el Precondicionador de Jacobi), garantizando una tolerancia de convergencia de $10^{-6}$ a través de tres escenarios de evaluación.

## Arquitectura del Software

El proyecto está diseñado bajo una arquitectura de **Single-Page Application (SPA)** estática, priorizando la reactividad y portabilidad sin dependencias externas:

*   **Frontend (UI/UX):** HTML5 y CSS3 semántico nativo.
*   **Lógica de Negocio y Matemáticas:** Vanilla JavaScript (ES6+).
*   **Módulos Clave:**
    *   Motor de cálculo de álgebra lineal (Eliminación Gaussiana, GC, GCP).
    *   Gestor de estado para la carga de escenarios financieros.
    *   Módulo de pruebas de calidad (QA) y validación de entrada de datos (simetría y definición positiva).

## Instrucciones de Instalación y Ejecución Local

Dado que la aplicación no requiere un servidor backend (Serverless) ni procesos de compilación (build steps), la ejecución local es directa:

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/TU_USUARIO/TU_REPOSITORIO.git
   ```
2. **Navegar al directorio del proyecto:**
   ```bash
   cd TU_REPOSITORIO
   ```
3. **Ejecución:**
   Abre el archivo `index.html` directamente en cualquier navegador web moderno (Google Chrome, Mozilla Firefox, Edge o Safari).
   *En sistemas basados en Unix puedes usar la terminal:*
   ```bash
   open index.html # macOS
   xdg-open index.html # Linux
   ```

## Escenarios Financieros Modelados

La aplicación cuenta con botones de carga rápida para evaluar el algoritmo bajo tres contextos de negocio:

1. **Escenario Ideal (Equilibrado):** Flujo de caja estable, matriz bien condicionada con diagonal dominante.
2. **Escenario Bajo Estrés:** Fuerte interdependencia departamental y reducción general del presupuesto esperado.
3. **Escenario Mal Condicionado:** Desescalamiento severo debido a un proyecto principal con costos abismalmente mayores al resto, demostrando la superioridad del Precondicionador de Jacobi.

## Módulo de QA Integrado

La interfaz web incluye un módulo de pruebas visible que valida:
* La correcta actualización reactiva de los flujos de caja.
* El manejo de excepciones sin colapso del DOM ante matrices asimétricas.
* La demostración de la reducción de iteraciones del GCP frente al GC simple.

## Referencias

* Suñagua S., P. (2020). *Método de Gradientes Conjugados Precondicionado*. Revista Boliviana de Matemática UMSA, 04, 2-7.
* Golub, G. H., & Van Loan, C. F. (2013). *Matrix Computations* (4th ed.). Johns Hopkins University Press.