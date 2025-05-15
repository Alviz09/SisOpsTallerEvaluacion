# Evaluación de Rendimiento: Multiplicación de Matrices

## 📘 Descripción

Este proyecto tiene como objetivo evaluar el rendimiento de diferentes implementaciones paralelas para la multiplicación de matrices (Fork, OpenMP y POSIX Threads), utilizando distintos sistemas y configuraciones de hardware.

## 🧠 Objetivos

- Comparar el rendimiento de distintas estrategias de paralelismo en la multiplicación de matrices.
- Analizar el impacto del número de hilos y del hardware en el tiempo de ejecución.
- Identificar posibles cuellos de botella o anomalías en la ejecución paralela.

## 🖥️ Plataformas de Evaluación

Se realizaron experimentos en 5 sistemas distintos con las siguientes características:

| Sistema | Procesador                 | Núcleos | RAM     | SO                |
|--------|-----------------------------|---------|---------|-------------------|
| 1      | Intel Core i7-7600U         | 2       | 16 GB   | Ubuntu 18.04 LTS  |
| 2      | AMD Ryzen 5 5600H           | 6       | 7.64 GB | Ubuntu 24.04 LTS  |
| 3      | AMD Ryzen 7 7435HS          | 8       | 16 GB   | ArchLinux         |
| 4      | AMD EPYC 7B13               | 4       | 64 GB   | Ubuntu 20.04 LTS  |
| 5      | Intel Xeon Gold 6240R       | 1       | 12 GB   | Ubuntu 22.04 LTS  |

## ⚙️ Configuración Experimental

- **Tamaños de matriz**: 500x500, 1000x1000, 2000x2000
- **Número de hilos**: 1, 2, 4, 8, 16
- **Repeticiones por configuración**: 30 veces
- **Métrica principal**: Tiempo de ejecución promedio (ms)

## 📊 Principales Resultados

- OpenMP resultó ser la implementación más rápida en la mayoría de las pruebas.
- El Sistema 3 (Ryzen 7, 8 núcleos) fue el más eficiente, especialmente con OpenMP.
- En sistemas con pocos núcleos (e.g., Sistema 1), el rendimiento se estabiliza o incluso empeora al usar más de 4 hilos.
- Se identificó una **anomalía significativa** en el Sistema 2 con OpenMP usando 2 hilos, donde el tiempo fue mayor que con 1 hilo.

## 📌 Análisis Destacado

- **OpenMP**: Mejor rendimiento general, pero con posibles problemas de planificación o sobrecarga en ciertas configuraciones.
- **Fork**: Escala bien, pero es más costoso por la creación de procesos.
- **POSIX Threads**: Rendimiento más estable, especialmente con división explícita del trabajo.

## 📈 Conclusiones

- El paralelismo mejora significativamente el rendimiento, especialmente con matrices grandes y más núcleos.
- El número de hilos óptimo depende del hardware. Más no siempre es mejor.
- La planificación de hilos y el manejo eficiente de la memoria son clave para evitar cuellos de botella.

## 🛠️ Recomendaciones Técnicas

- Usar `schedule(dynamic)` en OpenMP para evitar falso uso compartido.
- Usar herramientas como `perf` para perfilar el uso de caché y CPU.
- Considerar alineación de memoria para optimizar el acceso.

## 📚 Repositorios del Proyecto

- [Jeol28/Taller-de-Evaluacion](https://github.com/Jeol28/Taller-de-Evaluacion)
- [Alviz09/SisOpsTallerEvaluacion](https://github.com/Alviz09/SisOpsTallerEvaluacion)
- [CarlitosPinzon/TallerEvaluaci-n](https://github.com/CarlitosPinzon/TallerEvaluaci-n)
- [Danielhoyos06/Tallerevaluacionrend](https://github.com/Danielhoyos06/Tallerevaluacionrend)
- [Gantu78/TallerEvaluaciondeRendimiento](https://github.com/Gantu78/TallerEvaluaciondeRendimiento)

---

**Autores:**  
Juan Sebastián Álvarez, Daniel Hoyos, Carlos Santiago Pinzón Caicedo, Samuel Jerónimo Gantiva Garzón, Jorge Enrique Olaya Liévano  
**Curso:** Sistemas Operativos – Pontificia Universidad Javeriana  
**Profesor:** John Corredor, Ph.D.  
**Fecha:** 1 de mayo de 2025
