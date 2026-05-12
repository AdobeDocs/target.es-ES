---
solution: Target
product: target
title: Información general del servidor MCP de Adobe Target
description: Descubra qué es el servidor MCP de Adobe Target, sus funciones clave y cómo se conecta a su asistente de IA.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: d5d7a57ce6a3188f02e680c24849d773cb53457a
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 0%

---

# Servidor MCP [!DNL Adobe Target] {#target-mcp}

La integración de MCP [!DNL Adobe Target] le permite inspeccionar y analizar pruebas A/B, actividades de personalización y criterios de Recommendations directamente desde su asistente de IA. Convierta los datos de experimentación y personalización de [!DNL Target] en flujos de trabajo en un lenguaje sencillo: audite el portafolio de experimentos, revise los informes de rendimiento y explore audiencias y ofertas sin navegar por la interfaz de usuario ni escribir llamadas a la API.

>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**. En futuras versiones se agregará compatibilidad con aplicaciones compatibles con MCP adicionales.


## ¿Qué es el protocolo de contexto del modelo? {#mcp-overview}

Los equipos de marketing y optimización dependen cada vez más de las aplicaciones basadas en chat y las herramientas para desarrolladores, como Anthropic Claude, OpenAI ChatGPT, Cursor y Microsoft Copilot Studio, para optimizar su trabajo diario. Estas aplicaciones admiten el **Protocolo de contexto de modelo (MCP)**, un estándar abierto que permite a las aplicaciones exponer las herramientas back-end a modelos de lenguaje de gran tamaño (LLM) de manera uniforme.

[!DNL Adobe Target] ahora proporciona un servidor MCP que muestra las operaciones de experimentación, personalización y recomendaciones directamente dentro de cualquier aplicación compatible con MCP. [!DNL Adobe Target] actúa como la capa de toma de decisiones y ejecución, mientras que el asistente de IA gestiona el razonamiento y la explicación, lo que proporciona a los equipos un acceso más rápido a las perspectivas de optimización sin navegar por varias pantallas de producto ni escribir consultas contra la API de REST [!DNL Adobe Target].


>[!IMPORTANT]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a los productos de Adobe es una configuración elegida por el cliente, y los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## Funcionalidades clave {#mcp-capabilities}

El servidor MCP [!DNL Adobe Target] proporciona acceso de lectura a actividades, audiencias, ofertas, recomendaciones y configuración de implementación. Con la integración, puede:

* **Inspeccionar y auditar experimentos**: obtenga vínculos de estado, rendimiento, historial de cambios y vista previa de control de calidad para cualquier actividad sin navegar por la interfaz de usuario.
* **Analizar resultados**: recupere el rendimiento, los ingresos y los informes de A4T para las actividades A/B, XT, AP y de segmentación automática.
* **Explorar actividades**: enumera, inspecciona y analiza actividades A/B y XT.
* **Explorar audiencias y ofertas**: enumere e inspeccione audiencias, ofertas de HTML y ofertas JSON.
* **Explorar criterios de Recommendations**: enumere e inspeccione criterios y algoritmos basados en el carro de compras.
* **Implementación de auditoría**: revise la configuración de at.js, los tokens de respuesta y el historial de revisiones por entidad.

>[!NOTE]
>
>Las herramientas de escritura (crear, actualizar, activar, desactivar) no se exponen a través del catálogo MCP público en **Public Beta**. Todas las herramientas disponibles actualmente son de solo lectura. El acceso de escritura estará disponible en una versión futura.

El servidor MCP [!DNL Adobe Target] expone 23 herramientas de solo lectura en 10 categorías, desde la inspección de actividades y la creación de informes hasta la exploración de audiencias y las vistas previas de control de calidad. Para obtener la referencia de parámetro completa, vea [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md).

Para explorar lo que puede hacer con el servidor MCP [!DNL Adobe Target], incluidos tutoriales paso a paso para solicitar información, vea [Casos de uso y tutoriales](target-mcp-use-cases.md).

