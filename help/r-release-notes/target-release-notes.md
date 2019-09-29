---
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target.
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones
seo-description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target de DNL.
seo-title: Notas de la versión de Adobe Target (versión prelanzamiento)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1d91c46c78c0bcb58607def4cacaff0b761162fa

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 24 de septiembre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Anuncios

**July 31, 2019**

[!UICONTROL Los permisos] de Enterprise permiten a [!DNL Target] los clientes utilizar una sola organización, pero dividirla en espacios de trabajo para diferentes equipos o flujos de trabajo. The Enterprise Permissions feature facilitates effective scaling of optimization programs across teams.  Although this feature was available in the  UI, the Admin APIs lacked the corresponding support until the  February 2019 release. [!DNL Target][!DNL Target] Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with Approver access.

Con la próxima versión de [!DNL Target] septiembre de 2019, los permisos [!UICONTROL de] Enterprise proporcionarán a los clientes los siguientes controles de acceso:

* You can choose the workspaces to which the integration can be applied
* You can apply a role to the Adobe I/O integration: Approver, Editor, or Observer.

**Action Required**: Customers who are currently leveraging APIs for CRUD operations on resources (activities, audiences, offers, and reporting) across all workspaces need to grant their existing Adobe I/O integration access to all workspaces with the desired role. Prior to the September release, all integrations operated using Approver access, regardless of the role selected from the Product Role drop-down list.  With the upcoming release, you can now select the desired role.

This action should be performed during the month of August 2019. **** After the  September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. [!DNL Target] There is no adverse consequence to setting up integration roles in advance.

Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 de septiembre de 2019)

Esta versión de mantenimiento incluye la siguiente mejora:

* Several security fixes, including a security update to the Rich Text Editor (RTE) in the Visual Experience Composer (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 de septiembre de 2019)

| Función. / Mejora | Descripción |
| --- | --- |
| ![Permisos de Enterprise con distintivo](/help/assets/premium.png) Premium | Con la versión de Target de septiembre de 2019, los permisos de Enterprise proporcionan a los clientes los siguientes controles de acceso:<UL><li>Puede elegir los espacios de trabajo a los que se puede aplicar la integración.</li><li>Puede aplicar una función a la integración de Adobe I/O: Aprobador, Editor u Observador.</li></ul>Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
