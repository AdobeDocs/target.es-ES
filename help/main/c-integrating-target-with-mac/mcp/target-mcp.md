---
solution: Target
product: target
title: Trabajar con clientes de MCP
description: Obtenga información sobre cómo conectar Adobe Target a clientes MCP mediante el servidor MCP
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
source-git-commit: a0fbca3156a7d2a1c582ce591112a18b4a122a64
workflow-type: tm+mt
source-wordcount: '2267'
ht-degree: 1%

---

# Trabajar con clientes de MCP {#target-mcp}

>[!BEGINSHADEBOX]

Tabla de contenido:

* **[Trabajar con clientes MCP](target-mcp.md)**
* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Autoalojar el servidor MCP](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible actualmente en **Claude Web**, **Claude Desktop**, **Claude Code** y **Cursor**. En futuras versiones se agregará compatibilidad con aplicaciones compatibles con MCP adicionales.

La integración de MCP [!DNL Adobe Target] le permite inspeccionar, analizar y administrar pruebas A/B, actividades de personalización y criterios de Recommendations directamente desde su asistente de IA. Convierta las API de lectura y escritura de [!DNL Target] en flujos de trabajo en lenguaje sencillo: audite el portafolio de experimentos, revise los informes de rendimiento, administre audiencias y ofertas y realice acciones controladas sin navegar por la interfaz de usuario ni escribir llamadas a la API. Esta página explica cómo funciona la integración, qué puede hacer con ella y cómo empezar.

## ¿Qué es el protocolo de contexto del modelo? {#mcp-overview}

Los equipos de marketing y optimización dependen cada vez más de las aplicaciones basadas en chat y las herramientas para desarrolladores, como Anthropic Claude, OpenAI ChatGPT, Cursor y Microsoft Copilot Studio, para optimizar su trabajo diario. Estas aplicaciones admiten el **Protocolo de contexto de modelo (MCP)**, un estándar abierto que permite a las aplicaciones exponer las herramientas back-end a modelos de lenguaje de gran tamaño (LLM) de manera uniforme.

[!DNL Adobe Target] ahora proporciona un servidor MCP que muestra las operaciones de experimentación, personalización y recomendaciones directamente dentro de cualquier aplicación compatible con MCP. [!DNL Adobe Target] actúa como la capa de toma de decisiones y ejecución, mientras que el asistente de IA gestiona el razonamiento y la explicación, lo que proporciona a los equipos un acceso más rápido a las perspectivas de optimización sin navegar por varias pantallas de producto ni escribir consultas contra la API de REST [!DNL Adobe Target].

## Funcionalidades clave {#mcp-capabilities}

El servidor MCP [!DNL Adobe Target] proporciona acceso de lectura y escritura a actividades, audiencias, ofertas, recomendaciones y configuración de implementación. Con la integración, puede:

* **Inspeccionar y auditar experimentos**: obtenga vínculos de estado, rendimiento, historial de cambios y vista previa de control de calidad para cualquier actividad sin navegar por la interfaz de usuario.
* **Analizar resultados**: recupere el rendimiento, los ingresos y los informes de A4T para las actividades A/B, XT, AP y de segmentación automática.
* **Administrar actividades**: cree, actualice y active actividades A/B y XT; ajuste divisiones de tráfico, variantes, programaciones y prioridades.
* **Administrar audiencias y ofertas**: enumere, inspeccione y cree audiencias, ofertas de HTML y ofertas JSON.
* **Explorar criterios de Recommendations**: enumere e inspeccione criterios y algoritmos basados en el carro de compras.
* **Implementación de auditoría**: revise la configuración de at.js, los tokens de respuesta y el historial de revisiones por entidad.

>[!NOTE]
>
>Las operaciones de escritura (crear, actualizar, activar, desactivar) incluyen anotaciones de seguridad. No se ejecuta ningún cambio sin la confirmación explícita del usuario.

## Herramientas disponibles {#mcp-tools}

El servidor MCP [!DNL Adobe Target] expone 52 herramientas. Las herramientas de lectura están disponibles para todos los usuarios conectados con permisos de Vista; las herramientas de escritura requieren la función Editor o Aprobador.

### Herramientas de actividad: lectura

| Herramienta | Descripción |
|---|---|
| `list_target_activities` | Enumerar actividades con filtrado del lado del servidor por estado, tipo, nombre, fecha, prioridad, mbox y espacio de trabajo |
| `list_all_target_activities` | Recupere todas las actividades que coincidan con los filtros, paginando automáticamente mediante los resultados |
| `get_ab_activity` | Obtener información completa de una actividad A/B específica |
| `get_xt_activity` | Obtenga información detallada sobre una actividad específica de segmentación de experiencias (XT) |
| `get_abt_activity` | Obtenga información completa sobre una actividad específica de Automated Personalization (AP) |

### Herramientas de actividad: escritura

| Herramienta | Descripción |
|---|---|
| `create_ab_activity` | Crear una nueva actividad de prueba A/B |
| `create_xt_activity` | Crear una nueva actividad de segmentación de experiencias (XT) |
| `create_activity_from_modifications` | Creación de una actividad XT a partir de modificaciones de JavaScript |
| `update_ab_activity` | Actualizar una actividad A/B existente |
| `update_xt_activity` | Actualizar una actividad XT existente |
| `update_abt_activity` | Actualizar una actividad de Automated Personalization existente |
| `update_activity_state` | Activar, desactivar, pausar o archivar una actividad |
| `update_activity_schedule` | Actualizar las fechas de inicio y finalización de una actividad |
| `update_activity_priority` | Actualizar la prioridad de una actividad |
| `update_activity_name` | Cambiar nombre de actividad |
| `add_activity_variant` | Añadir una nueva variante (experiencia) a una actividad |
| `update_traffic_split` | Actualizar la asignación del tráfico entre variantes |
| `update_variant_offer` | Cambiar la oferta o las modificaciones del VEC para una variante |
| `remove_activity_variant` | Eliminación de una variante de una actividad |

### Herramientas de oferta

| Herramienta | Descripción |
|---|---|
| `list_target_offers` | Enumerar ofertas con filtrado y ordenación del lado del servidor |
| `list_all_target_offers` | Buscar todas las ofertas que coincidan con filtros, paginación automática |
| `get_target_offer` | Obtener detalles de una oferta específica |
| `create_target_offer` | Crear una nueva oferta de HTML |
| `create_target_json_offer` | Crear una nueva oferta JSON |
| `update_target_offer` | Actualizar una oferta de HTML existente |

### Herramientas de audiencia

| Herramienta | Descripción |
|---|---|
| `list_target_audiences` | Enumerar audiencias con filtrado y ordenación del lado del servidor |
| `create_target_audience` | Creación de una audiencia con reglas de segmentación opcionales |

### Herramientas de ubicación y mbox

| Herramienta | Descripción |
|---|---|
| `list_target_mboxes` | Enumerar mboxes mediante filtrado y ordenación |
| `list_all_target_mboxes` | Recuperar todos los mboxes que coincidan con los filtros, paginación automática |
| `get_target_mbox` | Obtener detalles de un mbox específico por nombre |
| `list_target_mbox_profile_attributes` | Enumerar todos los atributos de perfil asociados a mboxes |

### Propiedades

| Herramienta | Descripción |
|---|---|
| `list_target_properties` | Mostrar todas las propiedades de Target |

### Herramientas de informes y perspectivas

| Herramienta | Descripción |
|---|---|
| `get_ab_performance_report` | Obtenga un informe de rendimiento para una actividad A/B, de asignación automática o de segmentación automática |
| `get_ab_orders_report` | Obtener informes de pedidos e ingresos de una actividad A/B o de segmentación automática |
| `get_xt_performance_report` | Obtenga un informe de rendimiento para una actividad XT |
| `get_xt_orders_report` | Obtener pedidos e informe de ingresos de una actividad XT |
| `get_apt_performance_report` | Obtenga un informe de rendimiento para una actividad de AP o de Segmentación automática |
| `get_activity_insights` | Busque una actividad por su nombre y obtenga información detallada sobre el rendimiento |
| `get_a4t_report` | Obtenga el informe de Analytics for Target (A4T) de una actividad |

### Herramientas de Recommendations

| Herramienta | Descripción |
|---|---|
| `list_target_criteria` | Enumerar todos los criterios de Recommendations |
| `get_target_criteria` | Obtener detalles de criterios específicos de Recommendations |
| `update_target_criteria_cart` | Actualizar criterios basados en el carro de compras de Recommendations |

### Herramientas de implementación y configuración

| Herramienta | Descripción |
|---|---|
| `get_atjs_settings` | Obtener la configuración de AT.js |
| `get_atjs_versions` | Obtener las versiones de AT.js disponibles |
| `list_target_response_tokens` | Enumerar todos los tokens de respuesta en el inquilino de Target |
| `create_target_response_token` | Crear un nuevo token de respuesta personalizado |

### Herramientas de auditoría y revisión

| Herramienta | Descripción |
|---|---|
| `get_target_revisions` | Obtener el registro de auditoría de un tipo de recurso, filtrado por autor |
| `get_target_entity_revisions` | Obtener todas las revisiones de una entidad específica por ID |

### Utilidades

| Herramienta | Descripción |
|---|---|
| `preview_activity` | Generación de URL de vista previa de control de calidad para una actividad de Target |
| `create_page_delivery_segment` | Creación de un segmento de entrega de páginas para la segmentación de actividades VEC |
| `list_target_templates` | Enumeración de recursos y plantillas de MCP disponibles |
| `debug_token_info` | Inspeccionar los ámbitos y notificaciones del token de OAuth actual |

## Casos de uso {#mcp-use-cases}

Los siguientes ejemplos muestran cómo interactuar con el servidor MCP [!DNL Adobe Target] mediante lenguaje natural:

| Objetivo | Mensaje de ejemplo |
|---|---|
| **Auditoría de estado del experimento** | &quot;¿Qué pruebas A/B hay activas actualmente en la página principal? Muéstreme el estado, la asignación de tráfico y cuánto tiempo se ha estado ejecutando cada uno&quot;. |
| **Revisión de rendimiento** | &quot;Mostrar todas las pruebas activas que hayan alcanzado relevancia estadística: ¿qué experiencias están ganando?&quot; |
| **Análisis de ingresos** | &quot;Obtenga el informe de pedidos e ingresos de la actividad AT4821 y resuma qué experiencia genera la mayor cantidad de ingresos por visitante&quot;. |
| **Informes de A4T** | &quot;Extraiga el informe A4T para mi prueba de optimización de cierre de compra y resuma los datos de conversión del lado de Analytics&quot;. |
| **Administración de actividades** | &quot;Pausar la actividad 98765 y actualizar la prioridad de la actividad 11111 a 200&quot;. |
| **Información de la actividad** | &quot;Obtenga información para mi prueba de &#39;Banner de venta de verano&#39;. ¿Qué aspecto tiene el rendimiento y si hay alguna anomalía?&quot; |
| **Gestión de público** | &quot;Enumere todas las audiencias segmentadas por usuarios móviles y muéstreme con qué actividades están asociadas&quot;. |
| **Control de calidad y vista previa** | &quot;Generar URL de vista previa de control de calidad para los 12345 de actividad para poder revisar todas las variantes antes antes de activarlas&quot;. |
| **Revisión de recomendaciones** | &quot;Enumerar todos los criterios de Recommendations configurados en esta cuenta y resumir los tipos de algoritmo en uso.&quot; |
| **Auditoría de implementación** | &quot;¿Qué versión de at.js está configurada y qué tokens de respuesta están activos actualmente?&quot; |
| **Auditoría de cambios** | &quot;Mostrarme todos los cambios realizados en los 98765 de actividad en los últimos 30 días y quién los ha realizado&quot;. |

## Tutoriales de casos de uso {#mcp-use-case-walkthroughs}

Los siguientes tutoriales muestran cómo completar tareas comunes utilizando las peticiones de datos en lenguaje natural con el servidor MCP [!DNL Adobe Target].

+++Creación de una prueba A/B

**Mensaje:**
&quot;Cree una prueba A/B llamada &#39;Prueba de imagen a pantalla completa de página principal&#39; con dos experiencias: &#39;Control&#39; que muestre la imagen a pantalla completa actual y &#39;Variante&#39; que muestre una nueva imagen a pantalla completa con tema de verano. Oriente el mbox de la página principal&quot;.

El asistente de IA utiliza la herramienta `create_ab_activity` para crear la actividad con la configuración descrita. La herramienta devuelve el nuevo ID de actividad y una confirmación de las experiencias creadas.

+++

+++Comprobación del rendimiento de la actividad

**Mensaje:**
&quot;Mostrarme las métricas de rendimiento de mi actividad &#39;Optimización de flujo de cierre de compra&#39; durante los últimos 30 días&quot;.

El asistente de IA usa `get_ab_performance_report` o `get_xt_performance_report` (según el tipo de actividad) para recuperar las tasas de conversión, los recuentos de visitantes y otras métricas de la ventana de tiempo especificada.

+++

+++Administración de ofertas

**Mensaje:**
&quot;Cree una oferta de HTML llamada &#39;Banner de venta de verano&#39; con un banner promocional que diga &#39;20% de descuento en todos los artículos de verano&#39;&quot;.

El asistente de IA utiliza la herramienta `create_target_offer` para crear la oferta con el contenido de HTML especificado y devuelve una confirmación con el nuevo ID de oferta.

+++

+++Creación de una audiencia

**Mensaje:**
&quot;Cree una audiencia denominada &#39;Visitantes móviles de California&#39; que esté dirigida a usuarios de dispositivos móviles ubicados en California&quot;.

El asistente de IA utiliza la herramienta `create_target_audience` con las reglas de segmentación adecuadas derivadas de la descripción.

+++

+++Generación de vínculos de vista previa de control de calidad

**Mensaje:**
&quot;Genere URL de vista previa para los 12345 de la actividad para poder probar cada experiencia&quot;.

El asistente de IA utiliza la herramienta `preview_activity` para generar direcciones URL en las que se puede hacer clic y que omiten la segmentación de audiencia, lo que le permite ver cada experiencia directamente en el explorador.

+++

+++Creación de una actividad de segmentación de experiencias

**Mensaje:**
&quot;Cree una actividad de segmentación de experiencias llamada &#39;Geo Personalization&#39; que muestre diferentes banners a los visitantes de diferentes regiones.&quot;

El asistente de IA usa `create_xt_activity` para generar la actividad con asignación de experiencias basada en audiencias según las regiones que describa.

+++

+++Programación de una actividad

**Mensaje:**
&quot;Actualice la programación de la actividad 12345 para que comience el 1 de mayo y finalice el 31 de mayo&quot;.

El asistente de IA utiliza la herramienta `update_activity_schedule` para aplicar las nuevas fechas de inicio y finalización a la actividad.

+++

## Requisitos previos   {#mcp-prerequisites}

Antes de conectar el servidor MCP [!DNL Adobe Target] a su cliente MCP, asegúrese de lo siguiente:

* Tiene una licencia activa de [!DNL Adobe Target] (suscripción a Adobe Experience Cloud) con una organización de Adobe Experience Platform.
* Tiene una aplicación compatible con MCP (actualmente Claude Web, Claude Desktop, Claude Code o Cursor).
* Tiene [!DNL Adobe Target] permisos configurados en Adobe Admin Console:
   * Función de **Observer**: herramientas de solo lectura
   * Función **Editor**: leer + crear herramientas
   * Función de **aprobador**: leer + crear + activar/desactivar herramientas

## Conectar el servidor MCP [!DNL Adobe Target] {#mcp-connect}

>[!NOTE]
>
>El servidor MCP [!DNL Adobe Target] utiliza OAuth 2.0 para la autenticación. La primera vez que utilice una herramienta MCP de Target, se le redirigirá a Adobe Experience Cloud para que inicie sesión, seleccione su organización y conceda los permisos solicitados. No se requieren credenciales estáticas.

**Para conectarse desde Claude Desktop o Claude Web:**

1. Abra la configuración de cliente de MCP y agregue un nuevo servidor MCP.
1. Escriba la dirección URL del servidor: `https://targetmcp.adobe.io/mcp`
1. Cuando se le solicite, complete el inicio de sesión de OAuth de Adobe IMS con sus credenciales de Adobe Experience Cloud.
1. Una vez autenticadas, todas las herramientas están disponibles de inmediato. Pruebe &quot;Enumerar todas las actividades de Target activas&quot; para comprobar la conexión.

**Para conectarse desde el código Claude:**

Añada lo siguiente a la configuración del MCP de Claude Code:

```json
{
  "mcpServers": {
    "adobe-target": {
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

Complete el flujo del explorador OAuth cuando se le solicite la primera vez que lo utilice.

**Para conectarse desde el cursor:**

1. Abra **Cursor** y vaya a **Configuración** → **MCP** → **Agregar nuevo servidor MCP global**.
1. Añada la siguiente configuración:

```json
{
  "mcpServers": {
    "target": {
      "type": "streamable-http",
      "url": "https://targetmcp.adobe.io/mcp"
    }
  }
}
```

1. Guarde la configuración. El servidor MCP [!DNL Target] aparecerá en los servidores MCP disponibles.

>[!TIP]
>
>Si aparecen actividades o datos de una organización incorrecta, cierre la sesión de Adobe Experience Cloud por completo, vuelva a conectar el servidor MCP y seleccione cuidadosamente la organización correcta durante la reautenticación.

## Resolución de problemas {#mcp-troubleshooting}

+++El flujo de OAuth falla o redirige incorrectamente

1. Cierre la sesión de Adobe Experience Cloud por completo.
1. Borre las cookies del explorador de los dominios adobe.com.
1. Vuelva a intentar el flujo de autenticación.
1. Asegúrese de seleccionar la organización correcta cuando se le solicite.
+++

+++Aparecen actividades o datos de la organización incorrecta

1. Cierre la sesión de Adobe Experience Cloud por completo.
1. Desconecte y vuelva a conectar el servidor MCP en la configuración de cliente.
1. Seleccione cuidadosamente la organización correcta durante la reautenticación.
+++

+++Una herramienta de devuelve un mensaje de error

1. Compruebe que tiene los permisos necesarios en [!DNL Adobe Target] para la operación (vea [Requisitos previos](#mcp-prerequisites)).
1. Compruebe que los recursos a los que se hace referencia (actividades, ofertas y audiencias) existan en la organización.
1. Confirme que los ID de actividad y otros identificadores son correctos.
+++

+++No se puede conectar con el servidor MCP

1. Compruebe la conexión a Internet.
1. Compruebe que la URL del servidor MCP se haya introducido correctamente en la configuración del cliente.
1. Intente quitar y volver a agregar el servidor en la configuración de cliente de MCP.
+++

## Seguridad y permisos {#mcp-security}

El servidor MCP [!DNL Adobe Target] solo puede tener acceso a los datos para los que su cuenta de usuario de Adobe tiene permiso de visualización o modificación. Todas las operaciones respetan las asignaciones de funciones y los permisos de área de trabajo de [!DNL Target].

El servidor solicita los siguientes ámbitos de OAuth:

* `AdobeID`: identidad básica de Adobe
* `openid` — Autenticación de OpenID Connect
* `additional_info.projectedProductContext` — Descubrimiento de inquilino
* `read_organizations`: operaciones a nivel de organización
* `additional_info.roles` - Control de acceso basado en roles

Los tokens de OAuth se validan con Adobe IMS en cada solicitud, el servidor MCP no los almacena de forma persistente y todas las comunicaciones utilizan HTTPS.

## Preguntas más frecuentes {#mcp-faq}

+++¿Qué clientes MCP son compatibles?

El servidor MCP [!DNL Adobe Target] está disponible actualmente para **Claude Web**, **Claude Desktop**, **Claude Code** y **Cursor**. En futuras versiones se puede agregar compatibilidad con aplicaciones compatibles con MCP adicionales.
+++

+++¿A qué objetos de [!DNL Adobe Target] puedo acceder a través de MCP?

Puede acceder a actividades (A/B, XT, AP), audiencias, ofertas, propiedades, mboxes, criterios de Recommendations, tokens de respuesta, configuración de at.js, informes de A4T e historial de revisiones de entidades. Las operaciones de lectura y escritura son compatibles con 52 herramientas: las operaciones de escritura requieren la función adecuada y una confirmación explícita.
+++

+++¿Puede el servidor MCP crear o modificar actividades?

Sí. Además de las operaciones de lectura, el servidor expone operaciones de escritura que permiten crear actividades, pausarlas, actualizar prioridades, ajustar divisiones de tráfico, etc. Las operaciones de escritura siguen el mismo modelo de permisos que la interfaz de usuario de [!DNL Adobe Target]: necesita la función adecuada para realizar cambios y no se ejecuta ninguna acción sin la confirmación explícita del usuario.
+++

+++¿Se necesita acceso de desarrollador para utilizar el servidor MCP?

No. El servidor MCP está diseñado tanto para personalidades técnicas como de marketing. Los especialistas en marketing pueden interactuar con él utilizando indicadores de lenguaje natural en cualquier cliente de MCP admitido, mientras que los desarrolladores pueden utilizarlo en herramientas como Claude Code o Cursor.
+++

+++¿Se envían mis datos de [!DNL Adobe Target] al proveedor de cliente de MCP?

Cuando envía una solicitud, el cliente MCP puede enviar contexto relevante (incluidos [!DNL Adobe Target] datos devueltos por el servidor MCP) a su modelo para su procesamiento. Revise las políticas de privacidad y administración de datos de su proveedor de cliente MCP antes de conectarse a los datos de producción. La administración de datos de Adobe se rige por la [Política de privacidad de Adobe](https://www.adobe.com/es/privacy.html) y los [Términos de protección de datos](https://www.adobe.com/go/dpt-ww).
+++

+++¿Pueden las operaciones de escritura provocar cambios no deseados en las actividades activas?

Las herramientas de escritura incluyen anotaciones de seguridad y puertas de confirmación. Antes de cualquier acción de cambio de estado (como activar una actividad, cambiar la prioridad o actualizar la asignación del tráfico), el servidor presenta una confirmación estructurada que muestra el objeto afectado, el impacto estimado del tráfico y un paso de aprobación explícito requerido. No se realizan cambios hasta que se confirmen.
+++

+++¿Qué permisos necesito en [!DNL Adobe Target]?

Como mínimo, la función **Observer** concede acceso a todas las herramientas de lectura. El rol **Editor** permite crear actividades, audiencias y ofertas. Se requiere el rol **Aprobador** para activar, desactivar o archivar actividades. Póngase en contacto con el administrador de [!DNL Adobe Target] si no está seguro del nivel de acceso actual.
+++

+++¿Puedo utilizar el servidor MCP en varias organizaciones o propiedades de Target?

El servidor MCP define las operaciones a la organización asociada con sus credenciales de Adobe IMS autenticadas. Si tiene acceso a varias propiedades dentro de esa organización, puede consultar por propiedad utilizando la herramienta `list_target_properties` y filtrar las solicitudes posteriores en consecuencia.
+++

## Recursos relacionados {#mcp-related}

* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Autohospedar el servidor  [!DNL Adobe Target] MCP](target-mcp-self-hosted.md)
* [Documentación de protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [[!DNL Adobe Target] Referencia de API de administración](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentación del cursor](https://docs.cursor.com/){target="_blank"}
