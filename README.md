# Optimización de la asignación de operadores en ventanilla virtual mediante simulación evento a evento

Proyecto de simulación discreta orientada a eventos desarrollado para analizar y optimizar la distribución de operadores en la Ventanilla Virtual de una universidad.

El objetivo principal fue encontrar una configuración eficiente de recursos humanos que permitiera reducir tiempos de espera, mejorar los tiempos de respuesta y maximizar la utilización de operadores sin incrementar el presupuesto operativo.

---

# Descripción del problema

La Ventanilla Virtual centraliza consultas estudiantiles relacionadas con:

- Inscripciones
- SIU Guaraní
- Ingreso
- Trámites académicos
- Reclamos
- Cambios de curso

Las solicitudes son clasificadas automáticamente y derivadas a dos departamentos:

- Gestión Académica (GA)
- Dirección de Alumnos (A)

Cada departamento administra:

- su propia cola de tickets,
- sus operadores,
- y sus tiempos de atención.

El desafío consistió en determinar la cantidad óptima de operadores para cada sector con el fin de:

- Minimizar tiempos de espera
- Reducir tiempos de respuesta
- Evitar sobrecarga operativa
- Disminuir tiempos ociosos
- Mantener los costos actuales

---

# Objetivos

- Modelar el comportamiento real del sistema mediante simulación evento a evento
- Analizar el flujo de tickets y utilización de operadores
- Evaluar distintos escenarios de asignación de recursos
- Comparar métricas de rendimiento entre configuraciones
- Determinar la configuración más eficiente

---

# Metodología

Se implementó un modelo de simulación discreta basado en eventos.

La simulación representa la evolución temporal del sistema a partir de:

- Llegadas de tickets
- Inicio de atención
- Finalización de atención

Cada evento modifica el estado del sistema y actualiza métricas operativas.

---

# Variables del modelo

## Variables exógenas

- IAGA → Intervalos de arribo en Gestión Académica
- IAA → Intervalos de arribo en Alumnos
- TAGA → Tiempo de atención en Gestión Académica
- TAA → Tiempo de atención en Alumnos

## Variables de control

- N → Cantidad de operadores en Gestión Académica
- M → Cantidad de operadores en Alumnos

## Variables de estado

- NGA → Personas en sistema de Gestión Académica
- NA → Personas en sistema de Alumnos

## Variables de resultado

- PRTGA → Promedio de respuesta por ticket en GA
- PRTA → Promedio de respuesta por ticket en A
- PECGA → Promedio de espera en cola en GA
- PECA → Promedio de espera en cola en A
- PTOGA → Porcentaje de tiempo ocioso en GA
- PTOA → Porcentaje de tiempo ocioso en A

---

# Modelado estadístico

A partir de datos históricos reales se ajustaron funciones de distribución de probabilidad para modelar:

- Intervalos de arribo
- Tiempos de atención

## Distribuciones utilizadas

| Variable | Distribución |
|---|---|
| Intervalos de arribo | FoldCauchy |
| Tiempos de atención | Generalized Normal (gennorm) |

## Métodos utilizados

- Método de la inversa
- Método del rechazo

---

# Tabla de Eventos (TEI / TEF)

El sistema fue modelado utilizando:

- Tabla de Eventos Independientes (TEI)
- Tabla de Eventos Futuros (TEF)

## Eventos principales

| Evento | Descripción |
|---|---|
| TPLLGA | Llegada ticket GA |
| TPSGA(i) | Finalización atención GA |
| TPLLA | Llegada ticket A |
| TPSA(i) | Finalización atención A |

---

# Escenarios evaluados

Se simularon distintas configuraciones de operadores:

| Gestión Académica | Alumnos |
|---|---|
| 1 | 1 |
| 1 | 2 |
| 2 | 1 |
| 2 | 2 |
| 3 | 3 |

Cada escenario fue ejecutado durante un cuatrimestre completo:

- 38.400 minutos de simulación

---

# Resultados

## Configuración óptima

La simulación determinó que la mejor configuración fue:

# 1 operador en Gestión Académica + 2 operadores en Alumnos

Esta configuración logró:

- Tiempos de respuesta equilibrados
- Alta utilización de recursos
- Menor tiempo ocioso
- Buena experiencia de usuario
- Sin incremento presupuestario

---

# Métricas obtenidas

| Configuración | PRTGA | PRTA | PECGA | PECA |
|---|---|---|---|---|
| 1GA, 1A | 137.12 min | 8037.84 min | 124.69 min | 8014.11 min |
| 1GA, 2A | 90.89 min | 64.11 min | 78.33 min | 40.39 min |
| 2GA, 1A | 18.58 min | 9149.25 min | 5.97 min | 9125.62 min |
| 2GA, 2A | 18.87 min | 60.69 min | 6.33 min | 37.07 min |
| 3GA, 3A | 17.05 min | 32.19 min | 4.57 min | 8.51 min |

---

# Beneficios obtenidos

## Optimización de recursos

- Mejor distribución de operadores
- Mayor productividad
- Menor tiempo ocioso

## Mejora operativa

- Reducción significativa de tiempos de espera
- Mayor eficiencia en atención
- Mejor balance de carga

## Impacto económico

- No requiere aumentar presupuesto
- Reduce costos operativos indirectos
- Mejora utilización de recursos existentes

---

# Tecnologías y conceptos aplicados

- Simulación Evento a Evento
- Investigación Operativa
- Sistemas de Colas
- Distribuciones de Probabilidad
- Simulación Discreta
- Modelado Estadístico
- Optimización de Recursos

---

# Aprendizajes

Durante el desarrollo del proyecto se trabajó sobre:

- Modelado de sistemas discretos
- Gestión de colas
- Ajuste estadístico de distribuciones
- Simulación basada en eventos
- Evaluación de escenarios
- Optimización operativa
- Análisis cuantitativo de rendimiento

---

# Paper académico

El proyecto fue documentado mediante un paper académico donde se detallan:

- metodología,
- análisis estadístico,
- modelado,
- simulación,
- resultados,
- discusión,
- conclusiones.

---

# Autores

- Ramon Valenzuela
- Jonatan Raijman
- Guido Gelvan
- Matias Feldman

Universidad Tecnológica Nacional - FRBA
