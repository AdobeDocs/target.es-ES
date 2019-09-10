---
description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
keywords: notas de la versión
seo-description: Notas de la versión que proporcionan información sobre características, mejoras y correcciones de las últimas o más próximas [! Versiones de DNL Adobe Target.
seo-title: Notas de la versión de Adobe Target (versión prelanzamiento)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 6 de septiembre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Anuncios

**31 de julio de 2019**

[!UICONTROL Los permisos de Enterprise] permiten [!DNL Target] a los clientes utilizar una sola organización, pero dividirlo en espacios de trabajo para equipos o flujos de trabajo diferentes. La función [!UICONTROL Permisos] de Enterprise facilita la escala efectiva de los programas de optimización entre los equipos. Aunque esta función estaba disponible en [!DNL Target] la interfaz de usuario, las API de administración no tenían la compatibilidad correspondiente hasta [!DNL Target] la versión de febrero de 2019. Adobe ha actualizado las API de administración para que pueda utilizar la cuenta de integración para acceder a todos los espacios de trabajo creados en su organización. Por lo tanto, si bien anteriormente, las API de administración estaban restringidas al espacio de trabajo predeterminado, la actualización de febrero de 2019 otorgaba acceso a todos los espacios de trabajo con [!UICONTROL acceso de aprobador] .

Con la próxima versión [!DNL Target] de septiembre de 2019 [!UICONTROL , los permisos] de Enterprise proporcionarán a los clientes los siguientes controles de acceso:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* Puede aplicar una función a la integración de Adobe I/O: [!UICONTROL Aprobador], [!UICONTROL Editor]o [!UICONTROL Observador].

**Acción requerida**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada. Antes de la versión de septiembre, todas las integraciones operaban usando el acceso [!UICONTROL de aprobador] , independientemente de la función seleccionada en la [!UICONTROL lista desplegable Función] del producto. Con la próxima versión, puede seleccionar la función que desee.

Esta acción debe realizarse durante el mes **de agosto de 2019**. Después de [!DNL Target] la versión de septiembre de 2019, los controles de acceso se activarán y podrá observar el acceso solo al espacio de trabajo predeterminado, si está configurado. No hay consecuencias adversas para configurar las funciones de integración con antelación.

Para obtener instrucciones paso a paso y más información, consulte [Concesión de integraciones de Adobe I/O a espacios de trabajo y asignación de funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Standard/Premium 19.9.1 (10 de septiembre de 2019)

| Función. / Mejora | Descripción |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Enterprise Permissions | Con la versión de septiembre de 2019 de Target, los permisos de Enterprise proporcionan a los clientes los siguientes controles de acceso:<UL><li>Puede elegir los espacios de trabajo a los que se puede aplicar la integración.</li><li>Puede aplicar una función a la integración de Adobe I/O: Aprobador, Editor o Observador.</li></ul>Para obtener instrucciones paso a paso y más información, consulte [Concesión de integraciones de Adobe I/O a espacios de trabajo y asignación de funciones](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md). |

## Target Standard/Premium 19.9.2 (24 de septiembre de 2019)

Esta versión de mantenimiento incluye la siguiente mejora:

* Varias correcciones de seguridad, incluida una actualización de seguridad del Editor de texto enriquecido (RTE) en el Compositor de experiencias visuales (VEC). (TGT-35383)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
