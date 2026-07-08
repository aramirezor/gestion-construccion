PLATAFORMA DE GESTIÓN DE CONSTRUCCIÓN  
Documento de Diseño de Software

PSWE-04 — Diseño de Software

---

Universidad Cenfotec

Maestría Profesional en Ingeniería del Software

| Nombre del sistema | Plataforma de Gestión de Construcción |
| :---- | :---- |
| Grupo | Grupo 4 |
| Integrantes |  Andrés José Ramírez Ortega<br>María José Hernández López<br>Braulio Rivera Espinoza<br>Valery Carvajal Oreamuno |
| URL del repositorio | https://github.com/aramirezor/gestion-construccion.git |
| Docente | Juan Mauricio Leandro |
| Cuatrimestre | 2026 — II Cuatrimestre |
| Versión del documento | 0.4 — Avance 1 |
| Fecha de última actualización | 2026-06-28 |

San José, Costa Rica 2026

Control de Versiones

| Versión | Fecha | Hito | Cambios principales | Autor(es) |
| ----- | ----- | ----- | ----- | ----- |
| 0.1 | 2026-05-26 | Propuesta (S03) | Creación del documento inicial, definición del sistema, alcance, stakeholders y estructura base del documento. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
| 0.2 | 2026-06-21 | Avance 1 (S07) | Incorporación de drivers arquitectónicos, requerimientos funcionales clave, atributos de calidad prioritarios, restricciones, escenarios de calidad, principios de diseño y vista de contexto. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
| 0.3 | 2026-06-28 | Avance 1 (S07) - Correcciones | Profundización del problema arquitectónico central (operación offline, política de conflictos y priorización de sincronización); ampliación de stakeholders (Cliente, Bodega, Proveedores); ajuste técnico de drivers arquitectónicos; redefinición de escenarios de calidad con métricas verificables y adición de escenario de resiliencia para fotografías; optimización de la vista de contexto. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
| 0.4 | 2026-06-28 | Avance 1 (S07) - Ajustes finales | Reestructuración del documento para mantener consistencia con el alcance del avance; fortalecimiento de la lógica y coherencia entre las secciones; refinamiento de la descripción del sistema, drivers arquitectónicos, escenarios de calidad y vista de contexto; eliminación de secciones no desarrolladas y corrección de numeración, formato y redacción general. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
|  |  |  |  |  |

# 

# Documentación del Proyecto

## Tabla de Contenido

1. Descripción del Sistema y Alcance
   - 1.1 Descripción General
   - 1.2 Contexto del Negocio o Dominio
   - 1.3 Alcance del Sistema
   - 1.4 Usuarios y Casos de Uso Principales

2. Stakeholders

3. Drivers Arquitectónicos
   - 3.1 Requerimientos Funcionales Clave
   - 3.2 Atributos de Calidad Prioritarios
   - 3.3 Restricciones que Actúan como Drivers

4. Desafío Arquitectónico Principal

5. Escenarios de Calidad
6. Restricciones

7. Principios de Diseño

8. Vistas Arquitectónicas
   - 8.1  Vista de contexto


# 1\. Descripción del Sistema y Alcance

Este documento presenta el análisis arquitectónico inicial de la **Plataforma de Gestión de Construcción**, desarrollado como parte del proyecto del curso **PSWE-04 Diseño de Sistemas de Software**.

Su propósito es definir el contexto del sistema, los actores involucrados, el alcance, los principales requerimientos y los drivers arquitectónicos que orientarán las decisiones de diseño en las siguientes etapas del proyecto.


## 1.1 Descripción General

La Plataforma de Gestión de Construcción es un sistema diseñado para centralizar la información operativa y administrativa asociada a proyectos de construcción. El sistema permite gestionar materiales, compras, tareas, cronogramas, avances de obra, costos e indicadores de desempeño desde una única plataforma, reduciendo la dependencia de múltiples herramientas aisladas.

La solución está dirigida a pequeñas y medianas empresas constructoras que administran varios proyectos simultáneamente y que actualmente enfrentan dificultades debido a la dispersión de información entre hojas de cálculo, aplicaciones de mensajería, correos electrónicos y documentos compartidos. Esta situación genera duplicidad de información, pérdida de trazabilidad, retrasos en la comunicación y dificultades para monitorear el estado real de los proyectos.

El principal valor del sistema consiste en proporcionar una visión centralizada y consistente de cada proyecto, facilitando la coordinación entre el personal de campo y oficina, mejorando la toma de decisiones y permitiendo un seguimiento más preciso del progreso, los costos y la utilización de los recursos.

