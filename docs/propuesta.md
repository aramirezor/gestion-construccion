# Plataforma de Gestión de Construcción

## Integrantes

- Andrés José Ramírez Ortega
- María José Hernández López
- Braulio Rivera Espinoza
- Valery Carvajal


## Repositorio del Proyecto

**URL:** https://github.com/aramirezor/gestion-construccion

**Descripción:**  
Sistema de gestión de construcción diseñado para centralizar información de obra, mejorar la comunicación entre equipos y facilitar el seguimiento de avances y costos.


# 1. Introducción

La gestión de proyectos de construcción implica coordinar a múltiples actores, recursos y procesos. En muchas organizaciones, la información referente a avances de obra, materiales, compras, tareas y cronogramas está dispersa entre hojas de cálculo, aplicaciones de mensajería, correos electrónicos y documentos compartidos.

Esta dispersión dificulta la trazabilidad, genera duplicidades y limita la capacidad de monitorear el estado real de los proyectos.

Esta propuesta plantea analizar y diseñar una plataforma orientada a centralizar la información operativa y administrativa de proyectos de construcción, facilitando la coordinación entre personal de campo y oficina.


# 2. Problema

Actualmente, muchas empresas constructoras gestionan sus proyectos utilizando múltiples herramientas independientes para registrar avances, coordinar actividades, administrar materiales y controlar costos.

La falta de una plataforma centralizada provoca problemas como:

- Duplicidad de información.
- Pérdida de trazabilidad de decisiones.
- Dificultad para monitorear el progreso real de los proyectos.
- Retrasos en la comunicación entre equipos.
- Limitada visibilidad sobre materiales, compras y costos.

Como resultado, los responsables de los proyectos deben invertir tiempo adicional consolidando información proveniente de diversas fuentes antes de poder tomar decisiones.


# 3. Contexto del Dominio

La propuesta nace a partir de una observación directa de un proyecto de construcción residencial en ejecución.

Durante el seguimiento periódico, se ha detectado que gran parte de la información se comparte mediante fotografías, mensajería, documentos y reportes manuales, lo que dificulta centralizar y consultar históricamente los datos.

El sistema está orientado a pequeñas y medianas empresas constructoras que gestionan varios proyectos simultáneamente y requieren una mejor coordinación entre personal de campo y oficina.


# 4. Acceso al Dominio

El equipo dispone de acceso al dominio mediante un proyecto de construcción residencial en curso.

Existe comunicación periódica con la empresa constructora responsable, lo que facilita entender los procesos de planificación, ejecución y monitoreo.

Este acceso permitirá validar requerimientos y obtener retroalimentación durante las distintas fases del análisis y diseño.


# 5. Supuestos del Dominio

Para efectos del análisis y diseño se considerará el siguiente escenario de referencia:

- La empresa administra entre 10 y 15 proyectos simultáneamente.
- Aproximadamente 4 arquitectos o ingenieros supervisan las obras.
- Cada profesional puede participar en hasta 4 proyectos al mismo tiempo.
- Existen usuarios tanto en campo como en oficina.
- Los encargados de obra realizan actualizaciones frecuentes sobre avances y tareas.
- La conectividad a Internet puede ser limitada o intermitente en algunos sitios de construcción.
- Parte de la información actualmente se gestiona mediante hojas de cálculo, aplicaciones de mensajería y documentos compartidos.

Estos supuestos servirán como base para la toma de decisiones de diseño durante el desarrollo del proyecto.


# 6. Usuarios Principales

## Arquitecto o Ingeniero Responsable

- Supervisa el avance técnico de los proyectos.
- Registra información de obra.
- Coordina actividades con otros participantes.

## Encargado de Obra

- Coordina la ejecución diaria de actividades.
- Reporta avances.
- Comunica incidencias operativas.

## Administrador de Proyecto

- Monitorea el estado general de los proyectos.
- Analiza costos.
- Revisa cronogramas.
- Da seguimiento a indicadores de desempeño.


# 7. Objetivo General

Diseñar una plataforma de gestión de construcción que permita centralizar la información relacionada con proyectos de obra, facilitando el seguimiento de actividades, materiales, compras, avances, cronogramas y costos.


# 8. Funcionalidades Propuestas

## Gestión de Materiales

- Registro de inventario.
- Control de entradas y salidas.
- Seguimiento del consumo de materiales.
- Alertas de escasez.

## Gestión de Compras

- Solicitudes de compra.
- Registro de cotizaciones.
- Seguimiento de órdenes de compra.
- Administración de proveedores.

## Avances de Obra

- Registro de avances diarios o semanales.
- Asociación de fotografías a actividades específicas.
- Seguimiento del progreso del proyecto.

## Gestión de Tareas

- Asignación de actividades.
- Definición de responsables.
- Seguimiento del estado de ejecución.
- Control de fechas límite.

## Cronogramas

- Planificación de actividades.
- Gestión de hitos.
- Dependencias entre tareas.
- Alertas por retrasos.

## Monitoreo de Costos

- Seguimiento presupuestario.
- Registro de gastos.
- Identificación de desviaciones y sobrecostos.

## Reportes e Indicadores

- Reportes personalizados.
- Panel de control con indicadores de desempeño.
- Visualización del estado general de los proyectos.


# 9. Exclusiones del Alcance

Para mantener un alcance adecuado para el proyecto, se establecen las siguientes exclusiones:

- Gestión de planillas y recursos humanos.
- Modelado BIM.
- Diseño o edición de planos.
- Cálculos estructurales.
- Gestión de licitaciones.
- Facturación electrónica.
- Integraciones con sistemas ERP externos.
- Control de maquinaria pesada.
- Gestión documental avanzada de planos técnicos.

Estas funcionalidades podrán considerarse como posibles extensiones futuras del sistema.


# 10. Complejidad y Desafío de Diseño

El principal reto de diseño identificado corresponde al trabajo en entornos con conectividad limitada o intermitente.

Los arquitectos, ingenieros y encargados de obra realizan gran parte de sus actividades directamente en el sitio de construcción, donde el acceso a Internet no siempre es estable.

Por esta razón, uno de los aspectos más relevantes del análisis consiste en estudiar mecanismos que permitan registrar información aun cuando no exista conectividad inmediata.

### Desafíos principales

- Almacenamiento temporal de información.
- Sincronización de datos entre dispositivos y servidores.
- Resolución de conflictos cuando múltiples usuarios modifican la misma información.
- Consistencia de los datos.
- Manejo eficiente de fotografías y evidencia visual del avance de obra.

La resolución de estos problemas representa el principal desafío arquitectónico del proyecto y constituye el eje central del análisis de diseño.


# 11. Beneficios Esperados

- Centralización de la información del proyecto.
- Reducción de errores y duplicidad de registros.
- Mejor seguimiento de avances de obra.
- Mayor visibilidad sobre materiales y costos.
- Comunicación más eficiente entre equipos.
- Mayor capacidad de monitoreo y toma de decisiones.
- Mejor trazabilidad de las actividades realizadas.


# 12. Conclusión

La Plataforma de Gestión de Construcción busca abordar problemas reales asociados a la coordinación y administración de proyectos de obra mediante una solución centralizada orientada a mejorar la gestión de información.

Más allá de las funcionalidades propuestas, el valor académico del proyecto se encuentra en el análisis de los desafíos arquitectónicos asociados al trabajo en campo, especialmente aquellos relacionados con la operación offline, la sincronización de información y el mantenimiento de la consistencia de los datos en entornos distribuidos.
