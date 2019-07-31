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
source-git-commit: 48cb808283c9b2858e1bd041feb3fe8228253d6a

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

Enterprise Permissions allows [!DNL Target] customers to use a single organization, but divide it into workspaces for their different teams or workflows. Esto facilita el escalado efectivo de su programa de optimización entre equipos. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier this year. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, Target Enterprise Permissions will provide customers with the following access controls:

* Puede elegir los espacios de trabajo a los que se puede aplicar la integración
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Esta actualización admitirá los siguientes casos de uso:

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Conceda a la integración de Adobe I/O el acceso para seleccionar espacios de trabajo con la función apropiada para permitir que un equipo central realice cambios controlados por API en solo unos pocos espacios de trabajo.
* Cada equipo que posee su espacio de trabajo decide tener su propia integración siempre que el equipo esté listo para explorar las API y elegir la función correspondiente.
* Combina y coincide con cualquiera de los escenarios anteriores.

**Acción necesaria**: Los clientes que actualmente aprovechan las API para operaciones de CRUD en recursos (actividades, audiencias, ofertas e informes) en todos los espacios de trabajo deben conceder su acceso de integración de Adobe I/O a todos los espacios de trabajo con la función deseada según su caso de uso. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, irrespective of choice made in the [!UICONTROL Product Role] drop-down list. Ahora puede elegir la función que desee.

This action *must* be performed before September 4, 2019 to not face any disruption on your end. Si no se realiza esta acción, después del [! La versión de septiembre de Target DNL, los controles de acceso se activarán y podrá observar el acceso solo al espacio de trabajo predeterminado, si es así. No hay reacciones adversas para configurar integraciones de antemano según las directrices anteriores. Cuanto antes realice este cambio, mejor. Se requiere poco tiempo para configurar esto, según el número de espacios de trabajo de su organización. Este proceso solo toma unos pocos clics para agregar una integración existente en espacios de trabajo con la función deseada.

## Target Standard/Premium 19.8.1 (20 de agosto de 2019) {#tgt-19-8-1}

Esta versión de mantenimiento incluye la siguiente mejora:

* Varias correcciones de seguridad, incluida una actualización de seguridad del Editor de texto enriquecido (RTE) en el Compositor de experiencias visuales (VEC). (TGT-35383)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