Además, la plataforma busca permitir que usuarios ubicados en diferentes entornos de trabajo colaboren sobre la misma información, incluso cuando existan condiciones de conectividad limitada o intermitente.



## 1.2 Contexto del Negocio o Dominio

El sistema opera dentro del dominio de la gestión de proyectos de construcción. En este entorno participan arquitectos, ingenieros, encargados de obra, responsables de compras, personal de bodega y administradores de proyecto, quienes requieren información actualizada para coordinar actividades, controlar recursos y monitorear el avance de las obras.

Actualmente, gran parte de la información es compartida mediante fotografías, mensajería instantánea, reportes manuales y documentos distribuidos. Esta fragmentación dificulta la consulta histórica, la trazabilidad de las decisiones y la consolidación de la información necesaria para la gestión de los proyectos.

El escenario de referencia considera una empresa que administra entre 10 y 15 proyectos simultáneamente, con aproximadamente cuatro arquitectos o ingenieros supervisando múltiples obras. Existen usuarios tanto en campo como en oficina, y los encargados de obra realizan actualizaciones frecuentes sobre tareas, avances y consumo de materiales.

Un aspecto fundamental del dominio es la existencia de sitios de construcción con conectividad limitada o intermitente. Esta condición introduce desafíos relacionados con el registro oportuno de la información y la coordinación entre usuarios distribuidos, aspectos que se desarrollan con mayor detalle en el apartado **4. Desafío Arquitectónico Principal**.



## 1.3 Alcance del Sistema

### Dentro del alcance

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
- Centralización de la información de los proyectos.
- Soporte para operación en entornos con conectividad limitada.

### Fuera del alcance

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

| Tipo de usuario | Casos de uso principales |
| ----- | ----- |
| Arquitectos e Ingenieros | CU1: Registrar avances de obra.<br>CU2: Consultar cronogramas.<br>CU3: Supervisar tareas.<br>CU4: Adjuntar evidencia fotográfica.<br>CU5: Coordinar actividades entre participantes. |
| Encargados de Obra | CU1: Reportar avances diarios.<br>CU2: Actualizar estado de tareas.<br>CU3: Registrar incidencias.<br>CU4: Consultar actividades asignadas.<br>CU5: Solicitar materiales o compras. |
| Administradores de Proyecto | CU1: Monitorear costos y presupuesto.<br>CU2: Analizar indicadores de desempeño.<br>CU3: Gestionar cronogramas.<br>CU4: Supervisar múltiples proyectos.<br>CU5: Detectar desviaciones y sobrecostos. |


## 2\. Stakeholders

| Stakeholder | Rol | Intereses principales | Preocupaciones o restricciones |
| ----- | ----- | ----- | ----- |
| Empresa Constructora | Propietario del negocio y patrocinador del sistema. Define necesidades, objetivos y políticas de operación. | Centralización de información, trazabilidad, monitoreo y control de los proyectos. | Duplicidad de datos, falta de visibilidad y retrasos operativos. |
| Arquitectos e Ingenieros | Supervisores técnicos responsables de la planificación, coordinación y seguimiento de las obras. | Acceso a información actualizada, registro de avances y coordinación entre equipos. | Disponibilidad de datos, trabajo en campo y conectividad limitada. |
| Encargados de Obra | Usuarios operativos que registran avances, incidencias y estado de las actividades en campo. | Registrar avances e incidencias de forma rápida y consultar tareas asignadas. | Conectividad intermitente, facilidad de uso y sincronización de la información. |
| Administradores de Proyecto | Responsables del control global de los proyectos, incluyendo costos, cronogramas e indicadores. | Control presupuestario, seguimiento del progreso y toma de decisiones basada en información confiable. | Precisión, consistencia y disponibilidad de la información consolidada. |
| Encargado de Compras | Responsable de gestionar solicitudes, cotizaciones y órdenes de compra para abastecer los proyectos. | Dar seguimiento a las compras y garantizar el suministro oportuno de materiales. | Retrasos en el abastecimiento e información desactualizada sobre requerimientos. |
| Encargado de Bodega / Materiales | Responsable del inventario y distribución de materiales para las obras. | Registro exacto de entradas, salidas y consumo de materiales. | Diferencias de inventario ocasionadas por demoras en la sincronización o registros incompletos. |
| Proveedores de Materiales | Empresas externas encargadas del suministro de materiales y servicios. | Recibir solicitudes claras y oportunas, así como conocer el estado de las órdenes de compra. | Cambios de última hora, información incompleta y tiempos de entrega. |
| Cliente / Propietario del Proyecto | Persona o empresa que contrata la construcción y recibe el resultado final. | Conocer el estado real del proyecto, el avance de la obra y el uso del presupuesto. | Transparencia, cumplimiento de plazos y exactitud de los reportes. |
| Equipo de Desarrollo | Diseña, implementa y mantiene la plataforma tecnológica. | Construir una solución mantenible, escalable y alineada con las necesidades del negocio. | Complejidad de sincronización de datos, operación offline y evolución futura del sistema. |



