---
solution: Target
product: target
title: Referencia de herramientas del servidor Adobe Target MCP
description: Referencia de parámetro completa para las 39 herramientas públicas expuestas por el servidor MCP de Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
hide: true
source-git-commit: ecb51d828807735b990b8f3a52102feb005bc61b
workflow-type: tm+mt
source-wordcount: '2972'
ht-degree: 14%

---

# Referencia de herramientas del servidor MCP [!DNL Adobe Target] {#target-mcp-tools-reference}

>[!BEGINSHADEBOX]

Tabla de contenido:

* [Información general](target-mcp.md)
* [Introducción](target-mcp-get-started.md)
* [Casos de uso y tutoriales](target-mcp-use-cases.md)
* **[Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)**

>[!ENDSHADEBOX]

Esta página es una referencia completa para todas las herramientas públicas expuestas por el servidor MCP [!DNL Adobe Target]. Para cada herramienta encontrará una descripción, detalles de parámetros, un valor devuelto y un ejemplo de petición de datos en lenguaje natural. Para obtener instrucciones de configuración y casos de uso, consulte [Introducción](target-mcp-get-started.md) y [Casos de uso y tutoriales](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a los productos de Adobe es una configuración elegida por el cliente, y los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## Requisitos previos   {#tools-prerequisites}

La función [!DNL Adobe Target] determina qué herramientas están disponibles para usted:

* Función **Observer** o superior: acceso a todas las herramientas de lectura
* Función **Editor**: acceso para leer y escribir (crear) herramientas
* Función **Aprobador**: acceso para leer, escribir y activar/desactivar herramientas

Para obtener instrucciones de configuración completas, consulte [Introducción](target-mcp-get-started.md).

## Herramientas de actividad {#tools-activities}

+++Enumerar actividades

**Herramienta:** `list_target_activities`

Enumerar [!DNL Adobe Target] actividades con filtrado y ordenación del lado del servidor.

Recupera una lista paginada de actividades. La API de administración de [!DNL Target] aplica todos los filtros del lado del servidor. El servidor devuelve un máximo de 200 actividades por página.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `limit` | entero | No | Número máximo de actividades que se van a devolver (servidor máximo: 200) |
| `offset` | entero | No | Número de actividades que se omitirán para la paginación |
| `sort_by` | string | No | Campo por el que ordenar. Prefijo con `-` para orden descendente (por ejemplo, `-modifiedAt`). Opciones: `id`, `name`, `state`, `priority`, `startsAt`, `endsAt`, `lifetimeStart`, `lifetimeEnd`, `createdAt`, `createdBy`, `modifiedAt`, `modifiedBy`, `type`, `thirdPartyId` |
| `state` | string | No | Filtrar por estado de actividad: `approved` (activo/activo), `deactivated` (inactivo), `paused`, `saved` (borrador) |
| `activity_type` | string | No | Filtrar por tipo: `ab` (prueba A/B), `xt` (segmentación de experiencias), `abt` (Automated Personalization) |
| `name_contains` | string | No | Filtrar actividades cuyo nombre contenga esta cadena (sin distinción de mayúsculas y minúsculas) |
| `starts_after` | string | No | Fecha ISO 8601 — actividades que comienzan después de esta fecha |
| `starts_before` | string | No | Fecha ISO 8601 — Actividades que comienzan antes de esta fecha |
| `modified_after` | string | No | Fecha ISO 8601 — Actividades modificadas después de esta fecha |
| `ends_after` | string | No | Fecha ISO 8601 — Actividades que finalizan después de esta fecha |
| `ends_before` | string | No | Fecha ISO 8601 — Actividades que finalizan antes de esta fecha |
| `workspace` | string | No | Filtrar por ID de Workspace |
| `segment_id` | string | No | Filtrar por ID de segmento de audiencia |
| `profile_attribute_id` | string | No | Filtrar por ID de atributo de perfil |
| `priority` | entero | No | Filtrar por valor de prioridad exacto (0-999) |
| `mbox` | string | No | Filtrar por nombre de mbox/ubicación |
| `offer_id` | string | No | Filtrar por ID de oferta |
| `view_id` | string | No | Filtrar por ID de vista de SPA |

**Devuelve:** objeto JSON con `activities` (lista de objetos que incluye `id`, `name`, `state`, `type`, `priority`, `modifiedAt`, `startsAt`, `endsAt`) y `total` (el recuento total puede superar el tamaño de página devuelto).

**Mensaje de ejemplo:** &quot;Enumerar todas las pruebas A/B activas ordenadas por las últimas modificadas&quot;.

+++

+++Obtener una actividad A/B

**Herramienta:** `get_ab_activity`

Obtenga información detallada sobre una actividad A/B.

Recupera la configuración completa de una prueba A/B específica, incluidas experiencias, ubicaciones, métricas y reglas de segmentación.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad A/B |

**Devuelve:** detalles completos de la actividad, incluidos metadatos (nombre, estado, prioridad, fechas), experiencias, ubicaciones y ofertas, objetivos y métricas, y reglas de segmentación.

**Mensaje de ejemplo:** &quot;Obtener detalles de la actividad A/B 12345.&quot;

+++

+++Obtener una actividad de segmentación de experiencias

**Herramienta:** `get_xt_activity`

Obtenga información detallada sobre una actividad de segmentación de experiencias (XT).

Recupera la configuración completa de una actividad XT específica, incluidas las asignaciones, ubicaciones y métricas de experiencia de audiencia.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad XT |

**Devuelve:** detalles completos de la actividad, incluidos metadatos, experiencias con asignaciones de audiencia, ubicaciones y ofertas, y objetivos y métricas.

**Mensaje de ejemplo:** &quot;Obtenga detalles para la actividad de segmentación de experiencias 12345&quot;.

+++

+++Obtener una actividad de Automated Personalization

**Herramienta:** `get_abt_activity`

Obtenga información detallada sobre una actividad de Automated Personalization (AP).

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad AP |

**Devuelve:** detalles completos de la actividad, incluidos metadatos, experiencias, ubicaciones y configuración algorítmica.

**Mensaje de ejemplo:** &quot;Obtener detalles de la 12345 de actividad de Auto-Personalization&quot;.

+++

+++Creación de una actividad A/B

**Herramienta:** `create_ab_activity`

Cree una nueva actividad de prueba A/B.

Crea una nueva prueba A/B con la configuración especificada que incluye experiencias, ofertas y segmentación.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `name` | string | Sí | Nombre de la actividad |
| `state` | string | No | Estado inicial: `approved`, `deactivated` o `saved` (predeterminado: `saved`) |
| `priority` | entero | No | Prioridad de actividades (0-999, predeterminado: 0) |
| `starts_at` | string | No | Fecha de inicio de la actividad (ISO 8601) |
| `ends_at` | string | No | Fecha de finalización de la actividad (ISO 8601) |
| `experiences` | matriz | Sí | Lista de configuraciones de experiencia |
| `locations` | matriz | Sí | Lista de configuraciones de ubicación/mbox |
| `goals` | objeto | No | Métricas de objetivo principal y secundario |
| `audiences` | matriz | No | Configuraciones de audiencia de Target |
| `workspace_id` | string | No | Workspace ID de la actividad |

**Devuelve:** El objeto de actividad creado con su ID asignado.

**Mensaje de ejemplo:** &quot;Cree una prueba A/B llamada &#39;Homepage Hero Test&#39; con dos experiencias probando distintas imágenes a pantalla completa en el mbox homepage-hero&quot;.

+++

+++Crear una actividad de segmentación de experiencias

**Herramienta:** `create_xt_activity`

Cree una nueva actividad de segmentación de experiencias (XT).

Crea una actividad XT que ofrece diferentes experiencias a diferentes audiencias en función de las reglas de segmentación.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `name` | string | Sí | Nombre de la actividad |
| `state` | string | No | Estado inicial: `approved`, `deactivated` o `saved` (predeterminado: `saved`) |
| `priority` | entero | No | Prioridad de actividades (0-999, predeterminado: 0) |
| `starts_at` | string | No | Fecha de inicio de la actividad (ISO 8601) |
| `ends_at` | string | No | Fecha de finalización de la actividad (ISO 8601) |
| `experiences` | matriz | Sí | Lista de configuraciones de experiencia con asignaciones de audiencia |
| `locations` | matriz | Sí | Lista de configuraciones de ubicación/mbox |
| `goals` | objeto | No | Métricas de objetivo principal y secundario |
| `workspace_id` | string | No | Workspace ID de la actividad |

**Devuelve:** El objeto de actividad creado con su ID asignado.

**Mensaje de ejemplo:** &quot;Cree una actividad de segmentación de experiencias denominada &#39;Geo Personalization&#39; que muestre contenido diferente a visitantes de diferentes regiones.&quot;

+++

+++Actualización de una actividad A/B

**Herramienta:** `update_ab_activity`

Actualice una actividad A/B existente.

Utiliza un patrón de lectura-modificación-escritura: recupera el estado actual, combina los cambios, valida y envía la actualización.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad que se va a actualizar |
| `activity` | objeto | Sí | Campos para actualizar (nombre, prioridad, experiencias, ubicaciones, objetivos, etc.) |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Actualice la actividad 12345 para cambiar la asignación de tráfico a 70/30.&quot;

+++

+++Actualizar una actividad de segmentación de experiencias

**Herramienta:** `update_xt_activity`

Actualice una actividad de segmentación de experiencias existente.

Utiliza un patrón de lectura, modificación y escritura.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad XT que se va a actualizar |
| `activity` | objeto | Sí | Campos que actualizar |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Actualice la actividad XT 12345 para agregar una nueva experiencia para los visitantes móviles&quot;.

+++

+++Actualización de una actividad de Automated Personalization

**Herramienta:** `update_abt_activity`

Actualice una actividad de Automated Personalization existente.

Utiliza un patrón de lectura, modificación y escritura.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad AP que se va a actualizar |
| `activity` | objeto | Sí | Campos que actualizar |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Actualice la actividad de Auto-Personalization 12345 para cambiar el objetivo de optimización&quot;.

+++

+++Actualizar programación de actividades

**Herramienta:** `update_activity_schedule`

Actualizar las fechas de inicio y finalización de la actividad.

Actualiza la programación de una actividad sin modificar otros ajustes.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad |
| `activity_type` | string | Sí | Tipo de actividad: `ab`, `xt` o `abt` |
| `starts_at` | string | No | Nueva fecha de inicio (ISO 8601) |
| `ends_at` | string | No | Nueva fecha de finalización (ISO 8601) |

**Devuelve:** confirmación de la actualización de programación.

**Mensaje de ejemplo:** &quot;Actualice la programación de la actividad A/B 12345 para que se ejecute del 1 al 31 de mayo&quot;.

+++

+++Cambiar estado de actividad

**Herramienta:** `update_activity_state`

Cambiar estado de actividad (activar, desactivar o pausar).

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad |
| `state` | string | Sí | Nuevo estado: `approved` (activo/activo), `deactivated` (inactivo), `paused` o `saved` (borrador) |

**Devuelve:** El estado de actividad actualizado.

**Mensaje de ejemplo:** &quot;Activar 12345 de actividad&quot; o &quot;Pausar la prueba principal&quot;.

+++

+++Cambiar nombre de actividad

**Herramienta:** `update_activity_name`

Cambie el nombre de una actividad.

Actualiza solo el nombre sin modificar la configuración completa.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad |
| `name` | string | Sí | Nuevo nombre de actividad |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Cambie el nombre de la actividad 12345 a &#39;Prueba Hero de campaña de verano&#39;&quot;.

+++

+++Cambiar prioridad de actividad

**Herramienta:** `update_activity_priority`

Cambiar la prioridad de actividad.

Las actividades de prioridad más alta tienen prioridad cuando varias actividades se dirigen a la misma ubicación.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad |
| `priority` | entero | Sí | Nuevo valor de prioridad (0-999; mayor = mayor prioridad) |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Establezca la prioridad de la actividad 12345 en 100&quot;.

+++

+++Añadir una variante a una actividad

**Herramienta:** `add_activity_variant`

Añadir una nueva experiencia o variante a una actividad.

Gestiona toda la coordinación estructural, incluida la creación de opciones, la asignación a ubicaciones y el reequilibrio del tráfico.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El ID de la actividad que se va a modificar |
| `activity_type` | string | Sí | Tipo de actividad: `ab`, `xt` o `abt` |
| `variant_name` | string | Sí | Nombre de la nueva experiencia/variante |
| `offer_id` | entero | No | (Basado en formularios) ID de oferta existente que se debe utilizar |
| `offer_content` | string | No | (Basado en formularios) Contenido de HTML para una nueva oferta en línea |
| `traffic_percentage` | entero | No | % de tráfico para la nueva variante (1-99). Si se omite, el tráfico se reequilibra de manera uniforme |
| `audience_id` | entero | No | ID de audiencia para la variante (actividades XT) |
| `modifications` | matriz | No | (VEC) Lista de modificaciones basadas en selectores CSS |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Agregue una nueva variante denominada &#39;Tema de vacaciones&#39; a la actividad A/B 12345 mediante 67890 de oferta.&quot;

+++

+++Actualizar división de tráfico

**Herramienta:** `update_traffic_split`

Actualizar la asignación del tráfico entre las variantes.

Los porcentajes deben sumar exactamente 100.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El ID de la actividad que se va a modificar |
| `activity_type` | string | Sí | Tipo de actividad: `ab` o `abt` (XT no compatible: segmentado por audiencia) |
| `splits` | objeto | Sí | Nombre de la experiencia de asignación de diccionario al porcentaje. Debe incluir todas las experiencias y sumar 100 |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Cambie la división de tráfico para la actividad 12345 a 70% Control y 30% Variante A&quot;.

+++

+++Cambiar la oferta de una variante

**Herramienta:** `update_variant_offer`

Cambie la oferta por una variante específica.

Funciona tanto para actividades basadas en formularios (usando `offer_id`) como para actividades VEC (usando `modifications`).

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El ID de la actividad que se va a modificar |
| `activity_type` | string | Sí | Tipo de actividad: `ab`, `xt` o `abt` |
| `variant_name` | string | Sí | Nombre de la experiencia/variante que se va a actualizar |
| `offer_id` | entero | No | (Basado en formularios) Nuevo ID de oferta |
| `offer_content` | string | No | (Basado en formularios) Contenido de HTML para una nueva oferta en línea |
| `modifications` | matriz | No | (VEC) Nueva lista de modificaciones basadas en selectores CSS |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Actualice la experiencia &#39;Variante A&#39; en la actividad 12345 para usar 99999 de oferta.&quot;

+++

+++Eliminación de una variante de una actividad

**Herramienta:** `remove_activity_variant`

Eliminar una experiencia o variante de una actividad.

Elimina la experiencia, limpia las opciones huérfanas y reequilibra el tráfico de forma uniforme entre las variantes restantes.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El ID de la actividad que se va a modificar |
| `activity_type` | string | Sí | Tipo de actividad: `ab`, `xt` o `abt` |
| `variant_name` | string | Sí | Nombre de la experiencia/variante que se va a quitar |

**Devuelve:** El objeto de actividad actualizado.

**Mensaje de ejemplo:** &quot;Quitar la experiencia &#39;Variante de prueba&#39; del 12345 de actividad A/B.&quot;

+++

## Herramientas de oferta {#tools-offers}

+++Enumerar ofertas

**Herramienta:** `list_target_offers`

Enumerar todas las ofertas de su inquilino [!DNL Target].

Recupera una lista paginada de ofertas de contenido con filtrado opcional.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `limit` | entero | No | Número máximo de ofertas que devolver |
| `offset` | entero | No | Número de ofertas que se omitirán para la paginación |
| `type` | string | No | Filtrar por tipo de oferta: `content` (HTML), `json` o `redirect` |
| `name` | string | No | Filtrar por nombre de oferta (coincidencia parcial) |

**Devuelve:** objeto JSON con `offers` (lista de objetos que incluye `id`, `name`, `type`, `content`, `modifiedAt`) y `total`.

**Mensaje de ejemplo:** &quot;Enumerar todas las ofertas JSON&quot;.

+++

+++Obtener una oferta

**Herramienta:** `get_target_offer`

Obtenga información detallada sobre una oferta específica.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `offer_id` | entero | Sí | El identificador único de la oferta |

**Devuelve:** Detalles completos de la oferta, incluidos `id`, `name`, `type`, `content`, `workspace` y `modifiedAt`.

**Mensaje de ejemplo:** &quot;Obtener detalles para la 67890 de ofertas&quot;.

+++

+++Creación de una oferta de HTML

**Herramienta:** `create_target_offer`

Cree una nueva oferta de contenido de HTML.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `name` | string | Sí | Nombre de la oferta |
| `content` | string | Sí | HTML o contenido de texto para la oferta |
| `workspace_id` | string | No | ID de Workspace para la oferta |

**Devuelve:** La oferta creada con su ID asignado.

**Mensaje de ejemplo:** &quot;Cree una oferta de HTML llamada &#39;Banner de venta de verano&#39; con un banner promocional&quot;.

+++

+++Crear una oferta JSON

**Herramienta:** `create_target_json_offer`

Cree una nueva oferta JSON para ofrecer datos estructurados.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `name` | string | Sí | Nombre de la oferta |
| `content` | objeto | Sí | Contenido JSON para la oferta |
| `workspace_id` | string | No | ID de Workspace para la oferta |

**Devuelve:** La oferta creada con su ID asignado.

**Mensaje de ejemplo:** &quot;Cree una oferta JSON llamada &#39;Configuración de indicadores de características&#39; con la configuración de alternancia de características.&quot;

+++

+++Actualización de una oferta

**Herramienta:** `update_target_offer`

Actualizar una oferta existente.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `offer_id` | entero | Sí | El identificador único de la oferta que se va a actualizar |
| `name` | string | No | Nombre de oferta actualizado |
| `content` | cadena u objeto | No | Contenido de oferta actualizado |

**Devuelve:** El objeto de oferta actualizado.

**Mensaje de ejemplo:** &quot;Actualizar 67890 de oferta con contenido promocional nuevo&quot;.

+++

## Herramientas de audiencia {#tools-audiences}

+++Enumerar audiencias

**Herramienta:** `list_target_audiences`

Enumerar todas las audiencias de su inquilino de [!DNL Target].

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `limit` | entero | No | Número máximo de audiencias que se devolverán |
| `offset` | entero | No | Número de audiencias que se omitirán para la paginación |

**Devuelve:** objeto JSON con `audiences` (lista de objetos que incluye `id`, `name`, `description`, `origin`, `modifiedAt`) y `total`.

**Mensaje de ejemplo:** &quot;Enumerar todas las audiencias&quot;.

+++

+++Creación de audiencias

**Herramienta:** `create_target_audience`

Cree una nueva audiencia con reglas de segmentación.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `name` | string | Sí | Nombre de la audiencia |
| `description` | string | No | Descripción de la audiencia |
| `targetRule` | objeto | No | Reglas de segmentación (ubicación geográfica, explorador, atributos personalizados, etc.) |
| `workspace_id` | string | No | Workspace ID para la audiencia |

**Devuelve:** La audiencia creada con su ID asignado.

**Mensaje de ejemplo:** &quot;Cree una audiencia denominada &#39;Visitantes móviles de California&#39; dirigida a usuarios móviles en CA.&quot;

+++

## Herramientas de Mbox {#tools-mboxes}

+++Enumerar mboxes

**Herramienta:** `list_target_mboxes`

Enumerar todos los mboxes de su inquilino [!DNL Target].

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `limit` | entero | No | Número máximo de mboxes que devolver |
| `offset` | entero | No | Número de mboxes que se omitirán para la paginación |
| `name` | string | No | Filtrar por nombre de mbox (coincidencia parcial) |
| `status` | string | No | Filtrar por estado |

**Devuelve:** objeto JSON con `mboxes` (lista de objetos que incluye `name`, `status`, `lastRequestTime`) y `total`.

**Mensaje de ejemplo:** &quot;Enumerar todos los mboxes que contienen &#39;homepage&#39;.&quot;

+++

+++Obtener un mbox

**Herramienta:** `get_target_mbox`

Obtenga información detallada sobre un mbox específico.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `mbox_name` | string | Sí | El nombre del mbox |

**Devuelve:** detalles de mbox, incluidos `name`, `status` y la lista de actividades que usan el mbox.

**Mensaje de ejemplo:** &quot;Obtener detalles para mbox &#39;homepage-hero&#39;&quot;.

+++

+++Atributos de perfil de mbox de lista

**Herramienta:** `list_target_mbox_profile_attributes`

Enumera todos los atributos de perfil de mbox disponibles para el direccionamiento.

No se requieren parámetros.

**Devuelve:** matriz JSON de objetos de atributo de perfil.

**Mensaje de ejemplo:** &quot;¿Qué atributos de perfil están disponibles para el direccionamiento?&quot;

+++

## Herramientas de propiedad {#tools-properties}

+++Propiedades de lista

**Herramienta:** `list_target_properties`

Enumerar todas las propiedades del inquilino [!DNL Target].

Las propiedades organizan las actividades y controlan el acceso.

No se requieren parámetros.

**Devuelve:** Lista de objetos de propiedad, incluidos `id`, `name`, `description` y `channel`.

**Mensaje de ejemplo:** &quot;Enumerar todas las propiedades de Target&quot;.

+++

## Herramientas de informes {#tools-reporting}

+++Obtener un informe de rendimiento A/B

**Herramienta:** `get_ab_performance_report`

Obtenga un informe de rendimiento para una actividad A/B.

Recupera las tasas de conversión, el alza y los niveles de confianza.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad A/B |
| `report_interval` | string | No | Período de tiempo del informe (por ejemplo, `last7days`, `last30days` o un intervalo de fecha personalizado) |

**Devuelve:** métricas de nivel de experiencia (visitantes, conversiones, tasa de conversión), cálculos de alza, niveles de confianza estadística y métricas de ingresos (si están configuradas).

**Mensaje de ejemplo:** &quot;Mostrarme el informe de rendimiento para 12345 de prueba A/B durante los últimos 30 días&quot;.

+++

+++Obtener un informe de pedidos A/B

**Herramienta:** `get_ab_orders_report`

Obtenga un informe de pedidos/ingresos de una actividad A/B.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad A/B |
| `report_interval` | string | No | Período de tiempo del informe |

**Devuelve:** recuentos de pedidos, ingresos y valor de pedido promedio por experiencia.

**Mensaje de ejemplo:** &quot;Obtener el informe de pedidos de la actividad 12345&quot;.

+++

+++Obtener un informe de rendimiento de Segmentación de experiencias

**Herramienta:** `get_xt_performance_report`

Obtenga un informe de rendimiento para una actividad de segmentación de experiencias.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad XT |
| `report_interval` | string | No | Período de tiempo del informe |

**Devuelve:** métricas de rendimiento de nivel de experiencia.

**Mensaje de ejemplo:** &quot;Mostrar rendimiento para mi 54321 de actividad de segmentación de experiencias&quot;.

+++

+++Obtener un informe de pedidos de Segmentación de experiencias

**Herramienta:** `get_xt_orders_report`

Obtenga un informe de pedidos/ingresos de una actividad de segmentación de experiencias.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | El identificador único de la actividad XT |
| `report_interval` | string | No | Período de tiempo del informe |

**Devuelve:** métricas de pedidos por experiencia.

**Mensaje de ejemplo:** &quot;Obtener datos de pedidos para 54321 de actividad XT&quot;.

+++

+++Obtener un informe de rendimiento por nombre de actividad

**Herramienta:** `get_activity_report_by_name`

Busque una actividad por su nombre y obtenga su informe de rendimiento.

Resulta útil cuando conoce el nombre de la actividad pero no su ID.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_name` | string | Sí | Nombre de la actividad que se busca |
| `report_interval` | string | No | Período de tiempo del informe |

**Devuelve:** detalles de actividad y métricas de rendimiento.

**Mensaje de ejemplo:** &quot;Obtener el informe de rendimiento para mi actividad &#39;Prueba Hero de página principal&#39;&quot;.&quot;

+++

## Herramientas de previsualización {#tools-preview}

+++Previsualización de una actividad

**Herramienta:** `preview_activity`

Generar URL de vista previa de control de calidad del explorador para una actividad [!DNL Target].

Crea vínculos de vista previa en los que se puede hacer clic y que fuerzan a que se muestren experiencias específicas, omitiendo las reglas de segmentación de audiencia. Funciona para actividades A/B, XT y Automated Personalization.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `activity_id` | entero | Sí | Identificador de actividad [!DNL Target] que se va a previsualizar |
| `experience_index` | entero | No | Índice de experiencia basado en 0. Si se omite, devuelve las direcciones URL de todas las experiencias |
| `url` | string | No | URL de página para vista previa. Necesario para actividades basadas en formularios. Para las actividades de VEC, anula la ubicación creada si se proporciona |

**Devuelve:** información de la actividad (nombre, tipo, estado), URL de vista previa para cada experiencia y nombres e índices de experiencias.

**Mensaje de ejemplo:** &quot;Genere direcciones URL de vista previa para 12345 de actividad para poder probar cada experiencia en mi explorador&quot;.

+++

## Herramientas de token de respuesta {#tools-response-tokens}

+++Enumerar tokens de respuesta

**Herramienta:** `list_target_response_tokens`

Enumerar todos los tokens de respuesta del inquilino [!DNL Target].

Recupera todos los tokens de respuesta configurados, tanto integrados como personalizados.

No se requieren parámetros.

**Devuelve:** matriz JSON de objetos de token de respuesta con estado `name`, `type` y `enabled`.

**Mensaje de ejemplo:** &quot;Enumerar todos los tokens de respuesta&quot;.

+++

+++Crear un token de respuesta

**Herramienta:** `create_target_response_token`

Cree un nuevo token de respuesta personalizado para recopilar datos adicionales en [!DNL Target] respuestas.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `token_name` | string | Sí | Nombre del token de respuesta |
| `token_type` | string | Sí | Tipo de token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO` o `CRS` |

**Devuelve:** El objeto de token de respuesta creado.

**Mensaje de ejemplo:** &quot;Cree un token de respuesta personalizado denominado &#39;campaign_id&#39; de tipo ACTIVITY.&quot;

+++

## Herramientas de revisión {#tools-revisions}

+++Obtener el registro de auditoría

**Herramienta:** `get_target_revisions`

Obtenga el registro de auditoría para un tipo de recurso.

Recupera los cambios realizados en [!DNL Target] recursos con filtrado opcional por autor.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `revision_resource_type` | string | Sí | Tipo de recurso: `activity`, `offer` o `audience` |
| `modified_by` | string | No | Filtrar por el usuario que hizo los cambios |
| `limit` | entero | No | Número máximo de revisiones que se devolverán |
| `offset` | entero | No | Número de revisiones que se omitirán para la paginación |

**Devuelve:** historial de revisiones con marcas de tiempo, usuarios y descripciones de cambios.

**Mensaje de ejemplo:** &quot;Mostrarme el registro de auditoría para los cambios de la actividad&quot;.

+++

+++Obtener revisiones para una entidad específica

**Herramienta:** `get_target_entity_revisions`

Obtener todas las revisiones de una entidad específica por ID.

| Parámetro | Tipo | Requerido | Descripción |
|---|---|---|---|
| `revision_resource_type` | string | Sí | Tipo de recurso: `activity`, `offer` o `audience` |
| `entity_id` | entero | Sí | El identificador único de la entidad |

**Devuelve:** matriz JSON de todas las revisiones para la entidad especificada.

**Mensaje de ejemplo:** &quot;Mostrarme todos los cambios realizados en el 12345 de la actividad.&quot;

+++

## Herramientas de plantilla {#tools-templates}

+++Enumerar plantillas disponibles

**Herramienta:** `list_target_templates`

Enumere los recursos y plantillas de MCP disponibles para crear actividades y ofertas.

No se requieren parámetros.

**Devuelve:** objeto JSON que enumera las plantillas y los recursos disponibles.

**Mensaje de ejemplo:** &quot;¿Qué plantillas están disponibles para crear actividades?&quot;

+++

## Resumen de herramientas {#tools-summary}

| Categoría | Recuento | Herramientas |
|---|---|---|
| Actividad | 17 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity`, `create_ab_activity`, `create_xt_activity`, `update_ab_activity`, `update_xt_activity`, `update_abt_activity`, `update_activity_schedule`, `update_activity_state`, `update_activity_name`, `update_activity_priority`, `add_activity_variant`, `update_traffic_split`, `update_variant_offer`, `remove_activity_variant` |
| Oferta | 5 | `list_target_offers`, `get_target_offer`, `create_target_offer`, `create_target_json_offer`, `update_target_offer` |
| Público | 2 | `list_target_audiences`, `create_target_audience` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propiedad | 1 | `list_target_properties` |
| Creación de informes | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| Vista previa | 1 | `preview_activity` |
| Token de respuesta | 2 | `list_target_response_tokens`, `create_target_response_token` |
| Revisión | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| Plantilla | 1 | `list_target_templates` |
| **Total** | **39** | |

## Recursos relacionados {#tools-related}

* [Trabajar con clientes de MCP](target-mcp.md)
* [[!DNL Adobe Target] Referencia de API de administración](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
