# Avance 1 Proyecto de Diseño de Software

## Introducción

Este documento presenta el primer avance del proyecto **Plataforma de Gestión de Construcción**, desarrollado en el curso **PSWE-04 Diseño de Sistemas de Software**.

El objetivo de este avance es describir el problema identificado, el contexto del dominio, el alcance del sistema, los usuarios involucrados y los principales drivers arquitectónicos que influirán en las decisiones de diseño. Asimismo, se identifican los stakeholders relevantes, los requerimientos funcionales clave, los atributos de calidad prioritarios y las restricciones que condicionan la arquitectura de la solución.

La información presentada servirá como base para las siguientes etapas del proyecto, donde se profundizará en el análisis, diseño arquitectónico, diagramas y decisiones de diseño necesarias para construir una solución que responda a las necesidades del dominio de construcción.


# 1. Descripción del Sistema y Alcance

## 1.1 Descripción General

La **Plataforma de Gestión de Construcción** es un sistema diseñado para centralizar la información operativa y administrativa asociada a proyectos de construcción. El sistema permite gestionar materiales, compras, tareas, cronogramas, avances de obra, costos e indicadores de desempeño desde una única plataforma, reduciendo la dependencia de múltiples herramientas aisladas.

La solución está dirigida a pequeñas y medianas empresas constructoras que administran varios proyectos simultáneamente y que actualmente enfrentan dificultades debido a la dispersión de información entre hojas de cálculo, aplicaciones de mensajería, correos electrónicos y documentos compartidos. Esta situación genera duplicidad de información, pérdida de trazabilidad, retrasos en la comunicación y dificultades para monitorear el estado real de los proyectos.

El valor principal del sistema consiste en proporcionar una visión centralizada y consistente de cada proyecto, facilitando la coordinación entre personal de campo y oficina, mejorando la toma de decisiones y permitiendo un seguimiento más preciso del progreso, costos y utilización de recursos.


## 1.2 Contexto del Negocio o Dominio

El sistema opera dentro del dominio de gestión de proyectos de construcción. En este entorno participan arquitectos, ingenieros, encargados de obra y administradores de proyecto que requieren información actualizada para coordinar actividades, controlar recursos y monitorear el avance de las obras.

Actualmente, gran parte de la información es compartida mediante fotografías, mensajería instantánea, reportes manuales y documentos distribuidos. Esta fragmentación dificulta la consulta histórica, la trazabilidad de decisiones y la consolidación de información necesaria para la gestión de proyectos.

El escenario de referencia considera una empresa que administra entre 10 y 15 proyectos simultáneamente, con aproximadamente cuatro arquitectos o ingenieros supervisando múltiples obras. Existen usuarios tanto en campo como en oficina y los encargados de obra realizan actualizaciones frecuentes sobre tareas y avances.

Un aspecto fundamental del dominio es la existencia de sitios de construcción con conectividad limitada o intermitente. Esta condición introduce desafíos relacionados con almacenamiento temporal de información, sincronización de datos, resolución de conflictos y mantenimiento de consistencia entre usuarios distribuidos.


## 1.3 Alcance del Sistema

### Dentro del Alcance

- Registro y gestión de inventario de materiales.
- Control de entradas, salidas y consumo de materiales.
- Generación y seguimiento de solicitudes de compra.
- Registro y seguimiento de cotizaciones y órdenes de compra.
- Administración de proveedores.
- Registro de avances diarios o semanales de obra.
- Asociación de fotografías a actividades específicas.
- Gestión y seguimiento de tareas.
- Asignación de responsables.
- Gestión de cronogramas e hitos.
- Monitoreo de costos y presupuesto.
- Generación de reportes personalizados.
- Visualización de indicadores de desempeño.
- Centralización de información de proyectos.
- Soporte para operación en entornos con conectividad limitada.

### Fuera del Alcance

- Gestión de planillas y recursos humanos.
- Modelado BIM.
- Diseño o edición de planos.
- Cálculos estructurales.
- Gestión de licitaciones.
- Facturación electrónica.
- Integraciones con sistemas ERP externos.
- Control de maquinaria pesada.
- Gestión documental avanzada de planos técnicos.


## 1.4 Usuarios y Casos de Uso Principales

| Tipo de Usuario | Casos de Uso Principales |
|-----------------|--------------------------|
| **Arquitecto o Ingeniero Responsable** | CU1: Registrar avances de obra.<br>CU2: Consultar cronogramas.<br>CU3: Supervisar tareas.<br>CU4: Adjuntar evidencia fotográfica.<br>CU5: Coordinar actividades entre participantes. |
| **Encargado de Obra** | CU1: Reportar avances diarios.<br>CU2: Actualizar estado de tareas.<br>CU3: Registrar incidencias.<br>CU4: Consultar actividades asignadas.<br>CU5: Solicitar materiales o compras. |
| **Administrador de Proyecto** | CU1: Monitorear costos y presupuesto.<br>CU2: Analizar indicadores de desempeño.<br>CU3: Gestionar cronogramas.<br>CU4: Supervisar múltiples proyectos.<br>CU5: Detectar desviaciones y sobrecostos. |