## 3\. Drivers arquitectónicos

### 3.1 Requerimientos funcionales clave

| ID | Requerimiento | Stakeholder | ¿Por qué es un driver arquitectónico? |
| ----- | ----- | ----- | ----- |
| RF-01 | Centralizar la información de materiales, compras, cronogramas, tareas, costos y avances de todos los proyectos en una única plataforma. | Empresa Constructora | Requiere definir una arquitectura que garantice la consistencia, disponibilidad y organización de la información compartida. |
| RF-02 | Permitir que usuarios de campo registren información aun cuando exista conectividad limitada o intermitente. | Encargados de Obra, Arquitectos e Ingenieros | Obliga a implementar mecanismos de operación offline, almacenamiento temporal y sincronización posterior. |
| RF-03 | Sincronizar la información registrada por usuarios de campo y oficina manteniendo la consistencia de los datos. | Todos los usuarios operativos | Requiere definir estrategias de sincronización, resolución de conflictos y control de versiones de la información. |
| RF-04 | Gestionar evidencia fotográfica asociada a actividades y avances de obra. | Arquitectos e Ingenieros | Requiere decisiones sobre almacenamiento, transferencia y sincronización eficiente de archivos multimedia. |
| RF-05 | Controlar el acceso a la información según el rol de cada usuario. | Empresa Constructora, Administradores de Proyecto | Obliga a definir mecanismos de autenticación, autorización y control de permisos. |
| RF-06 | Proporcionar reportes e indicadores actualizados para apoyar la toma de decisiones. | Administradores de Proyecto | Requiere consolidar información proveniente de múltiples módulos y garantizar la disponibilidad de datos confiables. |

### 3.2 Atributos de calidad prioritarios 

| ID | Atributo | Importancia | Stakeholder | Justificación |
| ----- | ----- | ----- | ----- | ----- |
| QA-01 | Disponibilidad | Alta | Encargados de Obra, Arquitectos e Ingenieros | Los usuarios deben poder consultar y registrar información incluso cuando la conectividad sea limitada o intermitente. |
| QA-02 | Consistencia | Alta | Empresa Constructora, Administradores de Proyecto | La información debe mantenerse consistente entre usuarios de campo y oficina, aun cuando existan sincronizaciones posteriores. |
| QA-03 | Trazabilidad | Alta | Empresa Constructora, Administradores de Proyecto | El sistema debe conservar un historial de cambios, avances y decisiones para facilitar auditorías y seguimiento de proyectos. |
| QA-04 | Seguridad | Alta | Todos los stakeholders | La información debe estar protegida mediante autenticación, autorización y control de acceso basado en roles. |
| QA-05 | Mantenibilidad | Media | Equipo de Desarrollo | La solución debe facilitar la incorporación de nuevas funcionalidades y el mantenimiento del sistema sin afectar los componentes existentes. |
| QA-06 | Escalabilidad | Alta | Empresa Constructora | La plataforma debe soportar el crecimiento en el número de proyectos, usuarios y registros sin degradar significativamente su rendimiento. |

### 3.3 Restricciones que actúan como drivers 

Las siguientes restricciones no son negociables y condicionan directamente las decisiones arquitectónicas del sistema.

| ID | Restricción | Tipo | Impacto en el diseño |
| ----- | ----- | ----- | ----- |
| REST-01 | La empresa administra simultáneamente entre 10 y 15 proyectos de construcción. | Negocio | Requiere una arquitectura que permita organizar y gestionar múltiples proyectos sin afectar el rendimiento ni la disponibilidad de la información. |
| REST-02 | Existen usuarios distribuidos entre oficinas y distintos sitios de construcción trabajando sobre la misma información. | Negocio | Obliga a definir mecanismos de sincronización, consistencia de datos y resolución de conflictos cuando varios usuarios realizan cambios concurrentes. |
| REST-03 | La conectividad a Internet en los sitios de construcción puede ser limitada o intermitente. | Técnica | Requiere implementar capacidades de operación offline, almacenamiento temporal y sincronización automática cuando la conexión sea restablecida. |
| REST-04 | El sistema debe almacenar fotografías y evidencia visual del avance de las obras. | Técnica | Condiciona las decisiones relacionadas con almacenamiento, compresión, transferencia y sincronización eficiente de archivos multimedia. |
| REST-05 | La información debe estar protegida de acuerdo con el rol de cada usuario. | Seguridad | Obliga a implementar mecanismos de autenticación, autorización y control de acceso basado en roles. |
| REST-06 | El sistema será utilizado tanto desde dispositivos móviles en campo como desde equipos de escritorio en oficina. | Técnica | Requiere una arquitectura que facilite el acceso desde diferentes plataformas y garantice una experiencia de uso consistente entre clientes. |



