---
description: En estas notas de la versión se proporciona información acerca de las características, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Target.
keywords: notas de la versión
seo-description: En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de Adobe Target
seo-title: Notas de la versión de Target (versión previa)
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: bac43f0907b083f416aaf72fca0eb4c6d4b83a7e

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 28 de mayo de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios. Para ver la información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.

## Target Standard/Premium 19.6.1 (25 de junio de 2019) {#tgt-19-6-1}

| Función/Mejora | Descripción |
| --- | --- |
| Compositor de experiencias visuales (VEC) | <ul><li>Ahora puede utilizar [!DNL Styles > Background] el menú del VEC para cambiar la imagen de fondo y el color del elemento seleccionado. (TGT-15001)</li><li>Al hacer clic en un elemento de página del VEC, un menú muestra las opciones disponibles para ese tipo de elemento. Al hacer clic en una imagen, haga clic [!DNL Replace With]en dos nuevas opciones: [!DNL HTML] y [Fragmento de experiencias](/help/c-experiences/c-manage-content/aem-experience-fragments.md).<br> Reemplazar una imagen con HTML le proporciona control completo del elemento sin necesidad de seleccionar el elemento principal para acceder a la opción HTML. Los fragmentos de experiencia permiten insertar rápidamente elementos creados en Adobe Experience Manager (AEM) en los procesos de Target. (TGT-34097)</li></ul> |
| Compositor de experiencias visuales (SPA) de una aplicación de una sola página (VEC) | <ul><li>Un nuevo flujo de trabajo guiado ayuda a comprender cómo debe configurarse la configuración de las reglas de entrega de páginas para ejecutar y ejecutar una actividad correctamente en la aplicación de una sola página. (TGT-33718)</li><li>Ahora puede definir una modificación utilizando el VEC de SPA y luego clonar esa modificación para usarla en otras vistas de la aplicación de una sola página. (TGT-33882)</li><li>Hemos mejorado el proceso para configurar el rastreo de clics dentro del VEC de SPA.<br>Al seleccionar elementos que se utilizan en el rastreo de clics, los nombres de todos los elementos disponibles se muestran en el panel Modificaciones del lado derecho, lo que facilita y simplifica la selección de los elementos deseados.<br>La [!DNL Goals & Settings] página del flujo de trabajo de actividades guiadas de tres partes muestra un número que representa el número de elementos seleccionados para el rastreo de clics. Puede pasar el ratón sobre este número para ver los nombres de todos los elementos seleccionados. (TGT-33878) </li></ul> |
| Compositor de experiencias visuales móviles (VEC) | <ul><li>Ahora puede crear actividades para varias versiones de su aplicación móvil. Esto ahorra tiempo y esfuerzo cuando las versiones son muy similares y no es necesario cambiar de forma significativa la IU de la aplicación. (TGT-34231)</li></ul> |
| ![Actividades de Personalización automatizada de](/help/assets/premium.png)<br>Premium (AP) y de Segmentación automática: experiencia como control en | <ul><li>Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de PA o de segmentación automática. Esto permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. A continuación, puede evaluar el rendimiento de los envíos personalizados con respecto a la experiencia de control. (TGT-32801 y TGT-26572)</li></ul> |

### Mejoras, correcciones y cambios

* La   <BODY> ahora se muestra en la ruta DOM que aparece en la parte inferior del VEC cuando hace clic en un elemento de la página, lo que le permite realizar acciones en la página <BODY> etiqueta de cierre. (TGT-33736)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
