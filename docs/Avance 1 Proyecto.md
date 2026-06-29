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
| 0.1 | 2026-05-26 | Propuesta (S03) | Creación del documento inicial, definición del sistema, alcance, stakeholders y estructura base del documento. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal |
| 0.2 | 2026-06-21 | Avance 1 (S07) | Incorporación de drivers arquitectónicos, requerimientos funcionales clave, atributos de calidad prioritarios, restricciones, escenarios de calidad, principios de diseño y vista de contexto. | Andrés José Ramírez Ortega María José Hernández López Braulio Rivera Espinoza Valery Carvajal |
|  |  |  |  |  |
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

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAloAAAEACAIAAADkxE+xAABHaklEQVR4Xu2dd1wU1/r/iS87tqhRFLEgQSkK2E2MNcZoxFii+MvVa0mCPZYYLBE1YsGg2MUarFFU9HqJJbFcgz2J0SiaiNgAUUAErCji/p7vPpdzhzO7K2WBAT7vP/Z1znOec+bs7uz5zDM784yFDgAAACjyWMgGAAAAoOgBOQQAAAAghwAAAICW5fCvv/5atGjRXD1UoKrsAQAAAJgJjcphVFTU+vXro6Ojk/VQgapklP0AAAAAc6BFOTx37tz06dNZCJWQkZpkbwAAACDHaFEO4+PjZSVMh5pIFOUOAAAAQM7QnBxevXpV1sCMBAYGyn0AAACAnKE5OVy2bJksgBmJjo6W+wAAAAA5Q3NyOH/+fFkAVch9AAAAgJwBOQQAAAC0J4fh4eGy+mVk06ZNch8AAAAgZ2hODon79+/LGpgONX377bdyBwAAACBnaFEOfXx8ZBlMh5piYmLkDgAAAEDO0KIcEqR5mzdvvnfv3iM9VKAqhBAAAEAuoVE5JK5du7Z8+fIFeqhAVdkDAAAAMBPalUMAAAAgz4AcAgAAAJBDAAAAAHIIAAAA6CCH+c7ff/9dvnz5unXrrlixQm7LOhYW+EIBACA7aGL1DAoK4itIswp1lMcqUNy9e7dWrVqPHj26fPly48aN5easAzkEAIDsgdUzP7G3t79w4YJkTEhIqFChgru7O1dJ4erXr1+iRIk9e/ZQdffu3VRu2bJlaGgotwo35auwt27d2tLScuPGjVwV9OrVq2zZss7Ozlz19/d3dXWlQvfu3Q1unatibg8ePNDp8we1b9+e4lqxXRqHCmfOnKHt1qhRg7dL9sDAwKpVq+7du/fgwYPivbCbcnrUVLp0aXp3XAUAgDwDcpiflClT5uHDh5Jx1KhRjx8/Xr9+PVdJS6gaHBzMmkSvK1eu3Llzp52dHbcKN2VVsGvXrmfPnpEUSfYdO3akpKSsXbuWqzRmXFwcFZYsWWJw61wVcxs5ciRVPT09ly5dOnjwYLF1GocKDg4OtF1y4+2SnXzonbq5uc2cOVO8F3ZTTo+6v3z5kt4dVwEAIM+QV0+Ql1B89vTpU8lYt25dehUyKQle586dKTh78uSJwVa1HDJquxiBiY2N5QKHfeqtM2JutWrVooK1tXViYuKNGzfE1sU4xIsXLyQ7FSi+5IJwU1bprR06dEiaGwAA5AHyKgnyknHjxs2ZM4fLIiRipUlOf46VJHgMRXVWVlbCGB8fb0wOJ06cGBISorZTTCZZGJZD9dYZMbfq1atToXbt2hRT3rp1S9p6mzZtaLsXL16U7FKB3aTp0cREzAoAAHmGvEqCvOTmzZvVqlV7/PjxiRMnbGxs2Ojp6SmdrlQWHB0dg4KC+B9Enf7cKZWHDRsmCc/du3e58Pvvv1MAp5bD/fv3p6SkbN++XbKrT5YqW8XcBg0aRNUvv/yS5JyM0tYrVqxI2x06dKhpOWQ35fToraWmptI74ioAAOQZ8ioJ8hgSwrJly9rZ2QUGBrKFQj1LS8suXbpwVZKQ06dPu7i4sApSlf+HCwgIkISHxuRCgwYNrK2t1XLYu3fvcuXKubm5SfZu3boZ3Doj5kYFnf5Smnbt2lFcW7x4caXzrl27aLv+/v6m5ZDdlNOjt0ZDiSt3AAAgz5BXSQAyD4W2FGV6eXmRuMptAABQoIAcguxDEaqtrW3Hjh2joqLkNgAAKFBADgEAAADIIQAAAAA5BAAAAHSQQ+0jrrp8+PChh4dHxsYsoE5MAwAAQAA51DrKWx0qVKigaMka6nstAAAACLS+RD7VI1uLEkoZq1y5Mhd69+5dsWJFkUqtffv21atXF4+I4i7KZN8W6XCrwUTbAskeERFBr5wilZosLS2VublXr14tUnInJib26tXL2dn5t99+0+mT10jz5AzdnHwcAAA0hablcMGCBeF6qCC3FRmEkpEOCV1JTU2lV1tbW66SDtHrjRs3RBedyeymBjOLSgh7z5496XXfvn3qJjEUV2vWrKlMN1qnTh1pnpySVDgAAIB2MLAOagSKP06ePMllKqgfUVREIKVJS0vbsWOHeBgTG4mSJUty9eXLl/T6/Plz0UqvcXFxbdu2JRH9/fffhZELr1690ulzyvj4+NSrV0+SQ8luZWWVkpLCOkdNFPCJJuWYOn3wxyMzpUqVkuZJ86EyzwcAADSFduVQPFTIYLXoICRHnAvV6eMzUdbplY9eb926xVWlvEnJvpUFKdG2QLJ369Zt+PDhoikkJMRYbm4bGxtlZnBra2tpnjp9hm6eDwAAaAotymFUVBRFJ7JVpyNjEcx+otQqBwcHjtI+/vjjcuXKXb58me3t2rWrVauWeCYGd5Gym3p4eHAiUzGglFlUINnF85u4iUTOWDLSxMREih3d3NzOnz+v0z8rWJonpyRFhm4AgAbRohxOnTpVHVXo9CERNYlnDwEJTqsNAAAgG2hODknzTAgeNZEiytYiz/79+58+ferl5SU3AAAAyBzaksOVK1deuHBBtqogN9kEAAAA5AANyWFwcPDBgwdlqyHIrcheWQMAACA30IochoeHy6bXkY0uBYuQkBALCwvlDX/Z4N69e7IpI7t37xY3QpgRGvaTTz75z3/+0759e7kNAAC0hybkMC4uztvbW7a+DurCNxgUVtzd3T/77LMePXrIDVnhtalKRU4Z80LDPn/+vF27dseOHZPbAABAe2hCDgMDA7ORiY26UEfZWoiwtrZ+9uxZrVq15IasIN1Eoea1Dtkjl4YFAIBcAmuWRnn58uXVq1d1+nPCnHRGp7/zkg4CKGRUeko3/9Hr6NGjg4ODKT5Ttjo4OOzatWv9+vVSvMgOo0aNWrJkyePHj0eOHKlsJST70qVLk5KSBg8ezFXqzjE6jU/iTeMLu3jlTVMrb5omtnLlSnpTnAcVAAC0AOQwO7x48aJ79+6zZs366aef5DYzsXfvXlEOCQnhQnR0tE6Rm5RRy6Eyj6gUpakzlHK1bt26Dx48oII6GJXsBvOjCsQNowa3zlVOporkpQAATQE5zCYnT55ctGiRh4dHhw4dJk+ebPZMKx999JFFOiS9bGSxEblJGSE5kgJJVWMZSrlaqlQpjkE5plQi2Q3mR9Up0pkq7fzKm6ZWrnIyVSQvBQBoCsNyaJGDCxrF8io3GCGTnnzmUCCt6VogIiJiy5YtTZs2dXFxGTZs2N9//y17ZBpvb+/vvvtOVOfOnTt9+nQqkO6mpKSMGDHif656oXry5Alt0aAcUuvdu3epULFiRZKfoUOHGpRDT09PPik6aNAgtnMvXfrJUmGfM2dOcnIy+XNVjEbjU+BI4yvt/MqbplauOjo6BgUFpaamqqUXAADyC8Oi8vnnn+fwgsbMy1UmPaVnPGWyV74QGRlJy33r1q0dHByGDBkSFhYme7wOJycn8SwnIikpiSSEwrIPP/zQ2tqaBlf4/t/9mm+++WZAQIBBORSpSo1lKOVqfHx8t27dLC0tRaY37qXTp/BW2g3mR9Up0pkq7fzKm6ZWrnIyVSQvBQBoCgOiEhUVRSGIjY2NyJcdGhpavXp1WgfT0tKmTJlSuXLlwMBAafEVZfHKUHnGjBlVq1adNGkSP/2OBh84cKB4SKzwpMEpKqpRo0bHjh3FwxkEtHVlVWxl9erVxYoVU94tMHPmTJr8ypUr2Uenv9nAysqKJiD61q1bl3uxRaD2FG/cxNyMQQEWzerdd98lMcieLmoW5EcFABQyZDmkEIS0RKe/oJELxMWLF7lAB/V37tyhwoEDB4Qg/benSg7Z2LJlSwpuuMxP7KNAR1iUnhQS8SIbGxtbp04d4UBs3br1008/VVrEVoTGsIU2x09vP3r0qLD8r5vCU40JTxNzyxL37t37+uuv33nnHfoQNm7cyFPNBr6+vrlx73xmsLW1LV26NB0WyA0AAFCQkYVh7969bdu25bIoiIfY0TrIV3MkJCRkUg4rVapkkQ5150HEnQNKz1KlSnH4SK/sKejfv/8PP/ygtIitSNd0lC1blqJPnT7ZN1uUE1B6qjHhaWJu2YMCx3HjxjVr1szV1XXbtm2RkZGyBwAAgDwkgzDcvn3b2tqa5USnV0FpmX7vvffIhwqnTp1iqRCCcfXqVaVF2Gm55y4CCowePXokqsKzSZMmIgJTXl9jMNGXtBVRbt26Nd8DEBoayhaagPBReqox4WlsbmaEwvHBgwe//fbbnTp1OnLkCD/XEAAAQN6QQRikCxoJvqBR8O9//9vLy+vhw4etWrViqeCny7569er9999XSlSFChUuX75MEhIQEDB37lzSvzlz5tBCT02zZs3auXPn9u3bGzVqpPRctWqVv78/yYCfn1/jxo3FRidMmLBw4UJRZYzJ4ZYtW8aPH0+K2KJFC7bQBGjrND5NQOmpxoSnsbmZnbS0tN9//71Pnz52dnb0rn/99VeOSgEAAOQqGYRBuqBRp4/klCc2dfqkJFZWVtu2bWOp4OwnxYoV+9e//qWUKF9f33LlyllaWtL6Pnny5CpVqri7u8fExFATiQot9+KZ6UrPr7/+ulKlSh4eHso7zSlgku6y0BmXQ2LatGn16tVbu3Yt/7tGw9LWaRM0AclTwoSnsbnlHhSaz549+4MPPiBdDAwMvH79uuwBAADAfBgWhsxgTFTyl5o1a1KAmJiYSDHixIkT5eaCTERExIABA0gdu3bteurUKZH/BQAAQM7JvqRpUw6PHj3arFmzt956a+zYseJP0MIEqeDp06dJEUkXN2/ejGtwAADALGhR0kBmSEhIGDNmTOPGjd999106CBBX/wIAAMgGkMNCwuPHjw8cOECRcYsWLSZNmgR1BACALAE5LGxcvXp1+fLlb7/9dv/+/cXjlgAAAJgGclg4efTo0Y8//jh+/Ph33nnH29sb190AAIBpZDkUF8ikpqbevn37iy++yNiep6iv1lFbQGaIj4/ftm3b4MGDe/XqFRAQkDf3igAAQAFCVhdJbypVqsQFKQ337t27S5QoUbp06dDQUHZYu3ZttWrVRo8ezddzqnNeW6jSbfMgLVu25EHCw8N79OhhbW3t4ODAD7+lLhERERUqVOjSpcuff/7JFjEfzrWNu9SzxJEjRyZOnOjq6jp79uwzZ87Q1yR7AABAkcSoHCYnJ4eFhX355Zc6Q2m4SRo3bNiQ3un/OHDggE7/NAwnJyedoZzXFqp02+pBGBLUN954Q6d3O3r0qE7/hKMmTZqwRWdoPiB73Llzp3///m+//TZ9EdHR0XIzAAAUGQzIoYBkjBNkq9Nwh4SEULlRo0YiZ01iYqJO/5D08uXL6wzlvLZQpdvmQaZPny4GOXnyJMWUtra27ECvnCWHHChGFB3V8wE54cmTJ2PHjqUjmE6dOv3xxx9yMwAAFAEMyCG93rhxo3379nx+kiCFU1+4f/Hixf37948bN46rnJWbAjt+bCypF8shSWCxYsV0irhTWaZB3n33XR5k3bp1dnZ2a9asuXXrlpBDzmT94sWLcuXKiY4G5wNySFpa2tmzZ9u0aePq6jp16lScRwUAFCkMyyETFRXFD+RTp+F2dHQMCgoiwRNP0G3RosXNmzenTJnSr18/naGc12o55EH27NnDg5AWbtq0iXTOxcVFyGHbtm0fP37s4+Pj6ekpOvJ8ONc2zweYncjIyJUrV7q7u1PgeOjQIbkZAAAKF6bkUKd/5GGaHikN9+nTp0m0ihcvvnv3bvbcsmWLlZUVLZ0cJqpzXqvlkAfhZ2Lo9I9kcnJyouCShhJyuGLFCrJ07tyZtFl05Plwrm2eD8g91q9f37t375EjR/74448IygEAhRVZDgEwCB2jUNxvb28fHBxM8brcDAAABRzIIcgyjx49IlEkaaTQn2RSbgYAgAII5BBkk6dPn4aEhIwcOZKixm3btiUnJ8seAABQcIAcgpxCovj555/zeVS+EhgAkPfQUamPj48vyAQG81ZCDoE5SUxM/OSTT0gav/zyS3E7KQAgD0hKSkoGmSM8PHzNmjXSBwg5BOYnNjZ2/fr1jRs39vb2vnDhgtwMAMgF5CUfmMTPz0/6ACGHINf55ptvnJ2d3d3dHzx4ILcBAMyEvN4DkyxYsED6ACGHIC9ITU09fPiwvb39oEGDDJ61BwDkEHm9ByaBHIL85MmTJ0FBQY6OjhQvXrx4UW4GAOQAeb0HJoEcAg0xbtw4ihcHDhyIeBGAnCOv98AkkEOgLZ4+fbpz506KF729vf/66y+5GQCQaeT1HpgEcgi0SFRUlK+vr5ub29atW3HnIgDZQ17vgUkgh0DrxMbGLlu2rGPHjuvWrZPbAADGkdd7YBLIISgYnDhxYuTIkWPGjDl37pzcBgAwhLzeA5NADkFBIiAgoHXr1u+///7Tp0/lNgBARuT1Pp3o6GgrK6uSJUtOmzbtwYMHcvPrsLCwkE1GjMbIjHNkZKS1tXWZMmUaN24st+UOkENQILl79+53333n4uKyb98+5H4DwCDyep8OaQwXwsPDq1atymV+hO24ceMSEhKS9Yp14MCBVq1a1ahR486dO+wTExNDrSxmcXFx/fv3d3R0PHbsGPuzj5eXF2ktbSIsLIwtDHUcOnRo9erV16xZI5yljQomTZrk7e0tqi1atOACD962bVsenCdZrVo1UW7Tpk1y+rC0LTGssVkpgRyCAkxqaqq7u3uzZs1WrlwptwFQ5JHX+3QcHBwoQFRaVq9evWjRonv37i1fvpwKyXp18fDwuHLlysCBA318fNhtzpw53JSsV6yAgIClS5eSIgojMXfu3Ht6BgwYwBZm/vz5U6dOpQNZZ2dndlZvVEAzPHnypKiK5Ks8OM2HB+dJ0piiTBOmMg9748YNMayxWSmBHIJCgr+/PwWLP//8s9wAQFFFXu8VHD58ePr06cWLFyedoGrFihUt0ildunSyXl1iY2PZuXXr1vRK4vfhhx9yE72Sm/JEq5BDEZDxOAKKzO7fv0+F27dvs7N6o4KyZcvGx8crLQwPTq/qSUplaVhjs1ICOQSFhxcvXnzwwQfvvfceHkEMgM6kHDIHDx6kOIwK5cqVE1rCWCj+3tuwYQMpH3nu2LFDNFlaWiYmJqr9hfAUK1ZMtCYr5JCCOXZWb1TQqFGjS5cuiWpgYCAXeHBSSh5cOUllWT2ssVkpgRyCwsbJkycHDhy4ePFi5AcHRRx5vU9H/F947969ChUqJOvl5/Lly0ofpbqQlvj6+trY2LD+cVPDhg1jYmLU/jdu3OBCqVKlRCvRtGnTa9euUeHQoUPsrN6owMvLi8RJVNu1a8cFHjwiIoIHNyaH6mGNzUoJ5BAUWuLi4ubNmzd8+HD6bchtABQB5PU+HTpStLW1LVmy5OjRozmQIp0bP3585cqVu3btevXq1eSM6pKsjwXDw8O5zE0kpT169GjcuPGJEyeU/mPHjq1YsWKlSpUuXryY3vu/+Pj4VKtWzc/Pj53VG1USFhZGsl22bNlWrVoJIw/eu3dvHtyYHPKwNGcxrIlZCSCHoJATEBDg4uJC8aLcAEBhR17vgUkghwUSi3S6det29+5duRlk5Pnz55s2berVq9fRo0flNgAKL/J6D0wCOSzYPHz4sEKFCrIVGOfAgQNdunQ5cuSI3ABAoUNe74FJIIcFm0ePHlWuXFmn3+979+7ds2dPEkidPnxct25d+fLlY2Nj2bN79+4knO7u7lz19/d3dXXlEJMtrVu3trS0rFGjBlcFSrudnV1ERMT169epcObMGW7auHEje65evbp+/folSpTgamJiYtmyZZ2dnbmarL+uWsxw9+7d5NmyZcvQ0FB2yDN+/PHH9u3bHzt2TG4AWkKcAlHupcb4z3/+Q9+pbM0utHN+8sknr92o9pHXe2ASyGEB5uXLl9OnTx80aBCVx44de/HixbVr106cOFGnX0oGDhyYlJQ0dOhQdl6yZMnjx4/Xr1/P1ZUrV8bFxf13ID27du169uyZcDBoHzNmDHUMCAiggoODAzdVrVqVPUePHk2bCA4O5qqnp2dKSgpNias0w9TUVDFD0kIaaufOnaSs7JCXvHr1qm3btnRwcPz4cbkNFEDatWtnxuMb2jmfP38uWwsg8noPTAI5LKikpaXt2LFD3EtQqlQpPoguWbKkTi+H/HsWsRpnMhP5zEgPuCDw8fGh+LJevXom7CR+VlZWFCk+efLk/v373GTsIFpsmpFmSGJMgkTB5e+//650y2PoA6EYt2/fvr/++qvcBjQG7TyrV6+m/WrPnj1UjYiIoNfr169zE73yGQvaP8UZC2XH+vXrc0dd+skS/vnwbql05iq/JiYm9urVy9nZ+bffftOlb0KcFOHWsmXLcqsgISGBT8aITfCJE55AcsZzObl3pkRe73MTzo5WoIEcFmzoF8UFa2tr5RPk6ecXHR1NBRsbG7bwz5K+cuEjQUFbSEgIhZim7d26dfvggw+oQHs/NymXEiVi0wzNUFllKFgkfZWteQvFrNu2baPFKH+FGUiwLAnYMnr06ODgYD7S4sx8AQEB3ESvfMZi/fr14oyFGIpPXYhDND5ZMnLkSKWbQGxOpz/JQcedtKPyaX/ppAi3pqSkiD8FmFGjRvHJGN4EDcUnTngC0rmcHJ4poSO5R48eyVY98nqfjvKDtdDfn8CvOWHfvn2ySUHOx88DCowcxsTEBAYGijx7VKAqGWW/IgYdGtPvk2I1Ohr9+OOPmzRpwvfY0c63cOHCcuXKJafrH8kYHdJ26dIlQ3+djg5sudCgQQNSLH9//4ztsv3GjRv8kHpaFLjJwogc0oEzTcDNzY2rNEOqihmePn3axcWFFgI6NM7QLf+g44nvv/++UaNGkZGRcptOt3z5ctkE8haxp3GBDqRIh/hfbbbwGYt69epJ+6TUUZd+mkQ6gSFgN34lH+WpFOmkiNQqKFWqlE6/Fd6ENAGznymh3xTpMX0gtAiQPAt7hsVegYVKnIRFSn7NebpplRB5uhkqi9zZ9Ev38vIqU6aMMrM2HXAUK1aM3v7WrVvF+FLWb+6oTMmdvxQMOTx//vzMmTPluScnk5GaZG+g+PmBrPLw4UN7e3tvb2/JvmbNGskC8hixV3OBjvCGDx/O5yrYwmcsKPCS9n+poy79ZAkt+sJHCbvxq42NDcWCokk6KSK1CmrVqqXTqxFvQpqAdC6HyeGZEpKW7t270wi1a9emz2Tjxo0UMsorZjosTgYtUvJrztMdGxvLebqViNzZs2fPVmfWpg8qKSlpy5YtpIhsSVZl/VZ3zF8Khhwa1EKGmhAjqoEc5gT6kX/11VcUEFPYLYy03Pz5558KL5DXSKJC8ToVaNUWlooVK1KANXToUGn/lzrq0k+W8mVoOv03zgWG3fh11KhR+/fv3759e6NGjXTpm6CdQdlKQSq3Cjw9PflkKW9CmsCwYcMuXLiwatWq1q1bU5W0ISgoiP9B/N8QWYeC0fr161ulQ1GyvFymY5ERtnBTVFQUF1ixGjZsKCwSp06d4oKDg4PInUbHB8n60c6cOcOtyvGl0dQd85cCIIciM5AxpL/NATAX9IPv2rWruEmRT0ZldAEgT4mLi9u1axct3KTEpMGkeR06dJgxY0ZgYODRo0dr6Nm5cyc7y2tlOkL81BYp+bWUp9sg5cuXf21mbX6VRlN3zF8KgBzSMaA864zwNSMA5BKtWrXq27dvWFhYkyZNSBGXLVsmewCQO6Smpl6/fv37778nwRs8eLCtra2zs/PIkSPnz5+/Y8cOcVcxExoaSlpIoaewyGtlOibkUEp+LeXpNoiLi8trM2uL6FA5mrpj/lIA5JC+eHnWKuQ+AJiPFy9erFu3jpahuXPn0nJj8BJZAMwCRUv/+te/lixZ8tVXXzVt2pR2tnfeeYf/ctu/f7+xK0h1+jMZNjY20v0e8kKZjgk5JN0lxSKV4odIfPPNN5s2bSLddXJyYoezZ8+Kp0MwixcvFn8BspsxOeTRKJBlN3XH/AVyWIAJCQnZt2+fbE2HdjLZZAiLbP3LmMnBCwc7d+4cMGAAH5jzvzK9evWSnQDIBPHx8bt37yYZmDBhAqldzZo1W7du7eXltXz5cn7Sgtwhc3z++ee3b9+WrcblEBikAMghTpYaw93dvUePHrI1HenWK2NkTw4zOXhB5+rVq3RgzhJIR68NGjSoXbu2lT4RAe67AK/l2bNntAutW7fO29u7Q4cO9evXd3R0HDZsGIVEW7ZsMShg2YDTERhEXiuBSQqAHOJSGoNERUVZW1vXqlWLCnKbnkzqXCbdJLLXSyP4+Pj4ZoVp06aNHz/e09OzZ8+e77//fqtWrerWrUufvOwHfH3V9w8UKWJiYrZv3z5//vxRo0a5uLjQwdN77703derUVatWhYWFmTjVmRNMfObyWglMUgDkUIcbLVS8fPnSxsaGDjzpWIEKfE+xyBHKCTKEYkkFKXOHQWHr1q0bF8iZE5aq03wYdCA75wqR8m5IG+U0HDTt7KXhyAmzZ8+W9yFgPmiHLKw3aPJVLXTwTYdTn3/+ecOGDd9+++0hQ4bMmDGDdmx64xpMcyp/PcAkBUMOcRu+xN69e+mok8tUCAkJoULNmjWVPsbkkKEjSq6q5TAwMLBv375Ki3AWSFXlaHy1W506dWj5iIuLs7W1Vbt17tzZ3d390KFDoinPmDNnjrwbAbPi5+cnf+gFE9qTg4ODFy1aNG7cuCZNmvD/fHR4t2zZMvoBinTBWkb+boBJCoYcMteuXVu6dOl8PVSgquxRZLC2tqZAkMsUnLEQSjlCJRWMj4/ngpS5Qy2HW7ZsEWVy5oSlxuRQchB2Ke+GwXQhnBBcVPMGyGFuo15TtMnt27dpV587d+7w4cOdnJzouK1Dhw7e3t4U3f7000/KDAwFF/m7ASZR77ry4gg0yHfffaes0k9ap0+QQRop0meUKFGCc21wXtBhw4axFEmZOySdo9BQWSXnxMREdZoPkT5DchBuUt4NaaOchoPCxxym4cgGkMPcRr2maIGEhITz58/TYTQdlvXr169GjRrNmzf/6quvFi9eTL8OOliUOxQK5O8GmES960IOtc7Lly/5uTCCpKQkMoqU2XwC2cPDg9Nzcx79gIAAliJOve3v729QDukY2UIPV8mZ83dLbjS4QQfhJqUUlzbK+buLFy+e9/m7IYe5jXpNyXueP38eHh6+fv36GTNmDBky5O2336YjsA8//JC+/c2bN//yyy9paWlyn8KI/N0Ak6h3XcghKMxADnMb9ZpidmgrYWFhdIQ3ZcqUTz/91MbGxtXVtUePHn5+fjt37pQSkBZljKUbBWro0Fw8DlMAOQSFGchhbpMbcnj79u3Q0FD67jw9PR0cHOzs7Dp16sSXdB4+fFiDl3RqBPoufH1954FMcPz4cfnjgxyCwg3kMLfJuRzSIJcuXVqxYoWXl5eHh0fNmjWbNm3ap0+fxYsX0/F7QkKC3AGA3EETchgUFLQgW1BHeSwAFEAOc5sFr5PDJ0+eXL58OSAgYPLkyf3797e2tia1mzBhAtQOaA1NyCFQQwtNjRo1SpYsaWdnx/fdG0O67MWEMVcxuEWDxrwEcpgl9u3b16ZNG9lqErUc8jOJ/Pz8+JlEfEvDjBkzvv/++yNHjqSmpkr+AGiEfF6tgDH69u2bmJhIQnj//n06rJabCwialUO+nvaNN94oX748J+y3UGX9fy387G83Nze5wXxkZlY8DX5HpUuXlpuzAmkhKaJsNQnJ3vXr1zds2DBz5swhQ4bUr1+fJJCEkGSSRJGkUf5KANAq+bxaAWM4OTmpg8Lu3btXqFDB3d1daWTJIe3s1auXs7MzP/OFjbxEUuHMmTOtW7e2tLRUZ3wNDAysWrXq3r17Dx48SPGouNqK/cmiU4xD9O7du2LFij179uQq2V1dXbmg02+Ie/GG2EiLJvfiO0b4OeC0cIeGhvIguYcJORRlmrDS0q1bt5o1a1Jcvm3bNrYzf/zxBzc1aNBAaqIP38vLy8rKqm3btmFhYdx04MABjrSoXKVKFfqQKTyqVKkSvXfeEA3IG6IB2SJISEioXr06tVqkz4oOiWgQMvIDVAU02tatW5UWe3t7LkhdWDXpY6eJJSsmLzryWyhTpgy/BWLJkiW1a9cuVqyYtAkl6ugQgAIK5FCj/P7777QajhkzRnk1MC1Pjx8/Xr9+vcLxv5Lj6em5Y8cOdQpThpOIPnv2TP1sisGDB5NKUYhDR/ePHj0Sd8qzv7Qt4uLFi6mpqbQhrtKGOALgLaqTmurSM5pSL85ompcpTDMjhyQYSsvChQvv3r0bHR1N2iB8iMaNG3PT9OnTuUl0mT17tniQ24ABA7jJw8PjypUrXI6MjAwICCApomFJlsSAvCEa8L/bSGf+/PnURHopNrFo0SIanwJZKig9lW+EITcuSF3oY6dNP3jwwNbWNkOHdPgtEPwWkvXB4rlz55KSkoSEq4EcgkID5LAAIPKxcbwoRY0sObRgvXr1SjIK7t+/Tys1hWiSneBewi4K7F+vXj3hyVikI6rKAm2Ie3GVX0uVKsVdKBLS6f9boiiKyiT53Df3MCGHBMU91apV4wd2W6Trys8//0xxEoXawiLgprp163KTcKA3yBEYvfLpSgt9NlduFW7qAXlDNKBkpxCNC8q+jHQ6VDmm8JGq3CUoKIjKTk5OpIiiixIRd4pNxMfHc0G5FQnIISg0yIsj0AhVqlQR5YoVK3KB8wgnZ3xqqIVeckgyKSyTjAJOIhoSEiLZBcIuCuxPUd3/nPRIz5eROhpMaiplNGXyJoWpCTk0ZqHgaenSpUeOHJF8li1bxk1hYWHcJBzKly/PWkL6QRKrbFKW1QPyhsTJSYFaDoW4Sph4I+oup06doqB/5MiRkp0RcshvQYl6KwLIISg0GF4cQb4zZMiQS5cuPXnyJDo6mtYvNpo4WTpq1Kj9+/eLFKZsJDhnBycRTUxMFHYJYRcF9h86dChXRe6PCxcupKSkrFq1SvLngsGkppzRlHpxRtO8TGGaDTn8+++/JQtDcSQ3nTlzhpuEg4uLC1+PExERQZGisklZVg/IBRpQaSeaNm3KBdHl8uXL/2tWoP7vUJzYNNZF/d4ZfgvJ+mA3Y4vRLsmQQ1CIMLw4AlCwcHBw6NOnj/o+1GzIIQ1FwZmzs7OwWFpali1b9sCBA9y0du1aSQ7pCGDs2LF0KNC7d2+KjJVNyrK0URqQN0QDKu0MiWXlypVFl/Hjx1OVZnL16tWMjhmuLFX+ySd1OXz4MG2rePHi4s9Lfl/Cn99CpUqV+C0oUX9cAsghKDRADkFh4NSpU7a2tlZWVj4+PsoTs8bkEJgLs8shX3hsof/LM9vPyLQwchYEABNgpwGFBFJEe3t7UsRatWp99tlnbIQc5jZml0MKWPnJJxTFli9fXm7OHJBDkA2w02QBK6B56tSpwwVra2s7O7vRo0fL6zcwK2aXQyXiYmkhb1zg+2iVt7f6+/vr9E+97tix47p165Ru6ttt69evf+PGDZ3+HLvSzuO4uromZ7xTlujVqxfpNN/Uq4Y6knK/9957sbGxOv3FbnxvLncX05OmDbQG5BAUHk6cOEFCSGvcu+++SwtQQkICosPcJlflUCDJId9Hq7y9deXKlVT47LPPfHx86FXppr7ddvjw4cuWLaPChAkTlHYeJy4uTrpTltixY0dKSgrf1KuGOiYlJS1atIgvPaPufG8udxfTk6YNtAbkEBQSSAttbGyaNGnSvn37bdu2sRFymNvknhxa6BFlqaDT3/PDVQv9XZ5UoMArOjqaIj+lGzsoq3v27OnSpQsVpP8mxTh16tTh3Kq2trbc9OTJE6WnBI9Ph19W+nuHqLtOf38tdxfDMmLaQGto/Vt5qke2ApAROu6mI/Hw8HDJXhTkMBt5t82I2eVQmYaJ/0TUpetNfHw8F/g+Wun2Vp3+Dtfbt29HRkYq3QzebktN48aNk4zKcaQ7ZZU39QpoPlzgjvfv3+eMGdRd6SaGlaYNtIamv5W0tDRvPVSQ2wBI59q1a8aeE5R5ObQwfi+BgNbZESNGlClTpnHjxps2bZKb84ls5N02I2aXw7Jly7Ii0iuV2ViiRAmKz4YNG8ZCwvfRSre3EiNHjpw8eTJ9R0o3g7fbzpo1S33bq3CT7pQl9u/fT1W+qVen12mej+j48OFD+ijGjBnD3fneXO4uhpWmDbSGpr8V2r3C9Zj9JweKCGaUw5iYGCcnJz8/v3v37u3du7dmzZqyR5HE7L/N4OBgvtGCXkV0SMY333wzICCAhWTXrl0NGjTw9/eX5DApKenDDz/kdHTCjWI1tfycPXtWbRQWOrr6+OOPy5Urd/nyZbb07t2bqufPn+cqzY3nIzpSK3VJ1meMou5UbdKkCXcXw0rTBlpDu98K/QBMVAHIDK+Vw8wny3ZwcDh58qTSwsyePZszX/v4+LBFnfmac2erA0oPDw/a+pUrV5RizOVJkybRart06VJHR0dRjY2N5aoge3m3zYjZ5TAPePz48ZQpU6ZOnSo3ZBfIW+FAo9/ihQsXZJMRIwAmeK0ciqcVCkGKiorigiQ8ZcqUuXPnjtLCkExyISIiggsi6ZoYk5SMCxKnTp3igloOGzZsKGairgpEZjUbGxsuqLeeqxREOaTQrV27dskZc//mBMhh4UCL3yIdtakzPuv0V2RRkxl3YlDoea0cZj5ZdqNGjS5duiSq/ByMZH3+bi6I5z8IxJicO7tVq1YZ2/+H8ExISOCypaVlYmKicJCqguzl3TYjBVEOATCI5uSQNC/ZuOBRkxlPcWiNLVu2KKsUuCirxuAj03v37skNWiK/pvdaOcx8smwvLy9a+kV16dKlXHBxceGCiA4FkiCFhoYqq0qE57lz50R0KBRXXRVkL++2GYEcgkKD5uTQx8dHNmUkKipKNhUWmjVrRhEAlx88eJClMzAav7E3v6b3WjlcvXo1STWFfUI8ZsyYQcJDMsPn0wSRkZF2dnbz5s2Ljo5eu3Zt5cqV2b548WLpv0OBGHPDhg0UxolHT5w9e1bIGMPP5k1KSmrfvj33+uabbzZt2hQYGOjk5CSqFLlyVSD+O5TsyZBDALJIFhbc3CY4OPjgwYOy1RDkViivrLl69Wrjxo25TDGHkMPu3btXqFDB3d2dq2SvX7++uEzcQoFOf1Ub+ZMzPxzRIj1BVLI+75RIHGUsfxX5r1u3rnz58uLGYU5bxcPSNHhYgtNcXbt2javJ6YmpuEq6XrZsWWdn599++02aHr8XHofzNbds2ZIiJ+5oXl4rhyCHaEEOaRdS3q1oLmjY58+f01HRsWPH5DZQGNGQHGYpj1+WnAsQJDy//vorRQ8ODg6sHzrVYw7JTlVxQMBuwnnUqFHkT878lESL9ARRnHdKJI4ylr+K/AcOHEhhinjSIaet4mFpu+Lhi5zmaunSpVwViam46unpmZKSQlXOa6WcHr8XHodWHBp/586dFHixg3mBHOY2WpBDsXeZl1waFmgWrXzf6nwiryUbXbTPvHnzvtDz7bffil8jB1Iim7D0K5XksG7duuRPzrVq1WK7Mu+USBwlUI/GAR+nmyK4Ow9LBR6W4DRXXbt25apITMXVmjVrcoFRTk+nfy88TufOnSlSNJ0BKydADnObfJdDi3SkExhsZB/pxEb79u2rV6++YsUKMQIdhlKBz5fUqFFD2Z1fpezbfFajdOnSuXRWI6ts27bNx8fHF2QRcecoowk5DAwMzEYmNupCHWVrwad58+YuLi46hYTwzzg5/QojYVdWhZFkhvzJmX7wSruUd8pY/iqqRkdHU4HTTQl4WCrwsLr0NFc9evTgqpSYSuqunJ5O/17EOAQFkUJ9zQvkMLfJdznUpe9d6iM2gWTnf+j5bL9O9YMSPxPpl8VNXOXDuGw/jtG8zJ49OykpSf5iQOZYs2aN+CQ1IYdACa0vc+fO1Sl+h+qTpcJZVOlY9e7duzr9WUo+WTpo0CClM+edEomjjOWvouqoUaMoeuN0UwIelqbBw+rS01yJwyuRmIqrNAhVt2/fznmtlNPj98LjODo6BgUF8bE2dzQvkMPcZv78+fKHnufwPlyqVKmXL1/q9Dub5CDZufr8+XOuip8ABVi9e/euV6+e0s6v9+/fp1Zq4mpcXFzbtm1LlixJPyJ2zkewk+cEPz8/8UlCDjVHZGRkRESETvEr7datm6WlJZ+cVNqVVQ8PD07wGB8fT/7kzPmFhTPnnRKJo4zlr6LqwoULy5Url5zxdhcelqYh0hZzmqtbt25xVSSm4ioJLVXd3Nw4r5VyevxeeJzTp09TKFxCkY7LvGClyFVIJOrUqUOh0o4dO/Lxzwveh9UnMASSnU/pi11X/AT4fMnFixeVdn41mH372bNnuXRWI0tgJ88JytMbkEOQAUkdTWDeNFe5BFaK3Ea5mtAx0Hfffffpp582b978iy++WL16tcEHQZgd3mnVR2wiA7hkb9euHWnnzp07uSr2eT5A5CuxhZ1fpXSjfBhXvHjxXDqMyxLYyXMC5BAYJfNyaN40V7kEVorcxuB/hxEREaQf06ZNq1ev3vvvv09xFT8gQvbLV4Q6FnSwk+eEzMqhRUbk5lwmS1vMjPOjR4/q1KlTqlQpW1tbY1dpgsLBixcvaCF2dXWlQ/gxY8bQevGvf/3r5MmT4eHh8q8B5ACKjTJ/wx99KZcuXZo6dSrFavTVDBgwYNasWWFhYQYzMuYqtAKULl26Y8eOckPBBHKYE7Igh7IpD8nS1l/r/OzZs1atWl25cuX58+eki507d6ZXXSY6ggJKZGQkLbs1atSw12NnZ1e3bl1ra+sJEybMA2bi+PHj8ueeOejbOXjw4NKlSzt06GBjY9OmTZuZM2du3rz57Nmzsit4HZDDnJB9OSTL6tWraVkRaSBSUlIGDhxoaWn522+/6fT3Avbo0YMWHQcHh71793KX0NBQ8Sd2lSpVaO/nG8PZn5xLlixJ/mxJTU21srJSXuLh7e1Ni1qZMmXEX9/Cc/jw4eRMvyLhPGPGjKpVq06aNIlalc7006WdRlTXrVtHw+r004uIiKhQoUKXLl3+/PNPttCE27Vrp1NMj98LKHAcPXrUzc2tVq1aVnr45kigKeinevXq1RUrVtCRSvfu3Rs0aNC1a1eK6fft2/fXX3/J3kAF5DAnZEEOlbAlLCxMtOr0F8onJSUpezEkk2+88YZO7yau1GrZsiUXaJESnoz4X6FZs2Zc4PF1ilP80lpGnnfu3KHC4cOH2ZnGF5PhZCgC8ac6Q5sjCdfpt8KToY58VaRywgJ+L7nH3bt3acmmgPXy5csiT5tp8isLaGYQ310+EhMT4+/v37x5888+++ydd96hnefEiROyE9A8dLT6008/BQQE9OzZ09XVlQ6mP/300ylTpqxatYrWIj7HU8SBHOaELMih2iLdrFO6dGm+iUdw8uRJCrxsbW2Fgoqry4QmJSsuwSDnfv36iVQpwkdsXcR5tC0uMOTJ/zo8SM92XalSJYt01M5i5jr9LfxCDvl/RHoXFCOyRXk5HE9P/VGYl7Fjx4rg9fTp0xkbDZPbU8oJ+Ts32mEOHDjg4OBAi+alS5fatGlTu3ZtaGHhgH7Fhw4dWrdu3fTp0zt06EDrRrdu3UaMGDFv3jxaefj4uKhRFOTw+PHjsslM5EgOpXK5cuXS0tKEkXZTOzu7NWvW3Lp1ix2UXSpWrMgFcSUL+ZPzmTNnxIlQE3JYrFgxLjBCDh8/fszO5cuXN3ZhNx1XRkZGiurt27f59nDqyBnCaCh6L2wRbmJ66o/CvNjb26sfbixl7t69ezdpPGe7ttDD9kwmxU7OmMJbIL6m1atX169fX1wZ0bFjRxqWPgGlszIxt06VuYrieOpFXXhMddZvzgbOM6GdQcyE812Jkwc5wdfXlzZBn4bYE2rWrIlzpIUY2hWDg4MXLVr08ccfc/jYt2/fcePG0TL3yy+/XL9+3diaUGgwLYdBQUEWimebKMv5TuYno35+mbkwpxzOmjVr586dtMOxupAWbtq0iarigQzKLlu2bHn06NGNGzdatGjBFvIn53PnznFaMoK6kz7dvHlTdKQ19Ike6SwiedLaR/ZWrVqxc0BAwNy5c2kTtH906tRJ6UxqR8eS0dHRJK60Onft2pXXYurYtm1bElQfHx9PT0+2iF5ieuqPwryQxqjT1LGKCM3o3LkzHReL9J5iSpnMAmo6Z6lFempTMSynahOJrBgpEykjMleRLlIv6sJVddIsZfZUnf4CP7Zzviv1nDPJ3bt33dzcPvroo+3bt0tNpN+IC8Gff/554MCBb7/9dtiwYXSIZmVl1bx5c5JPb2/vZcuWkWDwsyrlbgUEE3L4119/0W+WfvVUYIuFXoHolVbLKlWqfP/99/SxVKpUiZ8+9scff1C0TV0aNGiwbds2slDf/v370wJ17NgxHmHy5MnUkQ44+NHTNNSSJUtq165NB7XKQUqWLCkG4c1VrVqVNyc8eTKvHdMiHWqiX7SXl1eZMmVo3Q4LC+PuDPWtXr06TZ5iGGGkYclIIyscM5AFOVTCFmUrvdIS1qdPHzq05+QjFJE4OTnRZ0fKp+5CVK5cuV69euK5B+RPzqSFyiff0uzpPYiOX3/9NX1bb775prQ0E35+fuRMOzQ7U5zKHystrzExMZIzCRtFP3yjRbIi/+eKFStoDqQi/CRF5YTF9KR3YXYcHR2vXLnCZaGLfBZanIum/ZL2MEtLS84LJaZE74jdOAcVp48SbgJy4++RBlHapa9JFDjyVp5h1qnSX0mZq4oXL069qAtX1UmzXr16xXZpJpzvik9fZ4mjR48OGTKkYcOG4i9tCemJygDo9PthZGTkqVOnVq9eTTvwmDFj3nnnHTr2bdmyZe/evUeOHElrAh3lnzx5kg6U5c7aw4Qc0nrISjBlyhS2WKTLYb9+/ehDoKX7008/paNY+pGSnUKOhQsX0vHl9OnT6aCBLJMmTSIlowNZWqOS9c8HpUD83r17y5cvpwIP1aZNG4oZ6LemHITGFIPw5mgc3pzw5MlkZkz2JGbPns3P+KQvbsCAAWxk5s+fTzMnMXZ2dmYLP82UhINGVnoqyawc5h759Wx0zUK7rPjvUCTLkDJ36/SKLrJdC93KZFJsKYW3gMcRo4nC7du3dfoL4tMd/w8pMbeUuYo2Qb2oC1eNJc0yOBN+a5LRBKT6S5cupYOYzZs3mwgrsaeBzHPz5k2SwODgYIpgRo0aRdJIh850tEeh5KBBg+hHun79emolHzoQlDvnPnRwSfIgHhojMCGH9FsjeeACZ/YXckg/Wy5w4Cj0hqGtvPHGG1SgY02KE4S9WbNmosoCSR3PnDnDFmOD8OaoKm2OXzMzphjZwcGBH51NAT0tR2xk3NzcuPDvf/+bCzSyaDVGvskhHctTkPvWW2+NHTtWbivynDhxgiJROkQVj+mQUpWePn2awi+R3tPDw4PtmcwCKuUsFbB08auy8OGHH9JPKCgoSHjqVJlIpcxVSUlJ1Iv/q9AZSprF8ExoHDETznclhZ4GoaO81q1bd+rUSfoHFIC8hwKg48eP0w5P0SStaf/85z9JQZ2cnOhIlANNEtF58+YtXryYfEhEb926xYnsc8KaNWtq165NgZfQRRNyaKGAfptsEa/qwrJly+gIgA40w8LC2EK/X/rVsw9BP1uKFEU1OaMEKgc5cuSIGMTY5vg1M2MKS/ny5fmEKq0qxYoVE24EiQsX6EPmAudeNk2+ySEA2YOOi3/++efBgwd/9dVX586dk5sB0BgcaB48eJC0cO7cuSSWpI4tWrSgIz+SCgo3qerp6Un2hQsX8kNd/vzzz8jIyMwc59WqVatRo0b169dnRTQmh3S4SQ5cJr2pUaNGskpdpEK1atX+/vtvKvD1g8n66DAmJoZ9CNouDSuqyYakSz2Isc3xa2bGFBb6AEV0KF1f07RpUy4cOnSICzTy/5qNADkEBYONGzd+9NFHrq6u+fi0BADymPv375MuXrhw4ccffySlpPX6m2++YUHt1KkTSSkJG2kqZ5awtrb+8ssv5TU+OfnBgwcODg5KS1RUFN+TlqySJVHgO5QozFq7di1b7t2716NHj9KlS584cSJZfyXL+PHjK1eu3LVr16tXrypHkAZxdnYWgxjbHL9mZsxvv/2W4lR2po+iUqVK9Gnw+V4lpMQ0jp+fH1fJmarUkUbO6Pg/IIdA6/z0009ffPHFsGHDjh49Kt3YCkARhyI2e3t70kIKE//xj38Yiw5BZoAcAu1CB8XTpk3r1asXLgoFQM2pU6coIiQhdHR05Au/IYc5AXIItMX27dv79OnTuHFjThsLAFBDQkhx4ejRoyU75DAnQA6BJkhNTT1y5MhIPTgpCoBpVq1alZCQIFshhzkDcgjyHwoEXV1d+/Xrt2PHDrkNAJBpIIc5AXII8ocffvihd+/ePj4+IgUPACCHQA5zAuQQ5CkvXrz46aefhg0bNnbs2Gw/MBYAYBDTciil8DaB2k1tKXxADkHe8euvvzZu3HjAgAHiWRkAADNiWg67du06aNAg2WqIoiB+aiCHIBeJj49ft24d/Qh9fX2vX78uNwMAzIoJOTSYwtvDw+PKlSvJ+vTcsbGxS5cuFZlCz58/T4UtW7YI54EDB/r4+HCVN6ROol2iRAnqsmnTJn46QsECcghyhadPnwYHBzs5OU2cOPHMmTNyMwAgFzAhhwZTeJ86dYpbGzZsqHRWR4dkOXHihJWVVVxc3P379zlltjqJdpUqVQICAqS+BQXIITAn06dPd3Fx6dGjR2JiotwGAMhlTMihhQJlCm+G054JDMohvW7YsKFevXqkgjt27Eg2kkSbJLZVq1YjR45U9C4YQA6BGYiKilq8ePF7773n7+8vPQcKAJBnGJNDEym8mcxEh8n6x+rWrFmTAkF+tIWxJNqhoaHqEbQP5BDkiKSkpM2bNzs5OU2dOhXPlwAgfzEmh15eXsrqjBkzkjNq3jfffEMyGRgYSL9lqYkRlmnTpnl7e3OZn9HB/x1yR5JViiC3bt3Kj+otWEAOQZb55Zdfxo4da29vHxQUVCAeEQ5AEcGYHILMADkEWeDChQvTp0/v2rXrmjVr6FhSbgYA5CuQw5wAOQSZ4tatWwsXLmzdurVyjwEAaArIYU6AHAKj7Ny5s3///vb29seOHUNObQC0D+QwJ0AOgcyLFy9+/vnnESNG/POf/9yzZ8+zZ89kDwCAJoEc5gTIIcjA2bNnHR0de/bsuWnTJrkNAKBtIIc5AXIIdEuXLu3QoUPTpk0vX74stwEACg6Qw5wAOSy6JCQkbNiwoUePHl5eXsijBkAhAHKYEyCHRYsXL16MGDHC3t5+4MCBT58+lZsBAAUZWtCjoqLkZR5kDuWTdiCHhZlXr15NnDjRwcFh8+bNDx48kJsBAAWfZH2I4+vrOw9kHeUnCTksnFy6dGnWrFlubm4rVqy4c+eO3AwAACAj2pXDv/76a9GiRXP1UIGqsgfISGxs7EcffdSoUaNp06bJbQAAAEyiUTmMiopav359dHQ0n96lAlXJKPsBPdu2bevbty/unQcAgGyjRTk8d+7c9OnTM/zdqYeMeH6CkmfPnu3du3fw4MGff/75jz/+mJKSInsAAADIHFqUw/j4eFkJ06EmEkW5QxHj9OnTTk5O7u7u9GnIbQAAALKF5uTw6tWrsgZmJDAwUO5TZJg1a1aTJk06duyI88YAAGBeNCeHy5YtkwUwI9HR0XKfws7169cXLFjw7rvv+vr60uGC3AwAACDHaE4O58+fLwugCrlPYeTBgwe9e/du2LDhhAkT0tLS5GYAAABmBXKoOR4/fvyPf/zD3t7+4MGDL168kJsBAADkApqTw/DwcFn9MlL4nrqQmpp67NixsWPHfvLJJz/88ENyYdd7AADQIJqTQ+L+/fuyBqZDTd9++63coSBz5swZZ2fn7t27r127Vm4DAACQV2hRDn18fGQZTIeaYmJi5A4FE3GZaGRkpNwGAAAgb9GiHBKkeZs3b753794jPVSgakEXwqioqGXLlrm5uc2cOfP8+fNyMwAAgPxDo3JIXLt2bfny5Qv0UIGqskfBITY2dt26dU5OTl5eXq9evZKbAQAA5DfalcPCQVJS0ieffGJvb//ll1+mpqbKzQAAALQB5NDMpKSk7Nu3z9PTc+DAgbt27Xry5InsAQAAQHtADs0GBX9Hjx6lQJDCwa1bt8rNAAAANAzk0Ay8evXq5MmTjo6O7u7usbGxcjMAAADNAznMJmFhYXPnzm3evPmCBQuuX78uNwMAAChQaEIOg4KC+ArSrEId5bFyH06oTUJIckiiKDcDAAAogGhCDrXP2rVr3d3dnZycTp06hTslAACg8AE5fA2bN2/u06fP2LFjjx07hjslAACgsAI5NMzDhw+DgoL+3//7fyNGjDhw4IDcDAAAoHABOTTM8+fPZRMAAIDCC+QQAAAAgBwCAAAAkEMAAABABzkEAAAAdJBDAAAAQAc5BAAAAHSQQwAAAEAHOQQAAAB0kEMAAABAp305fKpHtgIAAABmRdNyuGDBgnA9VJDbAAAAAPOhXTncuHHjyZMnuUwFqmZsBwAAAMyGduUwODjYRBUAAAAwI1qUw6ioKB8fH9mq05GRmmQrAAAAkGO0KIdTp0598eKFbNXpyEhNycnJcgMAAACQMzQnh6R5JgSPmkgRZSsAAACQM7QlhytXrrxw4YJsVUFusgkAAADIARqSw+Dg4IMHD8pWQ5AbrqwBAABgRrQih+Hh4bLpdWSjCwAAAGAQTchhXFyct7e3bH0d1IU6ylYAAAAg62hCDgMDA7ORiY26UEfZCgAAAGQdTcghAAAAkL9ADgEAAADIIQAAAJA9OQwJCdm3b59szQQWFoY3Z9BeqlQp2ZQ7GNw6AACAIkV2lMDd3b1Hjx6y1dzkmUrl2YYAAABoliwrQVRUlLW1tY2NjcimnZqaOnz4cDJu3ryZLSQwVatWfeutt7Zt2/bmm2+WKFFiz549bOfX1atXFytWTLLv3r2bLKVLlw4NDWWjgCzVq1fX6e81JCUuWbKkg4OD2LqVlZVy62lpaTVq1ChTpkzHjh3Zwt3btWvHVe5Fc6aO1EvI4YwZM8gyadIkahWeAAAAigJZk8OXL1+SEPIjealAVTI2a9bszp07VDh8+DC7scCkpKQIpRFCyK9hYWFqOynohg0b2C6MXLh48aKwMzQ4F2jrXBBbd3Jy4kJsbCwX1N2Vc+YNtWzZMikpiVudnZ2VzgAAAAo9WZPDvXv3tm3blstUCAkJoULZsmX5ARQPHjzgJkkFRUG8Pn/+XG2n0ajQqFEjVlll32fPnnFZp38UcL9+/WxtbblKW+eC2Lr401EEecrujHLOvKFKlSpZpEMRquQPAACgcJM1ObS2thZhGWlMzZo1qdCiRYt79+5R4dSpU9ykVDJlQfmqthszKlurV6/OUZ2IL2nrXBBbb9KkCRdEdKhGOWce39XV9fbt27IfAACAokHW5PC7775TVufOnUuvmzZt8vX1vXnzZqtWrdiuVrLMyKGjo2NQUBCFdCVKlKBqhQoVLl++HB8fr/S3s7OjzZ07d87FxYUtVH3y5Ily66tWrXqix8/PT3SU4DmTD/Xi8QMCAujt0ObmzJnTqVMnuQMAAIBCTRbk8OXLlw8fPlRakpKS+MQmCU+VKlWWLVvG9uzJ4enTp0nkihcvvnv3bqqSXJUrV87S0lLpHxoa6uTkRG5btmwRRgoZlVtPS0urVKnSm2++6eHhIXzU0JypI/Xi8anX5MmTaYvu7u4xMTGyNwAAgEJNFuQQAAAAKKxADgEAAADIIQAAAAA5BAAAAHSQQwAAAECnQTn8448/ZBMAAACQy2RNDsU9D8nJyatXr+7Xr1/GdjOgvK0CAAAAyBuypj1KrXr27Fm5cuXYGBoaygmyvb29OX32rVu3wsLClMk/ra2tHzx4MGPGjKpVq1pZWYkMagMHDrS0tGRPi3SkocQgAAAAQG6QTTl8+PChn5/f6NGj2ShyZMfHx3OhTp069Lpjxw6u6vR32ev0d+5zVSilsDBiE9JQAAAAQO6RZTlkqlev/sUXXzx69IiNIke2iPk4CzZVWSmPHz8ujSDSZHNeG4GQQ2koAAAAIPfIshzKpoxGoWHFihXjwuDBg+m1f//+XFU/XCItLU1ZVcuhGAoAAADIJQzImwleK4f+/v6cPrtx48Zs6dev3/vvv0+hJFfnzp1LMWV8fLxIk71z507SyO3bt3O1QoUKfJpUPRQAAACQSxiQNxO8Vg6//vprTp9948YNtvzyyy/kcO7cOa5Onjy5SpUq5cqVE2my+/TpU7p0aTc3N676+vpaWlrqDA0FAAAA5BIG5M283Lx5UzyqFwAAANAmuS6H7du3f/r0qWwFAAAAtESuyyEAAACgfSCHAAAAAOQQAAAA0On+P5apcQmz1NoXAAAAAElFTkSuQmCC>