## 4\. Problema Arquitectónico Central

El principal desafío arquitectónico de la Plataforma de Gestión de Construcción consiste en permitir que usuarios de campo y oficina trabajen sobre la misma información, aun cuando existan condiciones de conectividad limitada o intermitente.

Los encargados de obra, arquitectos e ingenieros necesitan registrar avances, incidencias, fotografías y consumo de materiales directamente desde el sitio de construcción. Sin embargo, estos registros no siempre pueden enviarse inmediatamente al sistema central debido a la disponibilidad variable de la red.

Como consecuencia, la arquitectura del sistema debe permitir el almacenamiento temporal de la información, su sincronización cuando exista conectividad y la resolución de posibles conflictos cuando múltiples usuarios modifiquen los mismos datos.

Este problema impacta directamente decisiones relacionadas con:

- Operación offline.
- Sincronización de datos.
- Resolución de conflictos.
- Consistencia de la información.
- Manejo eficiente de archivos multimedia.
- Trazabilidad de cambios realizados por los usuarios.

La resolución de este desafío constituye el principal eje arquitectónico del proyecto y orientará las decisiones de diseño en las siguientes etapas del desarrollo.

 

## 5\. Requerimientos de calidad — Escenarios 

### Escenario QS-01 — Disponibilidad 

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Encargado de Obra |
| **Estímulo** | Registra avances de obra y fotografías sin conexión a Internet |
| **Entorno** | Sitio de construcción con conectividad limitada o intermitente |
| **Artefacto** | Aplicación móvil y almacenamiento local |
| **Respuesta** | El sistema almacena temporalmente la información y permite continuar trabajando normalmente |
| **Medida de respuesta** | El 100% de los registros offline incluidos en la suite de pruebas se almacenan localmente y quedan en cola de sincronización|

*Tensión con:* QS-02 (Consistencia), ya que permitir trabajo offline puede generar versiones divergentes de los datos.



### Escenario QS-02 — Consistencia 

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Arquitecto e Ingeniero Responsable |
| **Estímulo** | Dos usuarios modifican simultáneamente el estado de una misma tarea |
| **Entorno** | Operación normal con usuarios distribuidos entre campo y oficina |
| **Artefacto** | Servicio de gestión de tareas y sincronización |
| **Respuesta** | El sistema detecta el conflicto, marca el registro como "conflicto pendiente" (resolución manual) y conserva la trazabilidad |
| **Medida de respuesta** | Los conflictos definidos en los casos de prueba son detectados y marcados como pendientes |

*Tensión con:* QS-01 (Disponibilidad), porque la sincronización y resolución de conflictos puede retrasar la disponibilidad inmediata de los cambios.



### Escenario QS-03 — Trazabilidad

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Administrador de Proyecto |
| **Estímulo** | Solicita revisar el historial de cambios de una actividad |
| **Entorno** | Operación normal |
| **Artefacto** | Sistema de auditoría y base de datos |
| **Respuesta** | El sistema muestra quién realizó cada modificación, cuándo ocurrió y cuál fue el cambio realizado |
| **Medida de respuesta** | El historial completo de cambios se recupera en menos de 3 segundos para el 95% de las consultas |

*Tensión con:* QS-04 (Rendimiento/Mantenibilidad), debido al almacenamiento adicional requerido para auditoría.



### Escenario QS-04 — Seguridad

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Usuario no autorizado |
| **Estímulo** | Intenta acceder a información de proyectos para los cuales no posee permisos |
| **Entorno** | Operación normal |
| **Artefacto** | Servicio de autenticación y autorización |
| **Respuesta** | El sistema rechaza el acceso, registra el intento y notifica el evento para auditoría |
| **Medida de respuesta** | Todo acceso a proyectos fuera del rol asignado en la matriz de permisos es rechazado y auditado |

*Tensión con:* QS-01 (Disponibilidad), porque los controles de seguridad agregan validaciones adicionales antes de permitir el acceso.



