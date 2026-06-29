PLATAFORMA DE GESTIÓN DE CONSTRUCCIÓN  
Documento de Diseño de Software

PSWE-04 — Diseño de Software

---

Universidad Cenfotec

Maestría Profesional en Ingeniería del Software

| Nombre del sistema | Plataforma de Gestión de Construcción |
| :---- | :---- |
| Grupo | Grupo 4 |
| Integrantes | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal |
| URL del repositorio | https://github.com/aramirezor/gestion-construccion.git |
| Docente | Juan Mauricio Leandro |
| Cuatrimestre | 2026 — II Cuatrimestre |
| Versión del documento | 0.2 — Avance 1 |
| Fecha de última actualización | 2026-06-21 |

San José, Costa Rica 2026

Control de Versiones

| Versión | Fecha | Hito | Cambios principales | Autor(es) |
| ----- | ----- | ----- | ----- | ----- |
| 0.1 | 2026-05-26 | Propuesta (S03) | Creación del documento inicial, definición del sistema, alcance, stakeholders y estructura base del documento. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
| 0.2 | 2026-06-21 | Avance 1 (S07) | Incorporación de drivers arquitectónicos, requerimientos funcionales clave, atributos de calidad prioritarios, restricciones, escenarios de calidad, principios de diseño y vista de contexto. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
| 0.3 | 2026-06-28 | Avance 1 (S07) - Correcciones | Profundización del problema arquitectónico central (operación offline, política de conflictos y priorización de sincronización); ampliación de stakeholders (Cliente, Bodega, Proveedores); ajuste técnico de drivers arquitectónicos; redefinición de escenarios de calidad con métricas verificables y adición de escenario de resiliencia para fotografías; optimización de la vista de contexto. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal Oreamuno |
|  |  |  |  |  |

# 

## 

