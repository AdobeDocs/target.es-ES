---
solution: Target
product: target
title: Referencia de herramientas del servidor Adobe Target MCP
description: Referencia de parámetro completa para las 21 herramientas de solo lectura expuestas por el servidor MCP de Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# Referencia de herramientas del servidor MCP [!DNL Adobe Target] {#target-mcp-tools-reference}


>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.

Esta página es una referencia completa para todas las herramientas de solo lectura expuestas por el servidor MCP [!DNL Adobe Target]. Para cada herramienta encontrará una descripción, detalles de parámetros, un valor devuelto y un ejemplo de petición de datos en lenguaje natural. Para obtener instrucciones de configuración y casos de uso, consulte [Introducción](target-mcp-get-started.md) y [Casos de uso y tutoriales](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a los productos de Adobe es una configuración elegida por el cliente, y los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## Requisitos previos {#tools-prerequisites}

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

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

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

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

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

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

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

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

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
| Actividad | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| Oferta | 2 | `list_target_offers`, `get_target_offer` |
| Público | 1 | `list_target_audiences` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propiedad | 1 | `list_target_properties` |
| Creación de informes | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| Vista previa | 1 | `preview_activity` |
| Token de respuesta | 1 | `list_target_response_tokens` |
| Revisión | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| Plantilla | 1 | `list_target_templates` |
| **Total** | **21** | |

## Recursos relacionados {#tools-related}

* [Trabajar con clientes de MCP](target-mcp.md)
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
