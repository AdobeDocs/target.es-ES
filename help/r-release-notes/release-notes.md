---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e7a866c01b03815a2e167612d4c7922cef54a5c0

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Target, los SDK, la biblioteca JavaScript (at.js) y otros cambios en la plataforma, si procede.

>[!IMPORTANT]
>
>A partir del 1 de marzo de 2020, Target desactivará la compatibilidad con el cifrado TLS 1.1 y TLS 1.0. Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. Este cambio es necesario para cumplir el estándar de cumplimiento de seguridad generalmente aceptado de TLS 1.2 o superior. Compruebe qué versión de TLS está utilizando actualmente. Si su versión es menor que 1.2, implemente los cambios necesarios antes del 1 de marzo de 2020 para seguir usando Target como se espera.
>
> Para obtener información detallada sobre el posible impacto y los pasos que debe seguir para actualizar la implementación, consulte Cambios [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)de codificación TLS (Transport Layer Security).

Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Target Standard/Premium 20.1.1 (4 de febrero de 2020)

La versión Target Standard/Premium 20.1.1 es una versión de mantenimiento que incluye mejoras y mejoras en el servidor. Además, se incluyen las siguientes correcciones:

* Se ha corregido un problema que provocaba que el campo del servidor de seguimiento de Adobe Analytics estuviera vacío en la página Objetivos y configuración de las actividades existentes de Adobe para Target (A4T). (TGT-35960)
* Se ha corregido un problema en la interfaz de usuario que provocaba que la selección en la segunda lista desplegable no se mostrara al crear una audiencia para afinidad de categoría. (TGT-36098)

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: API de servidor de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de la versión relacionadas con las API del servidor de Adobe Target. |
| [Notas de la versión: SDK de Node.js de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de la versión relacionadas con el SDK Node.js de Adobe Target. |
| [Notas de la versión: SDK de Java de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de la versión relacionadas con el SDK de Java de Adobe Target. |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios en cada versión de la biblioteca JavaScript de Adobe Target at.js. |
| [Detalles de la versión de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página muestra cambios realizados a cada versión de mbox.js.<br>Tenga en cuenta que la biblioteca mbox.js ya no se está desarrollando. Todos los clientes deberían migrar de mbox.js a at.js. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las Notas de la versión [de Experience Cloud](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
