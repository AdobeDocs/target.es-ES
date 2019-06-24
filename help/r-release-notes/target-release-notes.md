---
description: En estas notas de la versión se proporciona información acerca de las características, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Target.
keywords: notas de la versión
seo-description: En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Adobe Target
seo-title: Notas de la versión de Adobe Target (versión preliminar)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a30f868c49bca7a0c017d272b435a6a351c6e9a6

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 7 de junio de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas de lanzamiento, las funciones y demás información están sujetos a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferente, según la hora de las versiones.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.6.1 (25 de junio de 2019) {#tgt-19-6-1}

Esta versión incorpora las siguientes nuevas funciones y mejoras:

| Función / Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales (VEC) | **Nuevas opciones de menú VEC**: Al hacer clic en un elemento de página del VEC, un menú muestra las opciones disponibles para ese tipo de elemento.<ul><li>You can now use the [!UICONTROL Styles &gt; Background] option to change the background image and color for the selected element. (TGT-15001)</li></ul>**Mejoras en el rastreo de clics**: Hemos mejorado el proceso para configurar el rastreo de clics dentro del VEC y el VEC de aplicación de una sola página (SPA).<ul><li>Al seleccionar elementos que se utilizan en el rastreo de clics, los nombres de todos los elementos disponibles se muestran en el panel Modificaciones del lado derecho, lo que facilita y simplifica la selección de los elementos deseados.</li><li>The [!UICONTROL Goals &amp; Settings] page of the three-part guided activity workflow displays a number representing the number of elements selected for click tracking. Puede pasar el ratón sobre este número para ver los nombres de todos los elementos seleccionados. (TGT-33878)</li></ul> |
| Compositor de experiencias visuales para aplicaciones de una sola página  (SPA VEC) | **Flujo de trabajo guiado**: Un nuevo flujo de trabajo guiado ayuda a comprender cómo debe configurarse la configuración de las reglas de entrega de páginas para ejecutar y ejecutar una actividad correctamente en la aplicación de una sola página. (TGT-33718)<br>**Clone modifications**: You can now define a modification using the SPA VEC and then clone that modification for use in other views in your Single Page App. (TGT-33882) |
| Compositor de experiencias visuales (VEC) | **Varias versiones de la aplicación**: Ahora puede crear actividades para varias versiones de su aplicación móvil. Esto ahorra tiempo y esfuerzo cuando las versiones son similares y no es necesario cambiar de forma significativa la interfaz de usuario de la aplicación. (TGT-34231) |
| ![Insignia Premium](/help/assets/premium.png) Personalización automatizada (AP) y segmentación automática | **Experiencia específica como control**: Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de segmentación automática o de segmentación automática. Esta función permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado contra el tráfico de control a esa experiencia. La opción de control actual (experiencias servidas aleatoriamente) seguirá estando disponible. (TGT-32801 &amp; TGT-26572)<br>**Personalization Insights reports**: The marketer-friendly naming for attributes when a visitor sees a specific piece of content in a specific location provides more meaningful information. (TGT-33326 y TGT-34957) |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
