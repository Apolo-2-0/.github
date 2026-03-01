<div align="center">

# 🏗️ **Guía de Contribución Interna** 🏗️

</div>

Este documento establece los estándares profesionales, flujos de trabajo y expectativas para el equipo de desarrollo. A diferencia de proyectos open source, este repositorio es privado y todas las contribuciones provienen de empleados de la empresa.

---

<div align="center">

## Responsabilidades del Desarrollador

</div>

| | Responsabilidad | Detalles |
| :--- | :--- | :--- |
| **Disponibilidad** | Compromiso durante horario laboral | Responder a notificaciones de GitHub durante horario laboral acordado. Comunicar ausencias con anticipación mediante Issues o comentarios en Projects. |
| **Calidad** | Escribir código que cumpla los estándares técnicos | Seguir las reglas de oro, pasar tests antes de solicitar revisión, y no delegar calidad al revisor. |
| **Propiedad** | Responsabilidad sobre código propio | Mantener features propias, responder preguntas sobre código que se escribió, y corregir bugs introducidos. |
| **Revisión** | Revisar código de otros con diligencia | Revisar Pull Requests asignados dentro de 24 horas, comentarios constructivos con sugerencias concretas. |

---

<div align="center">

## Flujo de Trabajo

</div>

| Fase | Proceso | Herramienta |
| :--- | :--- | :--- |
| **Asignación** | Revisar GitHub Projects antes de iniciar trabajo nuevo. Asignarse Issues disponibles o solicitar asignación. | GitHub Projects |
| **Branching** | Crear branch desde `main` con nomenclatura: `feature/[issue-id]-descripcion` o `bugfix/[issue-id]-descripcion` | Git |
| **Desarrollo** | Trabajar en la branch, hacer commits frecuentes con mensajes descriptivos en español. | Local + Push frecuente |
| **Testing** | Ejecutar suite de tests localmente antes de PR. Todos los tests deben pasar. | Framework de tests del proyecto |
| **Pull Request** | Crear PR con descripción clara del cambio, link al Issue, y screenshots si aplica. Usar templates si están disponibles. | GitHub Pull Requests |
| **Revisión** | Mínimo una aprobación de un revisor asignado. Solicitar revisores específicos si es necesario. | GitHub Code Review |
| **Merge** | El autor hace merge después de aprobación. Usar squash merge para mantener historial limpio. | GitHub |

---

<div align="center">

## Estándares Técnicos Obligatorios

</div>

| | Estándar | Aplicación |
| :--- | :--- | :--- |
| **Bilingüismo Estratégico** | Código en inglés técnico (variables, funciones, módulos, base de datos). Documentación en español (README, comentarios de negocio, requerimientos). | Aplica a TODO el código nuevo. Código legacy se migra gradualmente. |
| **Fail-Fast & Safety** | Prohibido `unwrap()` en lógica de negocio. `.expect()` solo en fase de inicialización. Usar `Result` y manejo explícito de errores. | Revisión obligatoria en PRs. |
| **White Label Compliance** | Ningún código atado a marca específica. Cambios visuales mediante sistema de branding. No hardcodear logos, colores de marca, o textos comerciales. | Verificar en cada feature nueva. |
| **Seguridad** | No commitear credenciales, usar variables de entorno, sanitizar logs de datos sensibles. | Revisión de seguridad en cada PR. |
| **Documentación** | Documentar APIs públicas, funciones complejas, y decisiones arquitectónicas significativas. | Actualizar con cada cambio relevante. |

---

<div align="center">

## Código de Conducta Técnico

</div>

| | Práctica Correcta | Práctica Incorrecta |
| :--- | :--- | :--- |
| **Commits** | Mensajes descriptivos en español, un concepto por commit, commits frecuentes. | Mensajes vagos ("fix", "update"), commits masivos con múltiples cambios no relacionados. |
| **PRs** | Descripción clara del cambio, link al Issue, tests incluidos, scope limitado. | PRs de +500 líneas sin justificación, sin tests, o que mezclan múltiples features. |
| **Revisión** | Feedback específico con sugerencias concretas, responder a comentarios, aprender de feedback. | Comentarios vagos ("esto está mal"), no responder a feedback, ignorar sugerencias. |
| **Conflictos** | Resolver merge conflicts rápidamente, comunicar bloqueos en el PR, coordinar con otros desarrolladores. | Ignorar conflicts por días, hacer merge sin resolver, sobrescribir trabajo de otros. |

