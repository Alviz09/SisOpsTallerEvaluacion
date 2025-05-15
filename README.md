# Evaluación de Rendimiento: Multiplicación de Matrices

## 📎 Informe Original

Puedes consultar el informe completo en formato PDF [aquí](Informe%20de%20Evaluación%20de%20Rendimiento.pdf).

## 📘 Descripción

Este proyecto analiza y compara el rendimiento de diferentes implementaciones paralelas (Fork, OpenMP y POSIX Threads) para la multiplicación de matrices en diversos entornos de hardware y configuraciones.

## 🧠 Objetivos

- Evaluar el impacto del paralelismo en el rendimiento de la multiplicación de matrices.
- Comparar distintas implementaciones: Fork, OpenMP y POSIX.
- Estudiar el efecto del hardware y el número de hilos sobre el tiempo de ejecución.

## 💻 Plataformas Evaluadas

| Sistema | Procesador                       | Frecuencia | RAM     | SO                  | CPUs | Hilos | Núcleos |
|---------|----------------------------------|------------|---------|----------------------|------|--------|----------|
| 1       | Intel Core i7-7600U              | 2.80 GHz   | 16.27 GB| Ubuntu 18.04.6 LTS   | 4    | 2      | 2        |
| 2       | AMD Ryzen 5 5600H                | 3.29 GHz   | 7.64 GB | Ubuntu 24.04.2 LTS   | 12   | 2      | 6        |
| 3       | AMD Ryzen 7 7435HS               | 4.50 GHz   | 16 GB   | ArchLinux x86_64     | 16   | 2      | 8        |
| 4       | AMD EPYC 7B13                    | 3.05 GHz   | 64.31 GB| Ubuntu 20.04.2 LTS   | 8    | 2      | 4        |
| 5       | Intel Xeon Gold 6240R            | 2.40 GHz   | 12 GB   | Ubuntu 22.04.5 LTS   | 4    | 1      | 1        |

## ⚙️ Configuración Experimental

- **Tamaños de matrices:** 500x500, 1000x1000, 2000x2000
- **Número de hilos evaluados:** 1, 2, 4, 8, 16
- **Repeticiones:** 30 por configuración
- **Métrica principal:** Tiempo de ejecución promedio (ms)


## 📊 Tablas de Resultados
- **Sistema 1**
  
| Configuración | Fork (ms) | OpenMP (ms) | Posix (ms) |
|---------------|-----------|-------------|-------------|
| 500x1         | 375081    | 124287      | 348193      |
| 500x2         | 228023    | 77666.7     | 219651      |
| 500x4         | 228756    | 76787.6     | 214410      |
| 500x8         | 229725    | 81013.3     | 223147      |
| 500x16        | 235936    | 88520.1     | 225361      |
| 1000x1        | 4.0E+06   | 1.88E+06    | 3.88E+06    |
| 1000x2        | 2.12E+06  | 1.06E+06    | 2.17E+06    |
| 1000x4        | 2.29E+06  | 1.66E+06    | 2.31E+06    |
| 1000x8        | 2.27E+06  | 1.65E+06    | 2.27E+06    |
| 1000x16       | 2.25E+06  | 1.67E+06    | 2.25E+06    |
| 2000x1        | 3.99E+07  | 3.15E+07    | 3.98E+07    |
| 2000x2        | 2.11E+07  | 1.70E+07    | 2.19E+07    |
| 2000x4        | 2.01E+07  | 1.78E+07    | 2.01E+07    |
| 2000x8        | 2.16E+07  | 1.79E+07    | 2.17E+07    |
| 2000x16       | 2.18E+07  | 1.80E+07    | 2.18E+07    |

- **Sistema 2**
  
| Configuración | Fork (ms) | OpenMP (ms) | Posix (ms) |
|---------------|-----------|-------------|-------------|
| 500x1         | 333459    | 87371.1     | 400238      |
| 500x2         | 204840    | 46601.2     | 136203      |
| 500x4         | 109204    | 31916       | 108232      |
| 500x8         | 66744.1   | 25892.1     | 62849.3     |
| 500x16        | 61212     | 25385.7     | 60077.1     |
| 1000x1        | 3.48E+11  | 757059      | 3.66E+11    |
| 1000x2        | 1.86E+11  | 325864      | 1.86E+11    |
| 1000x4        | 915525    | 265446      | 930162      |
| 1000x8        | 748179    | 269462      | 654970      |
| 1000x16       | 594176    | 219941      | 494165      |
| 2000x1        | 2.83E+12  | 1.27E+12    | 2.85E+12    |
| 2000x2        | 1.60E+12  | 3.04E+12    | 1.55E+10    |
| 2000x4        | 8.72E+11  | 4.86E+11    | 8.73E+10    |
| 2000x8        | 5.78E+11  | 3.62E+11    | 5.85E+11    |
| 2000x16       | 4.94E+11  | 4.49E+11    | 5.53E+11    |

- **Sistema 3**
  
