---
description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
keywords: notas de la versión
seo-description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
seo-title: Notas de la versión de Adobe Target (versión preliminar)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e1174aacc5610878c8671e88fbd20d51fedffe6c

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 31 de julio de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas de lanzamiento, las funciones y demás información están sujetos a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Anuncios

**31 de julio de 2019**

[!UICONTROL Los permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirlo en espacios de trabajo para equipos o flujos de trabajo diferentes. The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although this feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until the [!DNL Target] February 2019 release. Adobe ha actualizado las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

**Acción requerida**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of the role selected from the [!UICONTROL Product Role] drop-down list. Con la próxima versión, puede seleccionar la función que desee.

This action should be performed during the month of **August 2019**. After the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. No hay consecuencias adversas para configurar las funciones de integración con antelación.

For step-by-step instructions and more information, see [Grant Adobe I/O integrations access to workspaces and assign roles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.8.1 (20 de agosto de 2019) {#tgt-19-8-1}

Esta versión de mantenimiento incluye la siguiente mejora:

* Varias correcciones de seguridad, incluida una actualización de seguridad del Editor de texto enriquecido (RTE) en el Compositor de experiencias visuales (VEC). (TGT-35383)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
