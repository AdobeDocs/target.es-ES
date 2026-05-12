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
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 0%

---

# Servidor MCP [!DNL Adobe Target]: casos de uso y tutoriales {#target-mcp-use-cases}


>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.


Esta página muestra lo que puede lograr con el servidor MCP [!DNL Adobe Target] mediante peticiones de datos en lenguaje natural, desde búsquedas rápidas hasta tareas de administración de actividades de varios pasos.

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

## Recursos relacionados {#mcp-use-cases-related}

* [Información general](target-mcp.md)
* [Introducción](target-mcp-get-started.md)
* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Documentación del protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
