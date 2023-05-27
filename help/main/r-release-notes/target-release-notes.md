---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información acerca de las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones y mejoras se incluirán en la próxima versión de  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ecdb94a679e033d3ec030513fd66c9eea039195b
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 56%

---

# Notas de la versión de [!DNL Target] (versión preliminar)

Este artículo contiene información previa al lanzamiento para las versiones de [!DNL Adobe Target], incluidos los SDK, las API y las bibliotecas de JavaScript.

**Última actualización: 24 de mayo de 2023**

>[!NOTE]
>
>Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.
>
>Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.5.2 (31 de mayo de 2023)

Esta versión incluye las siguientes mejoras y correcciones:

* Se ha corregido un problema que provocaba que se mostrara una página en blanco al generar un token de autorización de API de perfil. (TGT-45387)
* Se ha corregido un problema que impedía que se mostrara una imagen en la [!UICONTROL Crear diseño] panel si el nombre de la imagen contiene caracteres GB 18030. (TGT-44614)
* Se ha corregido un problema que generaba informes para [!UICONTROL Personalización automática] actividades para congelar durante el análisis. (TGT-44820)
* Se ha corregido un problema que hacía que no se mostraran actividades en la interfaz de usuario de Target para el espacio de trabajo predeterminado para determinados clientes. (TGT-45286)
* Se ha actualizado el comportamiento del indicador No permitir duplicados. Los indicadores de ofertas repetidas excluidas se actualizan para permitir ofertas repetidas si son la oferta de contenido predeterminada (para las API v3 y v4) y permitir opciones duplicadas si las opciones hacen referencia a la oferta de contenido predeterminada y no tienen plantillas definidas. (TNT-46617)
* Se ha corregido un problema por el cual se agregaba un parámetro de consulta a una dirección URL que impedía que la página se cargara en el Compositor de experiencias visuales (VEC). (TGT-44873)
* Se ha corregido un problema por el cual algunos caracteres se evitaban incorrectamente en Texto/HTML en experiencias. (TGT-44600)

## [!DNL Target] Standard/Premium 23.5.3 (fecha por determinar)

Esta versión incluye las siguientes mejoras:

| Función | Detalles |
|--- |--- |
| [!UICONTROL Modo de control de calidad] para [!UICONTROL Automated Personalization] actividades | [!DNL Adobe Target] [!UICONTROL Modo de control de calidad] ya está disponible para [!UICONTROL Automated Personalization] actividades, reemplazar [!UICONTROL Previsualizar vínculos] funcionalidad.<P>Para obtener más información, consulte [Control de calidad de las actividades.](/help/main/c-activities/c-activity-qa/activity-qa.md) |
| Atributos de perfil de Real-Time CDP compartidos con [!DNL Target] | Los [!UICONTROL Atributos de perfil de Real-Time CDP] se pueden compartir con [!DNL Target] para su uso en ofertas de HTML y JSON.<P>Para obtener más información, consulte [Uso compartido de atributos de perfil de Real-Time CDP con [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

* Mejoras de rendimiento para impedir la funcionalidad de duplicados (incluida la reducción del tiempo de carga) mientras que [administración de exclusiones](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) in [!UICONTROL Automated Personalization] actividades.

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: SDK web de Adobe Target Platform Experience](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=es) | Detalles acerca de los cambios realizados en cada versión del SDK web de Platform. |
| [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} | Detalles sobre los cambios realizados en cada versión de la biblioteca JavaScript de at.js. [!DNL Adobe Target]. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en [!DNL Target] y otras soluciones de [!DNL Adobe Experience Cloud], regístrese en [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