[1\. Descripción del sistema y alcance	5](#1.-descripción-del-sistema-y-alcance)

[1.1 Descripción general	5](#1.1-descripción-general)

[1.2 Contexto del negocio o dominio	5](#1.2-contexto-del-negocio-o-dominio)

[1.3 Alcance del sistema	6](#1.3-alcance-del-sistema)

[1.4 Usuarios y casos de uso principales	6](#1.4-usuarios-y-casos-de-uso-principales)

[2\. Stakeholders	8](#2.-stakeholders)

[3\. Drivers arquitectónicos	10](#3.-drivers-arquitectónicos)

[3.1 Requerimientos funcionales clave	10](#3.1-requerimientos-funcionales-clave)

[3.2 Atributos de calidad prioritarios	11](#3.2-atributos-de-calidad-prioritarios)

[3.3 Restricciones que actúan como drivers	12](#3.3-restricciones-que-actúan-como-drivers)

[4\. Requerimientos de calidad — Escenarios	13](#4.-requerimientos-de-calidad-—-escenarios)

[Escenario QS-01 — Disponibilidad	13](#escenario-qs-01-—-disponibilidad)

[Escenario QS-02 — Consistencia	13](#escenario-qs-02-—-consistencia)

[Escenario QS-03 — Trazabilidad	14](#escenario-qs-03-—-trazabilidad)

[Escenario QS-04 — Seguridad	14](#escenario-qs-04-—-seguridad)

[5\. Restricciones	16](#5.-restricciones)

[6\. Principios de diseño adoptados	17](#6.-principios-de-diseño-adoptados)

[7\. Vistas arquitectónicas	18](#7.-vistas-arquitectónicas)

[7.1 Vista de contexto	18](#7.1-vista-de-contexto)

[Figura 1 — Vista de contexto de la Plataforma de Gestión de Construcción	18](#figura-1-—-vista-de-contexto-de-la-plataforma-de-gestión-de-construcción)

## 

## 1\. Descripción del sistema y alcance {#1.-descripción-del-sistema-y-alcance}

### 1.1 Descripción general {#1.1-descripción-general}

La Plataforma de Gestión de Construcción es un sistema diseñado para centralizar la información operativa y administrativa asociada a proyectos de construcción. El sistema permite gestionar materiales, compras, tareas, cronogramas, avances de obra, costos e indicadores de desempeño desde una única plataforma, reduciendo la dependencia de múltiples herramientas aisladas.

La solución está dirigida a pequeñas y medianas empresas constructoras que administran varios proyectos simultáneamente y que actualmente enfrentan dificultades debido a la dispersión de información entre hojas de cálculo, aplicaciones de mensajería, correos electrónicos y documentos compartidos. Esta situación genera duplicidad de información, pérdida de trazabilidad, retrasos en la comunicación y dificultades para monitorear el estado real de los proyectos.

El valor principal del sistema consiste en proporcionar una visión centralizada y consistente de cada proyecto, facilitando la coordinación entre personal de campo y oficina, mejorando la toma de decisiones y permitiendo un seguimiento más preciso del progreso, costos y utilización de recursos.

### 1.2 Contexto del negocio o dominio {#1.2-contexto-del-negocio-o-dominio}

El sistema opera dentro del dominio de gestión de proyectos de construcción. En este entorno participan arquitectos, ingenieros, encargados de obra y administradores de proyecto que requieren información actualizada para coordinar actividades, controlar recursos y monitorear el avance de las obras.

Actualmente, gran parte de la información es compartida mediante fotografías, mensajería instantánea, reportes manuales y documentos distribuidos. Esta fragmentación dificulta la consulta histórica, la trazabilidad de decisiones y la consolidación de información necesaria para la gestión de proyectos.

El escenario de referencia considera una empresa que administra entre 10 y 15 proyectos simultáneamente, con aproximadamente cuatro arquitectos o ingenieros supervisando múltiples obras. Existen usuarios tanto en campo como en oficina y los encargados de obra realizan actualizaciones frecuentes sobre tareas y avances.

Un aspecto fundamental del dominio es la existencia de sitios de construcción con conectividad limitada o intermitente. Esta condición introduce desafíos relacionados con almacenamiento temporal de información, sincronización de datos, resolución de conflictos y mantenimiento de consistencia entre usuarios distribuidos.

El problema arquitectónico central radica en permitir que usuarios en campo y oficina registren, consulten y modifiquen información bajo condiciones de conectividad desigual, manteniendo consistencia y trazabilidad. Operaciones de campo como reportar avances diarios, registrar incidencias y adjuntar fotografías deben permitirse en modo offline, almacenándose localmente como fuente de verdad temporal.

Por otro lado, operaciones financieras o de aprobación requerirán conexión obligatoria. Para manejar modificaciones concurrentes (ejemplo: dos usuarios editando la misma tarea), el sistema implementará una política inicial de resolución de conflictos basada en el marcado de registros como "conflicto pendiente", requiriendo la intervención manual de un supervisor para la fusión final. Asimismo, la sincronización priorizará datos estructurados (texto, estados) antes que archivos pesados (fotografías) para asegurar la agilidad operativa.

### 1.3 Alcance del sistema {#1.3-alcance-del-sistema}

**Dentro del alcance:**

* Registro y gestión de inventario de materiales.  
* Control de entradas, salidas y consumo de materiales.  
* Generación y seguimiento de solicitudes de compra.  
* Registro y seguimiento de cotizaciones y órdenes de compra.  
* Administración de proveedores.  
* Registro de avances diarios o semanales de obra.  
* Asociación de fotografías a actividades específicas.  
* Gestión y seguimiento de tareas.  
* Asignación de responsables.  
* Gestión de cronogramas e hitos.  
* Monitoreo de costos y presupuesto.  
* Generación de reportes personalizados.  
* Visualización de indicadores de desempeño.  
* Centralización de información de proyectos.  
* Soporte para operación en entornos con conectividad limitada.

**Fuera del alcance:**

* Gestión de planillas y recursos humanos.  
* Modelado BIM.  
* Diseño o edición de planos.  
* Cálculos estructurales.  
* Gestión de licitaciones.  
* Facturación electrónica.  
* Integraciones con sistemas ERP externos.  
* Control de maquinaria pesada.  
* Gestión documental avanzada de planos técnicos.


### 1.4 Usuarios y casos de uso principales {#1.4-usuarios-y-casos-de-uso-principales}

| Tipo de usuario | Casos de uso principales |
| ----- | ----- |
| Arquitecto o Ingeniero Responsable | CU1: Registrar avances de obra. CU2: Consultar cronogramas. CU3: Supervisar tareas. CU4: Adjuntar evidencia fotográfica. CU5: Coordinar actividades entre participantes. |
| Encargado de Obra | CU1: Reportar avances diarios. CU2: Actualizar estado de tareas. CU3: Registrar incidencias. CU4: Consultar actividades asignadas. CU5: Solicitar materiales o compras. |
| Administrador de Proyecto | CU1: Monitorear costos y presupuesto. CU2: Analizar indicadores de desempeño. CU3: Gestionar cronogramas. CU4: Supervisar múltiples proyectos. CU5: Detectar desviaciones y sobrecostos. |

---

## 

## 2\. Stakeholders {#2.-stakeholders}

| Stakeholder | Rol | Intereses principales | Preocupaciones o restricciones |
| ----- | ----- | ----- | ----- |
| Empresa Constructora | Propietario del negocio y patrocinador del sistema. Define necesidades, objetivos y políticas de operación.  | Centralización de información, trazabilidad, monitoreo y control. | Duplicidad de datos, falta de visibilidad y retrasos operativos. |
| Arquitectos e Ingenieros | Supervisores técnicos responsables de la planificación, coordinación y seguimiento de las obras.  | Acceso a información actualizada y seguimiento técnico. | Disponibilidad de datos y coordinación entre equipos. |
| Encargados de Obra | Usuarios operativos que registran avances, incidencias y estado de las actividades en campo.  | Registrar avances e incidencias de manera rápida. | Conectividad limitada y facilidad de uso. |
| Administradores de Proyecto | Responsables del control global de los proyectos, incluyendo costos, cronogramas e indicadores.  | Control presupuestario, indicadores y seguimiento global. | Precisión y consistencia de la información. |
| Equipo de Desarrollo | Diseña, implementa y mantiene la plataforma tecnológica.  | Solución mantenible y evolutiva. | Complejidad de sincronización y consistencia de datos. |
| Cliente / Propietario del Proyecto | Inversor. | Conocer el estado real y financiero de la obra. | Transparencia y exactitud de los reportes. |
| Encargado de Bodega / Materiales | Controlador de inventario. | Registro exacto de entradas y salidas. | Desfase de inventario por demoras en sincronización. |
| Proveedores de Materiales | Entidad externa. | Recepción clara de órdenes de compra. | Claridad en los tiempos de entrega. |

---

## 

## 3\. Drivers arquitectónicos {#3.-drivers-arquitectónicos}

### 3.1 Requerimientos funcionales clave {#3.1-requerimientos-funcionales-clave}

| ID | Requerimiento | Stakeholder | Por qué es un driver |
| ----- | ----- | ----- | ----- |
| RF-01 | Centralizar información de materiales, compras, cronogramas, tareas y costos. | Empresa Constructora. | Requiere almacenamiento y sincronización de archivos y manejo de seguridad y roles. |
| RF-02 | Permitir monitoreo de proyectos mediante indicadores y reportes. | Administradores de Proyecto. | Requiere una consolidación eficiente de información y auditoría. |
| RF-03 | Coordinar usuarios de campo y oficina trabajando sobre la misma información. | Todos los usuarios operativos. | Requiere mecanismos para mantener consistencia y resolver conflictos. |
| RF-04 | Registrar información de obra aun cuando exista conectividad limitada o intermitente. | Encargado de Obra. | Requiere almacenamiento temporal y sincronización posterior. |
| RF-05 | Gestionar evidencia fotográfica asociada a actividades. | Arquitectos e Ingenieros. | Requiere almacenamiento y sincronización de archivos. |

### 3.2 Atributos de calidad prioritarios {#3.2-atributos-de-calidad-prioritarios}

| ID | Atributo | Importancia | Stakeholder | Justificación |
| ----- | ----- | ----- | ----- | ----- |
| QA-01 | Disponibilidad | Alta | Encargados de Obra, Arquitectos e Ingenieros  | Los usuarios de obra deben poder continuar registrando información incluso cuando la conectividad sea limitada. |
| QA-02 | Consistencia  | Alta | Administradores de Proyecto, Empresa Constructora  | Múltiples usuarios pueden modificar información relacionada con el mismo proyecto. |
| QA-03 | Trazabilidad  | Alta | Empresa Constructora, Administradores de Proyecto  | El sistema busca eliminar la pérdida de información y mantener historial de actividades y decisiones. |
| QA-04 | Mantenibilidad  | Media | Equipo de Desarrollo  | La plataforma puede evolucionar incorporando nuevas funcionalidades en el futuro. |
| QA-05 | Seguridad  | Alta | Todos los stakeholders  | La información de proyectos debe estar protegida y accesible según responsabilidades de cada usuario. |

### 3.3 Restricciones que actúan como drivers {#3.3-restricciones-que-actúan-como-drivers}

| ID | Restricción | Tipo | Impacto en el diseño |
| ----- | ----- | ----- | ----- |
| REST-01 | Administración simultánea de entre 10 y 15 proyectos. | Negocio | Requiere organización adecuada de datos y capacidad para gestionar múltiples contextos de proyecto. |
| REST-02 | Existencia de usuarios distribuidos entre campo y oficina. | Negocio | Requiere coordinación de cambios y consistencia de información. |
| REST-03 | Conectividad limitada o intermitente en sitios de construcción. | Técnica | Obliga a diseñar mecanismos de operación offline, almacenamiento temporal y sincronización. |
| REST-04 | Uso frecuente de fotografías como evidencia de avance. | Técnica | Condiciona decisiones relacionadas con almacenamiento, transferencia y sincronización de archivos. |

## 

## 4\. Requerimientos de calidad — Escenarios {#4.-requerimientos-de-calidad-—-escenarios}

### Escenario QS-01 — Disponibilidad {#escenario-qs-01-—-disponibilidad}

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Encargado de Obra |
| **Estímulo** | Registra avances de obra y fotografías sin conexión a Internet |
| **Entorno** | Sitio de construcción con conectividad limitada o intermitente |
| **Artefacto** | Aplicación móvil y almacenamiento local |
| **Respuesta** | El sistema almacena temporalmente la información y permite continuar trabajando normalmente |
| **Medida de respuesta** | El 100% de los registros realizados offline se almacenan localmente y quedan disponibles para sincronización posterior |

*Tensión con:* QS-02 (Consistencia), ya que permitir trabajo offline puede generar versiones divergentes de los datos.

---

### Escenario QS-02 — Consistencia {#escenario-qs-02-—-consistencia}

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Arquitecto e Ingeniero Responsable |
| **Estímulo** | Dos usuarios modifican simultáneamente el estado de una misma tarea |
| **Entorno** | Operación normal con usuarios distribuidos entre campo y oficina |
| **Artefacto** | Servicio de gestión de tareas y sincronización |
| **Respuesta** | El sistema detecta el conflicto, aplica reglas de resolución y conserva trazabilidad de los cambios |
| **Medida de respuesta** | El 100% de los conflictos son detectados y resueltos sin pérdida de información |

*Tensión con:* QS-01 (Disponibilidad), porque la sincronización y resolución de conflictos puede retrasar la disponibilidad inmediata de los cambios.

---

### Escenario QS-03 — Trazabilidad {#escenario-qs-03-—-trazabilidad}

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Administrador de Proyecto |
| **Estímulo** | Solicita revisar el historial de cambios de una actividad |
| **Entorno** | Operación normal |
| **Artefacto** | Sistema de auditoría y base de datos |
| **Respuesta** | El sistema muestra quién realizó cada modificación, cuándo ocurrió y cuál fue el cambio realizado |
| **Medida de respuesta** | El historial completo de cambios se recupera en menos de 3 segundos para el 95% de las consultas |

*Tensión con:* QS-04 (Rendimiento/Mantenibilidad), debido al almacenamiento adicional requerido para auditoría.

---

### Escenario QS-04 — Seguridad {#escenario-qs-04-—-seguridad}

| Elemento | Descripción |
| ----- | ----- |
| **Fuente del estímulo** | Usuario no autorizado |
| **Estímulo** | Intenta acceder a información de proyectos para los cuales no posee permisos |
| **Entorno** | Operación normal |
| **Artefacto** | Servicio de autenticación y autorización |
| **Respuesta** | El sistema rechaza el acceso, registra el intento y notifica el evento para auditoría |
| **Medida de respuesta** | El 100% de los accesos no autorizados son bloqueados y registrados en el sistema de auditoría |

*Tensión con:* QS-01 (Disponibilidad), porque los controles de seguridad agregan validaciones adicionales antes de permitir el acceso.

---

## 

## 5\. Restricciones {#5.-restricciones}

| ID | Restricción | Tipo | Origen | Impacto en el diseño |
| ----- | ----- | ----- | ----- | ----- |
| REST-01 | El sistema debe soportar entre 10 y 15 proyectos activos simultáneamente. | Negocio | Empresa Constructora | Requiere una organización eficiente de datos y escalabilidad moderada. |
| REST-02 | Existen usuarios distribuidos entre oficina y campo. | Negocio | Empresa Constructora | Obliga a diseñar mecanismos de sincronización y acceso remoto. |
| REST-03 | Los sitios de construcción pueden presentar conectividad limitada o intermitente. | Técnica | Contexto operativo | Requiere capacidades offline y sincronización diferida. |
| REST-04 | Las fotografías son evidencia obligatoria de avances de obra. | Técnica | Arquitectos e Ingenieros | Impacta el almacenamiento, transferencia y sincronización de archivos. |
| REST-05 | El sistema debe cumplir con la Ley N.º 8968 de Protección de la Persona frente al Tratamiento de sus Datos Personales de Costa Rica. | Regulatoria | Gobierno de Costa Rica | Requiere controles de acceso, auditoría y protección de datos. |
| REST-06 | La solución debe ser accesible mediante navegador web y dispositivos móviles. | Negocio | Empresa Constructora | Condiciona la arquitectura hacia clientes multiplataforma. |

---

## 

## 6\. Principios de diseño adoptados {#6.-principios-de-diseño-adoptados}

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

### 

## 7\. Vistas arquitectónicas {#7.-vistas-arquitectónicas}

### 7.1 Vista de contexto {#7.1-vista-de-contexto}

**Figura 1**

### **![][image1]**

### 

### **Figura 1 — Vista de contexto de la Plataforma de Gestión de Construcción** {#figura-1-—-vista-de-contexto-de-la-plataforma-de-gestión-de-construcción}

| Elemento | Tipo | Descripción de la relación |
| ----- | ----- | ----- |
| Plataforma de Gestión de Construcción | Sistema principal | Centraliza la información relacionada con materiales, compras, cronogramas, tareas, costos y avances de obra. |
| Arquitecto / Ingeniero Responsable | Persona / Rol | Consulta cronogramas, supervisa tareas, registra avances y adjunta evidencia fotográfica al sistema. |
| Encargado de Obra | Persona / Rol | Reporta avances diarios, incidencias, actualiza tareas y solicita materiales desde los sitios de construcción. |
| Administrador de Proyecto | Persona / Rol | Monitorea costos, indicadores de desempeño, cronogramas y el estado general de múltiples proyectos. |
| Servicio de Correo Electrónico | Sistema externo | Recibe solicitudes de envío de notificaciones y alertas generadas por la plataforma mediante SMTP o API. |
| Almacenamiento de Archivos | Sistema externo | Almacena y proporciona acceso a fotografías y documentos asociados a actividades y avances de obra mediante HTTPS. |

![Vista de Contexto](./diagramas/diagrama_contexto.jpg)
