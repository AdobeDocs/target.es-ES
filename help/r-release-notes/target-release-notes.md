---
description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones para las versiones más recientes o futuras de [!DNL Adobe Target].
keywords: notas de la versión
seo-description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones para las versiones más recientes o futuras de [!DNL Adobe Target].
seo-title: Notas de la versión de Adobe Target (versión prelanzamiento)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d675c6875c8474ba490956ea395076eef5b9e58f

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

[!UICONTROL Los permisos] de Enterprise permiten a [!DNL Target] los clientes utilizar una sola organización, pero dividirla en espacios de trabajo para diferentes equipos o flujos de trabajo. La función Permisos [!UICONTROL de] empresa facilita la escalada efectiva de los programas de optimización entre equipos. Aunque esta función estaba disponible en la interfaz de [!DNL Target] usuario, las API de administración carecían de la compatibilidad correspondiente hasta la versión [!DNL Target] de febrero de 2019. Adobe ha actualizado las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por lo tanto, aunque antes las API de administración estaban restringidas al espacio de trabajo predeterminado, la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con acceso de [!UICONTROL aprobador] .

Con la próxima versión de [!DNL Target] septiembre de 2019, los permisos [!UICONTROL de] Enterprise proporcionarán a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]u [!UICONTROL Observador].

**Acción requerida**: Los clientes que actualmente utilizan API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben otorgar a su integración de Adobe I/O existente acceso a todos los espacios de trabajo con la función deseada. Antes de la versión de septiembre, todas las integraciones funcionaban con acceso de [!UICONTROL aprobador] , independientemente de la función seleccionada en la lista desplegable Función [!UICONTROL del] producto. Con la próxima versión, ahora puede seleccionar la función deseada.

Esta acción debe realizarse durante el mes de **agosto de 2019**. Después de la versión de [!DNL Target] septiembre de 2019, los controles de acceso se activarán y observará el acceso al espacio de trabajo predeterminado únicamente si es así como está configurado actualmente. No hay consecuencias negativas en la configuración anticipada de las funciones de integración.

Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.2 (30 de septiembre de 2019)

This maintenance release includes the following enhancement:

* Varias correcciones de seguridad, incluida una actualización de seguridad al editor de texto enriquecido (RTE) en el Compositor de experiencias visuales (VEC). (TGT-35383)

## Target Standard/Premium 19.9.1 (10 de septiembre de 2019)

| Función. / Mejora | Descripción |
| --- | --- |
| ![Permisos de Enterprise con distintivo](/help/assets/premium.png) Premium | Con la versión de Target de septiembre de 2019, los permisos de Enterprise proporcionan a los clientes los siguientes controles de acceso:<UL><li>Puede elegir los espacios de trabajo a los que se puede aplicar la integración.</li><li>Puede aplicar una función a la integración de Adobe I/O: Aprobador, Editor u Observador.</li></ul>Para obtener instrucciones paso a paso y más información, consulte [Conceder acceso a las integraciones de Adobe I/O a los espacios de trabajo y asignar funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
