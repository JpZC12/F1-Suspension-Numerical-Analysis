# Análisis Dinámico y Optimización de Suspensión (Formula Student)

![MATLAB](https://img.shields.io/badge/MATLAB-Simulation-blue?logo=mathworks)
![Autodesk Fusion](https://img.shields.io/badge/Autodesk%20Fusion-FEA%20%26%20CAD-orange)
![Numerical Methods](https://img.shields.io/badge/Methods-Runge--Kutta%20%7C%20Optimization-success)

## Descripción del Proyecto
Este repositorio contiene el código fuente y los modelos mecánicos para la simulación, análisis numérico y optimización del sistema de suspensión (masa-resorte-amortiguador) de un monoplaza de **Formula Student**. 

El proyecto demuestra un ciclo completo de ingeniería mecatrónica: partiendo de la resolución de ecuaciones diferenciales y métodos numéricos en MATLAB, hasta la validación estructural mediante Análisis de Elemento Finito (FEA) en Autodesk Fusion.

## Metodología Computacional (MATLAB)
El núcleo numérico se encarga de resolver los problemas físicos de la dinámica vehicular:
1. **Solución de ODEs:** Implementación del método de Runge-Kutta de cuarto orden (RK4) y `ode45` para predecir la respuesta transitoria del sistema ante perturbaciones del asfalto.
2. **Análisis Modal:** Extracción de frecuencias naturales del sistema utilizando valores y vectores propios (`eig`).
3. **Procesamiento de Datos:** Aplicación de Transformada Rápida de Fourier (FFT) y Splines cúbicos sobre datos de telemetría simulada.
4. **Optimización Mecánica:** Minimización de la energía potencial del sistema empleando `fminbnd` para encontrar los coeficientes óptimos de rigidez ($k$).

## Integración CAD/FEA (Autodesk Fusion)
Para cerrar la brecha entre el modelo matemático y la realidad manufacturable, se diseñó el balancín (*Rocker*) de la suspensión en Autodesk Fusion.
* **Cargas Importadas:** Las fuerzas pico de compresión extraídas de las gráficas de MATLAB se utilizaron como las *Boundary Conditions* en el modelo 3D.
* **Validación:** Se ejecutó un análisis de esfuerzo estático (FEA), confirmando que la geometría diseñada soporta las cargas calculadas con un factor de seguridad de 1.8.

## Cómo ejecutar las simulaciones
1. Clona el repositorio: `git clone https://github.com/tu-usuario/F1-Suspension-Numerical-Analysis.git`
2. Abre MATLAB y navega a la carpeta `/src`.
3. Ejecuta el archivo principal `solver_RK4.m` para visualizar los *Phase-plane plots* y la cinemática del amortiguador.
