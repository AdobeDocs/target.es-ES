---
solution: Target
product: target
title: 'Servidor MCP de Adobe Target: Casos de uso y tutoriales'
description: Explore casos de uso comunes y tutoriales de mensajes paso a paso para el servidor MCP de Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 53dc7056ca62339a682756fe1b39e6af349f3ae6
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---

# Servidor MCP [!DNL Adobe Target]: casos de uso y tutoriales {#target-mcp-use-cases}

>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.

Esta página muestra lo que puede lograr con el servidor MCP [!DNL Adobe Target] mediante peticiones de datos en lenguaje natural, desde búsquedas rápidas hasta tareas de análisis e informes de varios pasos.

>[!IMPORTANT]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a los productos de Adobe es una configuración elegida por el cliente, y los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## Casos de uso {#mcp-use-cases}

Los siguientes ejemplos muestran cómo interactuar con el servidor MCP [!DNL Adobe Target] mediante lenguaje natural:

| Objetivo | Mensaje de ejemplo |
|---|---|
| **Auditoría de estado del experimento** | &quot;¿Qué pruebas A/B hay activas actualmente en la página principal? Muéstreme el estado, la asignación de tráfico y cuánto tiempo se ha estado ejecutando cada uno&quot;. |
| **Revisión de rendimiento** | &quot;Mostrar todas las pruebas activas que hayan alcanzado relevancia estadística: ¿qué experiencias están ganando?&quot; |
| **Análisis de ingresos** | &quot;Obtenga el informe de pedidos e ingresos de la actividad AT4821 y resuma qué experiencia genera la mayor cantidad de ingresos por visitante&quot;. |
| **Informes de A4T** | &quot;Extraiga el informe A4T para mi prueba de optimización de cierre de compra y resuma los datos de conversión del lado de Analytics&quot;. |
| **Información de la actividad** | &quot;Obtenga información para mi prueba de &#39;Banner de venta de verano&#39;. ¿Qué aspecto tiene el rendimiento y si hay alguna anomalía?&quot; |
| **Gestión de público** | &quot;Enumere todas las audiencias segmentadas por usuarios móviles y muéstreme con qué actividades están asociadas&quot;. |
| **Control de calidad y vista previa** | &quot;Generar URL de vista previa de control de calidad para los 12345 de actividad para poder revisar todas las variantes antes antes de activarlas&quot;. |
<!-- | **Recommendations review** | "List all Recommendations criteria configured in this account and summarize the algorithm types in use." | -->
| **Auditoría de implementación** | &quot;¿Qué versión de at.js está configurada y qué tokens de respuesta están activos actualmente?&quot; |
| **Auditoría de cambios** | &quot;Mostrar todos los cambios realizados en los 98765 de actividad en los últimos 30 días y quién los ha realizado&quot;. |

## Tutoriales de casos de uso {#mcp-use-case-walkthroughs}

Los siguientes tutoriales muestran cómo completar tareas comunes utilizando las peticiones de datos en lenguaje natural con el servidor MCP [!DNL Adobe Target].

<!--
+++Creating an A/B test

**Prompt:**
"Create an A/B test called 'Homepage Hero Image Test' with two experiences: 'Control' showing the current hero and 'Variant' showing a new summer-themed hero image. Target the homepage mbox."

The AI assistant uses the `create_ab_activity` tool to create the activity with the configuration you described. The tool returns the new activity ID and a confirmation of the created experiences.

+++
-->

+++Comprobación del rendimiento de la actividad

**Mensaje:**
&quot;Mostrarme las métricas de rendimiento de mi actividad &#39;Optimización de flujo de cierre de compra&#39; durante los últimos 30 días&quot;.

El asistente de IA usa `get_ab_performance_report` o `get_xt_performance_report` (según el tipo de actividad) para recuperar las tasas de conversión, los recuentos de visitantes y otras métricas de la ventana de tiempo especificada.

+++

<!--
+++Managing offers

**Prompt:**
"Create an HTML offer called 'Summer Sale Banner' with a promotional banner that says '20% off all summer items'."

The AI assistant uses the `create_target_offer` tool to create the offer with your specified HTML content and returns a confirmation with the new offer ID.

+++

+++Building an audience

**Prompt:**
"Create an audience called 'Mobile Visitors from California' that targets users on mobile devices located in California."

The AI assistant uses the `create_target_audience` tool with the appropriate targeting rules derived from your description.

+++
-->

+++Generación de vínculos de vista previa de control de calidad

**Mensaje:**
&quot;Genere URL de vista previa para los 12345 de la actividad para poder probar cada experiencia&quot;.

El asistente de IA utiliza la herramienta `preview_activity` para generar direcciones URL en las que se puede hacer clic y que omiten la segmentación de audiencia, lo que le permite ver cada experiencia directamente en el explorador.

+++

<!--
+++Creating an Experience Targeting activity

**Prompt:**
"Create an Experience Targeting activity called 'Geo Personalization' that shows different hero banners to visitors from different regions."

The AI assistant uses `create_xt_activity` to build the activity with audience-based experience mapping according to the regions you describe.

+++

+++Scheduling an activity

**Prompt:**
"Update the schedule for activity 12345 to start on May 1st and end on May 31st."

The AI assistant uses the `update_activity_schedule` tool to apply the new start and end dates to the activity.

+++
-->

## Recursos relacionados {#mcp-use-cases-related}

* [Información general](target-mcp.md)
* [Introducción](target-mcp-get-started.md)
* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Documentación del protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
