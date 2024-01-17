---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b76a0541b181ee5ebe88f2d11f5556c6c7b91126
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 50%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: miércoles, 16 de enero de 2024**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Obsolescencia de iPad y iPhone a partir del atributo de audiencia del explorador (30 de abril de 2024)

| Desaprobación | Detalles |
|--- |--- |
| [!DNL iPad] y [!DNL iPhone] que se van a retirar del [Atributo de explorador](/help/main/c-target/c-audiences/c-target-rules/browser.md) se utiliza para crear audiencias.<p>Fecha de desuso:<P>miércoles, 30 de abril de 2024 | [!DNL Adobe Target] le permite [segmentar en cualquiera de los atributos de categoría](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluidos los usuarios que utilizan un específico [opciones del navegador o](/help/main/c-target/c-audiences/c-target-rules/browser.md) cuando visiten su página.<P><B>A partir del 30 de abril de 2024, iPad y iPhone se eliminarán de las versiones de disponibles [!UICONTROL Explorador] escriba lista desplegable al crear categorías para audiencias.</b><P>Si tiene audiencias dirigidas a iPads o iPhone que utilizan [!UICONTROL Explorador] debe cambiar esta configuración antes del 30 de abril de 2024 para garantizar que estas audiencias sigan funcionando según lo esperado.<P>En adelante, se debe utilizar la siguiente configuración:<ul><li>[!UICONTROL Móvil] > [!UICONTROL es tableta]<P>![mobile es tablet](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL Móvil] > [!UICONTROL Nombre de marketing del dispositivo] [!UICONTROL matches] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL Móvil] > [!UICONTROL Nombre de marketing del dispositivo] [!UICONTROL matches] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 y 25 de enero de 2024)

Esta versión está programada para los siguientes días:

* **22 de enero**: región de Europa, Oriente Medio y África (EMEA)
* **23 de enero**: región de Asia-Pacífico (APAC)
* **25 de enero**: región de América

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que provocaba que los intervalos de fechas de creación de informes no funcionaran correctamente. (TGT-47396)
* Se ha corregido un problema que provocaba que se mostrara un estado incorrecto en la [!UICONTROL Todas las actividades] después de que los clientes activaran o desactivaran una actividad mediante [!UICONTROL Más acciones] icono. (TGT-47367)
* Se ha corregido un problema que provocaba que [!UICONTROL Atributos importantes] informe que no se mostrará para un cliente. (TGT-47272)
* Se ha corregido un problema que provocaba que se mostrara un mensaje &quot;Carga útil no válida&quot; cuando un cliente intentaba habilitar &quot;Requerir autenticación&quot;. (TGT-47195)
* Se han actualizado varias cadenas localizadas en [!DNL Target] IU.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
