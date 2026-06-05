---
solution: Target
product: target
title: Introducción al servidor MCP de Adobe Target
description: Obtenga información sobre cómo conectar el servidor MCP de Adobe Target a su asistente de IA, incluidos los requisitos previos, la configuración del cliente y la resolución de problemas.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: 40e87a3a70d51ccda99f046609ba9633719ea540
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# Introducción al servidor MCP [!DNL Adobe Target] {#target-mcp-get-started}

>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.

Esta página le explica todo lo que necesita para conectar el servidor MCP de [!DNL Adobe Target] a su asistente de IA y comprobar la configuración.

>[!IMPORTANT]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a los productos de Adobe es una configuración elegida por el cliente, y los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## Requisitos previos {#mcp-prerequisites}

Antes de conectar el servidor MCP [!DNL Adobe Target] a su cliente MCP, asegúrese de lo siguiente:

* Tiene una licencia activa de [!DNL Adobe Target] (suscripción de Adobe Experience Cloud) con una organización de Adobe Experience Platform.
* Tiene una aplicación compatible con MCP (actualmente Claude Web, Claude Desktop, Claude Code, Cursor o ChatGPT).
* Tiene [!DNL Adobe Target] permisos configurados en Adobe Admin Console. La función requerida depende de las operaciones que desee realizar:
   * Función **Observer** o superior: acceso a todas las herramientas de solo lectura (inspeccionar, informar, auditar)
   * Función **Editor** o superior: acceso a las herramientas de lectura y escritura (crear, actualizar)
   * Función de **aprobador**: acceso a todas las herramientas, incluidas las de activación y desactivación

## Conectar el servidor MCP [!DNL Adobe Target] {#mcp-connect}

>[!NOTE]
>
>El servidor MCP [!DNL Adobe Target] utiliza OAuth 2.0 para la autenticación. La primera vez que utilice una herramienta MCP de Target, se le redirigirá a Adobe Experience Cloud para iniciar sesión, seleccionar su organización y conceder los permisos solicitados. No se requieren credenciales estáticas.

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

1. Compruebe que tiene el rol requerido en [!DNL Adobe Target] para la operación que está intentando realizar (vea [Requisitos previos](#mcp-prerequisites)). Las herramientas de solo lectura requieren Observer o superior; las herramientas de escritura requieren Editor o superior; la activación y desactivación requieren Approver.
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

## Recursos relacionados {#mcp-get-started-related}

* [Información general](target-mcp.md)
* [Casos de uso y tutoriales](target-mcp-use-cases.md)
* [Referencia de herramientas del servidor MCP](target-mcp-tools-reference.md)
* [Documentación del protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
