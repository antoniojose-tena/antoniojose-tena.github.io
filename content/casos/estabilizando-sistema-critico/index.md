---
title: "Estabilizar un sistema crítico en producción sin reescrituras"
date: 2026-01-15
tags: ["arquitectura", "sistemas críticos", "legacy"]
---

## Contexto

Aplicación web industrial en producción, utilizada por técnicos de campo para registrar inspecciones reglamentarias en instalaciones sujetas a normativa.

El sistema era la pieza central del proceso operativo:
- registro completo de inspecciones
- trazabilidad de cada instalación y equipo
- emisión de certificaciones oficiales cuando se cumplía la regulación

La disponibilidad y fiabilidad del sistema eran críticas para la operación diaria y el negocio.

---

## Situación inicial

Cuando me incorporé, el sistema se encontraba en un estado muy delicado:

- Caídas frecuentes y aleatorias en producción
- Reinicios constantes que dejaban el sistema fuera de servicio
- Técnicos obligados a registrar inspecciones en papel
- Malestar generalizado entre usuarios finales
- Impacto económico directo en cada parada
- Despliegues frágiles, con alto riesgo de romper funcionalidades existentes
- Ausencia de documentación técnica y de procesos claros
- Dependencia crítica de conocimiento externo ya no disponible internamente

Cualquier cambio, por pequeño que fuera, generaba efectos colaterales inesperados.

### Arquitectura inicial

![Arquitectura inicial del sistema y dependencias críticas](arquitectura-inicial.png)

---

## Mi rol

Asumí el rol de responsable técnico principal del sistema:

- Toma de decisiones técnicas críticas
- Responsabilidad sobre estabilidad, despliegues y continuidad del servicio
- Referente técnico en un entorno de alta presión de negocio

---

## Enfoque inicial (antes de tocar código)

Antes de introducir cambios, el foco fue entender y ordenar:

- Análisis profundo del estado real del sistema
- Identificación de dependencias críticas y flujos principales
- Documentación de arquitectura, procesos y despliegues inexistentes o difusos
- Priorización estricta orientada a negocio

La decisión fue clara:  
**la estabilidad era prioritaria frente a cualquier nueva funcionalidad.**

---

## Decisiones clave

Se tomó una decisión consciente y sostenida en el tiempo:

- No añadir nuevas funcionalidades hasta estabilizar el sistema

Aunque existía presión para seguir desarrollando features, se priorizó:
- reducir incidentes
- recuperar la confianza en el sistema
- evitar seguir construyendo sobre una base inestable

---

## Acciones técnicas

- Definición y documentación de un proceso de despliegue claro y reproducible
- Implantación de planes de despliegue más seguros
- Revisiones de código orientadas a evitar regresiones
- Mejora de los flujos de entrega para eliminar fallos recurrentes
- Reducción progresiva de la dependencia externa mediante extracción de conocimiento y comunicación controlada
- Análisis y optimización de la capa de datos, identificando consultas críticas y ajustando esquema e índices para reducir bloqueos y comportamientos inestables en producción.

---

## Resultado

- Eliminación de las caídas constantes en producción
- Despliegues estables y predecibles
- Recuperación de la operativa normal de los técnicos de campo
- Reducción del riesgo en cambios y entregas
- Recuperación de la confianza del negocio en el sistema

Se estableció una base técnica sólida que permitió, posteriormente, volver a evolucionar el producto con menor riesgo.

---

## Aprendizajes

- La estabilidad no es una mejora: es un prerrequisito
- Muchas veces, la mejor decisión técnica es **no hacer más**, sino hacer menos y mejor
- Estabilizar un sistema es tan valioso como construir uno nuevo
- La arquitectura madura prioriza continuidad, no brillantez

Este tipo de trabajo rara vez es visible, pero suele marcar la diferencia
entre un sistema que sobrevive y uno en el que el negocio puede confiar.