### Escenario QS-05 — Resiliencia en la sincronización de fotografías

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Encargado de Obra |
| **Estímulo** | Intenta sincronizar fotografías pesadas tras recuperar conectividad intermitente|
| **Entorno** | Operación de campo pasando de offline a online |
| **Artefacto** | Módulo de sincronización de archivos |
| **Respuesta** | El sistema transfiere los archivos en segundo plano sin bloquear la interfaz, reanudando descargas fallidas desde el punto de interrupción  |
| **Medida de respuesta** | La subida de fotografías simuladas bajo red inestable se completa exitosamente tras interrupciones, sin corromper el archivo |



## 6\. Restricciones 

| ID | Restricción | Tipo | Origen | Impacto en el diseño |
| ----- | ----- | ----- | ----- | ----- |
| REST-01 | El sistema debe soportar entre 10 y 15 proyectos activos simultáneamente. | Negocio | Empresa Constructora | Requiere una organización eficiente de datos y escalabilidad moderada. |
| REST-02 | Existen usuarios distribuidos entre oficina y campo. | Negocio | Empresa Constructora | Obliga a diseñar mecanismos de sincronización y acceso remoto. |
| REST-03 | Los sitios de construcción pueden presentar conectividad limitada o intermitente. | Técnica | Contexto operativo | Requiere capacidades offline y sincronización diferida. |
| REST-04 | Las fotografías son evidencia obligatoria de avances de obra. | Técnica | Arquitectos e Ingenieros | Impacta el almacenamiento, transferencia y sincronización de archivos. |
| REST-05 | El sistema debe cumplir con la Ley N.º 8968 de Protección de la Persona frente al Tratamiento de sus Datos Personales de Costa Rica. | Regulatoria | Gobierno de Costa Rica | Requiere controles de acceso, auditoría y protección de datos. |
| REST-06 | La solución debe ser accesible mediante navegador web y dispositivos móviles. | Negocio | Empresa Constructora | Condiciona la arquitectura hacia clientes multiplataforma. |


## 7\. Principios de diseño adoptados

| Principio | Justificación para este sistema |
| ----- | ----- |
| Separación de responsabilidades (SoC) | Permite aislar módulos como inventario, compras, cronogramas y gestión de avances, facilitando mantenimiento y evolución. |
| Diseño para el cambio | La empresa puede incorporar nuevas funcionalidades o procesos constructivos en el futuro sin rediseñar toda la solución. |
| DRY (Don't Repeat Yourself) | Evita duplicación de lógica de negocio entre aplicaciones web, móvil y procesos de sincronización. |
| KISS (Keep It Simple, Stupid) | Reduce la complejidad innecesaria en una plataforma utilizada por personal técnico y operativo con diferentes niveles de experiencia. |
| Defensa en profundidad | Protege información sensible mediante autenticación, autorización, auditoría y cifrado de datos. |
| Principio de menor privilegio (PoLA) | Cada usuario accede únicamente a la información y funciones necesarias para su rol. |
| Alta cohesión y bajo acoplamiento | Facilita el mantenimiento de módulos como inventario, compras, costos y cronogramas sin afectar el resto del sistema. |
| Diseño orientado a la resiliencia | Es fundamental debido a los escenarios de conectividad intermitente presentes en las obras de construcción. |


## 8. Vistas arquitectónicas

### 8.1 Vista de contexto

**Figura 1. Vista de contexto de la Plataforma de Gestión de Construcción**

![Diagrama - Vista de Contexto](../diagramas/diagrama_contexto.jpg)

| Elemento | Tipo | Descripción de la relación |
| ----- | ----- | ----- |
| Plataforma de Gestión de Construcción | Sistema principal | Centraliza la información relacionada con materiales, compras, cronogramas, tareas, costos y avances de obra. |
| Arquitectos e Ingenieros | Persona / Rol | Consultan cronogramas, supervisan tareas, registran avances y adjuntan evidencia fotográfica al sistema. |
| Encargado de Obra | Persona / Rol | Reporta avances diarios, incidencias, actualiza tareas y solicita materiales desde los sitios de construcción. |
| Administrador de Proyecto | Persona / Rol | Monitorea costos, indicadores de desempeño, cronogramas y el estado general de múltiples proyectos. |
| Servicio de Correo Electrónico | Sistema externo | Recibe solicitudes de envío de notificaciones y alertas generadas por la plataforma mediante SMTP o API. |
| Almacenamiento de Archivos | Sistema externo | Almacena y proporciona acceso a fotografías y documentos asociados a actividades y avances de obra mediante HTTPS. |