---

<div align="center">

## Proceso de Incidentes

</div>

| Severidad | Tiempo de Respuesta | Ejemplo | Acción |
| :--- | :--- | :--- | :--- |
| **Crítico (P0)** | Inmediato (dentro de 1 hora) | Servicio caído, datos perdidos, seguridad comprometida | Crear Issue con label `critical`, asignar inmediatamente, hotfix directo |
| **Alto (P1)** | Dentro de 4 horas | Feature principal rota, múltiples usuarios afectados | Crear Issue con label `high-priority`, asignar inmediatamente, PR dentro de 24h |
| **Medio (P2)** | Dentro de 24 horas | Funcionalidad degradada, workaround disponible | Crear Issue con label `medium-priority`, asignar en sprint actual o siguiente |
| **Bajo (P3)** | Dentro de 1 semana | Problema menor, impacto limitado | Crear Issue con label `low-priority`, priorizar en backlog |

---

<div align="center">

## Canales de Comunicación

</div>

| Canal | Uso | Tiempo de Respuesta Esperado |
| :--- | :--- | :--- |
| **GitHub Issues** | Reportar bugs, proponer features, discusiones técnicas detalladas, asignación de tareas | Dentro de 48 horas |
| **GitHub Projects** | Visualización de trabajo, asignación de Issues, seguimiento de progreso | Revisar al inicio de cada jornada |
| **GitHub PR Comments** | Revisión de código, discusión específica de cambios | Dentro de 24 horas |
| **GitHub Discussions** | Preguntas generales, propuestas arquitectónicas, anuncios técnicos | Dentro de 72 horas |
| **GitHub Wiki** | Documentación extendida, guías de proceso, FAQs | Actualizar cuando cambien procesos |

---

<div align="center">

## Criterios de Aprobación

</div>

| Tipo de Cambio | Requisitos de Aprobación | Ejemplos |
| :--- | :--- | :--- |
| **Bug fixes** | Mínimo una aprobación de cualquier revisor | Corrección de errores, mejoras menores |
| **Features nuevas** | Mínimo dos aprobaciones de revisores diferentes | Nuevas funcionalidades, cambios de UX |
| **Cambios arquitectónicos** | Crear Discussion primero, mínimo dos aprobaciones, documentación actualizada | Refactors mayores, nuevas dependencias, cambios de diseño |
| **Hotfixes de producción** | Aprobación posterior al merge (retroactiva) | Fixes urgentes en producción |
| **Cambios de CI/CD** | Mínimo una aprobación, verificar que pase el pipeline | Modificación de workflows, configuración de builds |

---

<div align="center">

## Gestión de Issues

</div>

| | Práctica | Detalles |
| :--- | :--- | :--- |
| **Creación** | Usar templates si están disponibles | Incluir pasos para reproducir, comportamiento esperado vs actual, y screenshots. |
| **Labels** | Aplicar labels apropiados | Usar labels existentes para categorizar: `bug`, `feature`, `enhancement`, `documentation`, `critical`, etc. |
| **Asignación** | Asignarse a uno mismo o asignar a persona específica | No asignar Issues sin consultar primero mediante comentarios. |
| **Cierre** | Cerrar Issue solo cuando el PR mergeado resuelve el problema completamente | Mencionar "Closes #[issue-id]" en el PR para cierre automático. |

---

<div align="center">

## Expectativas Contractuales

</div>

| | Obligación | Consecuencia del Incumplimiento |
| :--- | :--- | :--- |
| **Confidencialidad** | No compartir código, datos de clientes, o información del negocio con terceros. No hacer fork público del repositorio. | Terminación inmediata del contrato y acciones legales. |
| **Propiedad Intelectual** | Todo el código producido pertenece a la empresa. No utilizar código propio previo sin autorización. | Reclamación legal de propiedad. |
| **Horarios** | Cumplir horario laboral acordado. Comunicar ausencias con anticipación mediante Issues o Projects. | Amonestación, descuento de salario, o terminación según severidad. |
| **Calidad** | Entregar código que cumpla los estándares técnicos. No inflar estimaciones. | Revisión de desempeño, plan de mejora, o terminación en casos graves. |

---

<div align="right">

*Este documento aplica exclusivamente a empleados de la empresa y no tiene aplicación para contribuidores externos.*<br>
*Para consultas sobre este documento, crear un Issue con el label `documentation`.*

</div>
