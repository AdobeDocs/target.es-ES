---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 716180f5a9177b6c86b2aacce76d87a9994f596d
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 68%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 19 de mayo de 2023**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Estándar/Premium 23.5.1 (23-25 de mayo de 2023)

Esta versión estará disponible según la siguiente programación escalonada:

23 de mayo: Europa, Oriente Medio y África (EMEA) 24 de mayo: Región Asia-Pacífico (APAC) 25 de mayo: Región de América

Esta versión incluye las siguientes nuevas funciones, mejoras y correcciones:

| Función | Detalles |
|--- |--- |
| Atributos de perfil de Real-Time CDP compartidos con [!DNL Target] | Los [!UICONTROL Atributos de perfil de Real-Time CDP] se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y JSON.<P>Para obtener más información, consulte [Uso compartido de atributos de perfil de Real-Time CDP con [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

* Se ha corregido un problema que impedía que algunos clientes crearan audiencias con perfiles de visitante mediante operadores &quot;buenos que&quot; o &quot;inferiores a&quot;. (TGT-45271)

## [!DNL Target] Standard/Premium 23.5.2 (31 de mayo de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que hacía que se mostrara una página en blanco al generar un token de autorización de API de perfil. (TGT-45387)
* Se ha corregido un problema que impedía que una imagen se mostrara en la variable [!UICONTROL Crear diseño] si el nombre de la imagen contiene 18030 caracteres GB. (TGT-44614)
* Se ha corregido un problema que provocaba informes para [!UICONTROL Personalización automática] actividades que se congelarán durante el análisis. (TGT-44820)

## [!DNL Target] Standard/Premium 23.5.3 (Fecha por determinar)

Esta versión incluye las siguientes mejoras:

| Función | Detalles |
|--- |--- |
| [!UICONTROL Modo de control de calidad] para [!UICONTROL Automated Personalization] actividades | [!DNL Adobe Target] [!UICONTROL Modo de control de calidad] ya está disponible para [!UICONTROL Automated Personalization] actividades, reemplazar [!UICONTROL Vista previa de vínculos] funcionalidad.<P>Para obtener más información, consulte [Control de calidad de las actividades.](/help/main/c-activities/c-activity-qa/activity-qa.md) |

* Se ha mejorado el rendimiento al usar la variable [!UICONTROL No permitir duplicados] opción while [administración de exclusiones](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) en [!UICONTROL Automated Personalization] actividades.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
