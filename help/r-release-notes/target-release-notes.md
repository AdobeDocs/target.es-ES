---
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target.
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
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

[!UICONTROL Enterprise Permissions] allows [!DNL Target] customers to use a single organization, but divide it into workspaces for different teams or workflows. The Enterprise Permissions feature facilitates effective scaling of optimization programs across teams.  Although this feature was available in the  UI, the Admin APIs lacked the corresponding support until the  February 2019 release. [!DNL Target][!DNL Target] Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with Approver access.

Con la próxima versión de [!DNL Target] septiembre de 2019, los permisos [!UICONTROL de] Enterprise proporcionarán a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]u [!UICONTROL Observador].

**Acción requerida**: Los clientes que actualmente utilizan API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben otorgar a su integración de Adobe I/O existente acceso a todos los espacios de trabajo con la función deseada. Antes de la versión de septiembre, todas las integraciones funcionaban con acceso de [!UICONTROL aprobador] , independientemente de la función seleccionada en la lista desplegable Función [!UICONTROL del] producto. Con la próxima versión, ahora puede seleccionar la función deseada.

Esta acción debe realizarse durante el mes de **agosto de 2019**. Después de la versión de [!DNL Target] septiembre de 2019, los controles de acceso se activarán y observará el acceso al espacio de trabajo predeterminado únicamente si es así como está configurado actualmente. There is no adverse consequence to setting up integration roles in advance.

Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 de septiembre de 2019)

Esta versión de mantenimiento incluye la siguiente mejora:

* Varias correcciones de seguridad, incluida una actualización de seguridad al editor de texto enriquecido (RTE) en el Compositor de experiencias visuales (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 de septiembre de 2019)

| Función. / Mejora | Descripción |
| --- | --- |
| ![Permisos de Enterprise con distintivo](/help/assets/premium.png) Premium | Con la versión de Target de septiembre de 2019, los permisos de Enterprise proporcionan a los clientes los siguientes controles de acceso:<UL><li>Puede elegir los espacios de trabajo a los que se puede aplicar la integración.</li><li>You can apply a role to the Adobe I/O integration: Approver, Editor, or Observer.</li></ul>Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