Para conectar el servidor MCP [!DNL Adobe Target] a su asistente de IA, incluidos los requisitos previos, la configuración específica del cliente y la solución de problemas, consulte [Introducción](target-mcp-get-started.md).

## Preguntas más frecuentes {#mcp-faq}

+++¿Qué clientes MCP son compatibles?

El servidor MCP [!DNL Adobe Target] está disponible actualmente para **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**. En futuras versiones se puede agregar compatibilidad con aplicaciones compatibles con MCP adicionales.
+++

+++¿A qué objetos de [!DNL Adobe Target] puedo acceder a través de MCP?

Puede acceder a actividades (A/B, XT, AP), audiencias, ofertas, propiedades, mboxes, criterios de Recommendations, tokens de respuesta, configuración de at.js, informes de A4T e historial de revisiones de entidades. Las 23 herramientas disponibles actualmente son de solo lectura.
+++

+++¿Puede el servidor MCP crear o modificar actividades?

No está en Beta público. El catálogo público de MCP expone actualmente 23 herramientas de solo lectura. Las operaciones de escritura (creación, actualización, activación, desactivación) aún no están disponibles a través del servidor MCP público. El acceso de escritura estará disponible en una versión futura.
+++

+++¿Se necesita acceso de desarrollador para utilizar el servidor MCP?

No. El servidor MCP está diseñado tanto para personalidades técnicas como de marketing. Los especialistas en marketing pueden interactuar con él utilizando indicadores de lenguaje natural en cualquier cliente de MCP admitido, mientras que los desarrolladores pueden utilizarlo en herramientas como Claude Code o Cursor.
+++

+++¿Se envían mis datos de [!DNL Adobe Target] al proveedor de cliente de MCP?

Cuando envía una solicitud, el cliente MCP puede enviar contexto relevante (incluidos [!DNL Adobe Target] datos devueltos por el servidor MCP) a su modelo para su procesamiento. Revise las políticas de privacidad y administración de datos de su proveedor de cliente MCP antes de conectarse a los datos de producción. La administración de datos de Adobe se rige por la [Política de privacidad de Adobe](https://www.adobe.com/privacy.html) y los [Términos de protección de datos](https://www.adobe.com/go/dpt-ww).
+++

+++¿Pueden las operaciones de escritura provocar cambios no deseados en las actividades activas?

Las herramientas de escritura no están disponibles a través del catálogo público de MCP de Beta público; las 23 herramientas expuestas actualmente son de solo lectura. Cuando se introduzcan herramientas de escritura en una versión futura, incluirán anotaciones de seguridad y puertas de confirmación para que no se ejecute ninguna acción de cambio de estado sin la confirmación explícita del usuario.
+++

+++¿Qué permisos necesito en [!DNL Adobe Target]?

La función **Observer** o superior concede acceso a las 23 herramientas de solo lectura disponibles en Public Beta. Las herramientas de escritura aún no se exponen a través del catálogo MCP público, por lo que los privilegios de función Editor y Aprobador no desbloquean herramientas MCP adicionales en este momento. Póngase en contacto con el administrador de [!DNL Adobe Target] si no está seguro del nivel de acceso actual.
+++

+++¿Puedo utilizar el servidor MCP en varias organizaciones o propiedades de Target?

El servidor MCP define las operaciones a la organización asociada con sus credenciales de Adobe IMS autenticadas. Si tiene acceso a varias propiedades dentro de esa organización, puede consultar por propiedad utilizando la herramienta `list_target_properties` y filtrar las solicitudes posteriores en consecuencia.
+++

## Recursos relacionados {#mcp-related}

* [Introducción](target-mcp-get-started.md)
* [Casos de uso y tutoriales](target-mcp-use-cases.md)
* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Documentación del protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
* [Documentación del cursor](https://docs.cursor.com/){target="_blank"}