| Configuración | Fork (ms) | OpenMP (ms) | Posix (ms) |
|---------------|-----------|-------------|-------------|
| 500x1         | 340191    | 73109.3     | 339791      |
| 500x2         | 174012    | 38701.2     | 173509      |
| 500x4         | 90116.5   | 20200.5     | 89286.6     |
| 500x8         | 48601     | 13730.8     | 45880.1     |
| 500x16        | 35883.9   | 12548       | 31771.6     |
| 1000x1        | 2.71E+11  | 558444      | 2.72E+11    |
| 1000x2        | 1.38E+11  | 286036      | 1.38E+11    |
| 1000x4        | 721326    | 152835      | 715809      |
| 1000x8        | 382485    | 82739       | 377432      |
| 1000x16       | 258734    | 93608.8     | 237560      |
| 2000x1        | 2.43E+12  | 7.03E+11    | 2.43E+12    |
| 2000x2        | 1.28E+12  | 4.06E+10    | 1.28E+12    |
| 2000x4        | 6.65E+11  | 2.17E+11    | 6.62E+11    |
| 2000x8        | 3.64E+11  | 1.23E+11    | 3.62E+09    |
| 2000x16       | 2.03E+11  | 947484      | 2.04E+11    |

- **Sistema 4**
  
| Configuración | Fork (ms) | OpenMP (ms) | Posix (ms) |
|---------------|-----------|-------------|-------------|
| 500x1         | 112115    | 104380      | 126192      |
| 500x2         | 59512.2   | 56190.6     | 68859.6     |
| 500x4         | 39769.8   | 42513.3     | 43726.9     |
| 500x8         | 34143.4   | 35872.2     | 38778.3     |
| 500x16        | 32639.8   | 32536.9     | 35452.6     |
| 1000x1        | 932071    | 875351      | 1.02E+11    |
| 1000x2        | 476706    | 467572      | 532075      |
| 1000x4        | 365363    | 407998      | 393908      |
| 1000x8        | 323192    | 351595      | 389933      |
| 1000x16       | 323441    | 335386      | 368966      |
| 2000x1        | 1.53E+12  | 1.72E+12    | 1.65E+12    |
| 2000x2        | 7.69E+11  | 8.91E+10    | 8.54E+11    |
| 2000x4        | 6.55E+11  | 6.86E+11    | 6.73E+10    |
| 2000x8        | 5.96E+11  | 6.05E+11    | 6.26E+11    |
| 2000x16       | 5.77E+11  | 5.88E+11    | 6.11E+10    |

- **Sistema 5**
  
| Configuración | Fork (ms) | OpenMP (ms) | Posix (ms) |
|---------------|-----------|-------------|-------------|
| 500x1         | 578747    | 165231      | 577243      |
| 500x2         | 292599    | 89175.7     | 298032      |
| 500x4         | 156744    | 49405.5     | 158697      |
| 500x8         | 156752    | 49438.5     | 154133      |
| 500x16        | 157122    | 48098.2     | 150363      |
| 1000x1        | 5.35E+06  | 1.84E+06    | 5.33E+06    |
| 1000x2        | 2.54E+06  | 946214      | 2.55E+06    |
| 1000x4        | 1.17E+06  | 483623      | 1.17E+06    |
| 1000x8        | 1.17E+06  | 468183      | 1.14E+06    |
| 1000x16       | 1.19E+06  | 458066      | 1.13E+06    |
| 2000x1        | 6.13E+07  | 5.04E+07    | 6.20E+07    |
| 2000x2        | 2.95E+07  | 2.33E+07    | 2.96E+07    |
| 2000x4        | 1.38E+07  | 1.04E+07    | 1.31E+07    |
| 2000x8        | 1.32E+07  | 1.06E+07    | 1.23E+07    |
| 2000x16       | 1.48E+07  | 1.12E+07    | 1.37E+07    |


## ✅ Conclusiones Clave

- OpenMP es la implementación más eficiente en la mayoría de escenarios.
- El Sistema 3 (Ryzen 7) fue el más rápido, gracias a sus 8 núcleos y 4.5 GHz de frecuencia.
- Fork es estable, pero más lento que OpenMP; POSIX tiene un rendimiento intermedio.
- En sistemas con pocos núcleos (Sistemas 1 y 5), el incremento de hilos no mejora el rendimiento significativamente.

## 👨‍💻 Autores

- Juan Sebastián Álvarez
- Daniel Hoyos
- Carlos Santiago Pinzón Caicedo
- Samuel Jerónimo Gantiva Garzón
- Jorge Enrique Olaya Liévano

## 📋 Profesor

- John Corredor, Ph.D.

## 🔗 Repositorios Relacionados

- [Jeol28/Taller-de-Evaluacion](https://github.com/Jeol28/Taller-de-Evaluacion)
- [Alviz09/SisOpsTallerEvaluacion](https://github.com/Alviz09/SisOpsTallerEvaluacion)
- [CarlitosPinzon/TallerEvaluaci-n](https://github.com/CarlitosPinzon/TallerEvaluaci-n)
- [Danielhoyos06/Tallerevaluacionrend](https://github.com/Danielhoyos06/Tallerevaluacionrend)
- [Gantu78/TallerEvaluaciondeRendimiento](https://github.com/Gantu78/TallerEvaluaciondeRendimiento)
