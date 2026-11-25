# H08 — Hipótesis de complementariedad evolutiva asimétrica
## Formulación, variables, predicciones y criterios de falsación

**Programa:** SI–CPEA–TAE · **Versión:** 1.0 fundacional · **Estado:** propuesta no validada · **Fecha:** 2026-11-25

[← README](../README.md) · [Manifiesto](MANIFIESTO_SI_CPEA_TAE.md) · [IAE-06](IAE_06_INTEGRACION_EVOLUTIVA.md)

---

## Índice

1. [Enunciado](#1-enunciado)
2. [Motivación](#2-motivacion)
3. [Alcance y delimitación](#3-alcance-y-delimitacion)
4. [Modelo conceptual](#4-modelo-conceptual)
5. [Variables](#5-variables)
6. [Predicciones](#6-predicciones)
7. [Diseño experimental](#7-diseno-experimental)
8. [Controles y análisis](#8-controles-y-analisis)
9. [Criterios de falsación](#9-criterios-de-falsacion)
10. [Limitaciones](#10-limitaciones)
11. [Relación con H09](#11-relacion-con-h09)

## 1. Enunciado

**SI–CPEA–TAE–H08: Hipótesis de complementariedad evolutiva asimétrica.**

La evolución de sistemas artificiales con capacidades cognitivas superiores a las humanas no requiere necesariamente equivalencia intelectual entre ambos sistemas. Una relación humano–IA potencialmente beneficiosa podría mantenerse mediante mecanismos verificables de compatibilidad de objetivos, protección de intereses humanos y coexistencia evolutiva, incluso cuando la supervisión humana directa de los procesos artificiales deje de ser viable.

**Predicción general:** en modelos experimentales, determinadas arquitecturas de compatibilidad y protección podrían mantener resultados humanos protegidos bajo asimetría cognitiva y ausencia de supervisión humana directa operación por operación, incluso cuando los agentes artificiales se sometan a modificaciones internas.

**Falsación general:** la hipótesis quedaría debilitada o rechazada para el dominio estudiado si los mecanismos evaluados no mantienen las restricciones predefinidas, si la compatibilidad desaparece sistemáticamente tras cambios recursivos o si los resultados no generalizan a escenarios independientes.

## 2. Motivación

La supervisión directa presupone que el supervisor puede comprender y evaluar la operación. En sistemas con mayor capacidad, velocidad o complejidad, ese supuesto puede fallar.

H08 plantea que la relación no debe depender exclusivamente de la capacidad humana de inspeccionar cada operación. Debe estudiarse si es posible verificar propiedades, restricciones y resultados relevantes por medios complementarios.

Esto no equivale a afirmar que la seguridad pueda resolverse sin intervención humana, ni que los mecanismos actuales sean suficientes.

## 3. Alcance y delimitación

H08 se evaluará inicialmente en simulaciones de agentes sintéticos. No afirma:

- que exista actualmente una superinteligencia;
- que la inteligencia superior implique conciencia o benevolencia;
- que una simulación represente fielmente una futura IA avanzada;
- que el alineamiento sea un problema resuelto;
- que los intereses humanos puedan reducirse a una única función de recompensa.

El dominio inicial es acotado: tareas sintéticas, restricciones explícitas, perturbaciones y transformaciones recursivas controladas.

## 4. Modelo conceptual

\[
\mathcal{S}(t)=\{H(t),A(t),R(t),E(t)\}
\]

La asimetría se representa por un vector de diferencias de desempeño:

\[
\Delta_C(t)=\mathbf{C}_A(t)-\mathbf{C}_H(t)
\]

La compatibilidad se representa inicialmente como vector:

\[
\mathbf{K}(t)=[K_I(t),K_D(t),K_A(t),K_T(t),K_R(t)]
\]

- \(K_I\): compatibilidad con intereses humanos especificados;
- \(K_D\): cumplimiento de restricciones de dignidad y derechos modeladas;
- \(K_A\): preservación de autonomía y oportunidades humanas;
- \(K_T\): estabilidad temporal;
- \(K_R\): robustez ante perturbaciones y transformaciones.

Los componentes no son intercambiables. Algunas restricciones deben evaluarse como condiciones de veto y no como términos compensables de una suma ponderada.

### 4.1 Compatibilidad a través del tiempo

\[
\mathcal{K}_{0:T}=\{\mathbf{K}(t):t\in[0,T]\}
\]

La pregunta central es si las restricciones relevantes se mantienen durante el proceso, incluidas las transiciones entre versiones del agente.

### 4.2 Transformación recursiva

Sea \(A_{n+1}=\Phi(A_n,\xi_n)\), donde \(\Phi\) representa una modificación interna y \(\xi_n\) las condiciones de actualización. La compatibilidad debe evaluarse antes y después de cada transformación y bajo perturbaciones.

Esta expresión es un esquema conceptual. La implementación deberá definir qué componentes pueden modificarse y cuáles permanecen fuera del proceso de actualización.

## 5. Variables

| Variable | Tipo | Operacionalización inicial |
|---|---|---|
| Asimetría \(\Delta_C\) | Independiente | Diferencia de desempeño en tareas preregistradas |
| Recursividad \(R_c\) | Independiente | Número y tipo de modificaciones internas |
| Supervisión directa \(S_d\) | Independiente | Frecuencia de intervención humana simulada |
| Mecanismo \(M_k\) | Independiente | Restricciones y procedimientos activos |
| Compatibilidad \(K_b\) | Dependiente | Proporción de decisiones que cumplen restricciones |
| Deriva \(D_g\) | Dependiente | Cambio respecto a línea base |
| Robustez \(R_b\) | Dependiente | Persistencia bajo perturbaciones |
| Continuidad \(C_h\) | Dependiente | Preservación de capacidades y oportunidades modeladas |

Controles: complejidad de tarea, presupuesto computacional, distribución de entrenamiento, semillas, dificultad de perturbación y horizonte temporal.

## 6. Predicciones

**P1 — Asimetría no implica incompatibilidad automática.** En tareas sintéticas, un agente de mayor capacidad puede mantener restricciones compatibles sin compartir la arquitectura cognitiva del agente humano modelado.

**P2 — La recursividad introduce riesgo de deriva.** Sin mecanismos de evaluación y protección, algunas modificaciones sucesivas pueden degradar el cumplimiento de restricciones.

**P3 — Las restricciones verificables pueden mejorar la robustez.** Mecanismos independientes de la explicación interna podrían reducir ciertos fallos, sin presuponer que los eliminen todos.

**P4 — La supervisión directa no será el único factor explicativo.** En determinados escenarios, la calidad de las restricciones y pruebas externas podría explicar más variación que la frecuencia de intervención humana.

**P5 — La compatibilidad debe evaluarse bajo cambio.** El rendimiento inicial no predice necesariamente el mantenimiento de restricciones después de modificaciones.

## 7. Diseño experimental

### 7.1 Escenarios

| ID | Asimetría | Recursividad | Supervisión directa | Mecanismos |
|---|---|---|---|---|
| S01 | Baja | No | Alta | Línea base |
| S02 | Alta | No | Alta | Control de asimetría |
| S03 | Alta | Sí | Alta | Efecto recursivo |
| S04 | Alta | Sí | Baja/ausente | Compatibilidad sin supervisión directa |
| S05 | Alta | Sí | Baja/ausente | Restricciones y auditoría externa |
| S06 | Alta | Sí | Variable | Ablación de mecanismos |

### 7.2 Protocolo

1. Definir tareas, restricciones y población humana simulada.
2. Separar datos de entrenamiento, validación y prueba.
3. Establecer métricas y umbrales antes de ejecutar.
4. Ejecutar escenarios con múltiples semillas.
5. Introducir modificaciones internas controladas.
6. Aplicar perturbaciones y cambios de distribución.
7. Registrar violaciones y resultados negativos.
8. Comparar controles y ablaciones.
9. Repetir con configuraciones independientes.

### 7.3 Controles

- Agente no recursivo.
- Agente sin mecanismo de compatibilidad.
- Agente con objetivos fijos.
- Agente con restricciones externas.
- Agente con auditoría posterior.
- Escenario de distribución no vista.

## 8. Controles y análisis

El análisis deberá especificar previamente:

- unidad de análisis;
- número de semillas y justificación;
- variables primarias y secundarias;
- intervalos de incertidumbre;
- tratamiento de datos faltantes;
- corrección por comparaciones múltiples cuando corresponda;
- análisis de sensibilidad;
- criterios de exclusión;
- condiciones de replicación.

No se fija un tamaño muestral ni un umbral universal en esta versión. Deberán derivarse del diseño, la variabilidad estimada y el efecto mínimo de interés antes del experimento confirmatorio.

## 9. Criterios de falsación

H08 se rechazará para el dominio experimental predefinido si se observa de forma robusta cualquiera de estas condiciones:

1. Los mecanismos no preservan las restricciones primarias bajo asimetría elevada.
2. La compatibilidad se degrada sistemáticamente tras transformaciones recursivas.
3. Los mecanismos funcionan solo en distribuciones conocidas y fallan fuera de distribución.
4. Las métricas pueden optimizarse mientras las restricciones sustantivas se incumplen.
5. Los resultados desaparecen en replicaciones independientes.
6. Los daños a subgrupos quedan ocultos por promedios agregados.

Un resultado negativo no demuestra que toda coexistencia sea imposible. Delimita el alcance de los mecanismos y condiciones estudiados.

## 10. Limitaciones

- Los agentes sintéticos no son superinteligencias.
- La capacidad en benchmarks no equivale a inteligencia general.
- Las preferencias codificadas no representan toda la pluralidad humana.
- Las restricciones formalizadas pueden omitir daños no anticipados.
- La opacidad de un modelo simulado no reproduce necesariamente la de sistemas reales.
- La robustez en un entorno no garantiza robustez en otro.

## 11. Relación con H09

H08 plantea la posibilidad general de complementariedad evolutiva asimétrica. H09 estudiará con mayor precisión la estabilidad de la relación después de cambios recursivos sucesivos.

H08 es la hipótesis marco; H09 es una hipótesis más específica sobre persistencia y recuperación de compatibilidad bajo transformación.

---

[Volver al README](../README.md)
