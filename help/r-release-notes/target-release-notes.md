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
source-git-commit: e50ae8c95774716ea484f02b276b2d66cb228364

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 6 de junio de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas de lanzamiento, las funciones y demás información están sujetos a cambios sin previo aviso. Para ver la información sobre la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números de problema entre paréntesis son para [!DNL Adobe] uso interno.

## Target Standard/Premium 19.6.1 (25 de junio de 2019) {#tgt-19-6-1}

Esta versión incorpora las siguientes nuevas funciones y mejoras:

### Compositor de experiencias visuales (VEC)

* **Nuevas opciones de menú VEC**: Al hacer clic en un elemento de página del VEC, un menú muestra las opciones disponibles para ese tipo de elemento.

   * **Estilos &gt; Fondo**: Ahora puede utilizar la opción [!UICONTROL Estilos &gt; Fondo] para cambiar la imagen de fondo y el color del elemento seleccionado. (TGT-15001)

   * **[!UICONTROL Reemplazar con &gt; HTML]y[!UICONTROL Reemplazar con &gt; Fragmento de experiencias]**: Al hacer clic en una imagen y luego en [!UICONTROL Reemplazar con], se muestran dos nuevas opciones:

      * **HTML**: Puede reemplazar una imagen con HTML para darle un control total del elemento sin necesidad de seleccionar el elemento principal para acceder a la opción HTML.
      * **Fragmento de experiencias**: Puede reemplazar una imagen con un fragmento [de experiencia de Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) para insertar rápidamente elementos creados en AEM en actividades de Target. (TGT-34097)

* **Mejoras en el rastreo de clics**: Hemos mejorado el proceso para configurar el rastreo de clics dentro del VEC y el VEC de aplicación de una sola página (SPA).

   * Al seleccionar elementos que se utilizan en el rastreo de clics, los nombres de todos los elementos disponibles se muestran en el panel Modificaciones del lado derecho, lo que facilita y simplifica la selección de los elementos deseados.
   * La [!UICONTROL página Objetivos y configuración] del flujo de trabajo de actividades guiadas de tres partes muestra un número que representa el número de elementos seleccionados para el rastreo de clics. Puede pasar el ratón sobre este número para ver los nombres de todos los elementos seleccionados. (TGT-33878)

### SPA VEC

* **Flujo de trabajo guiado**: Un nuevo flujo de trabajo guiado ayuda a comprender cómo debe configurarse la configuración de las reglas de entrega de páginas para ejecutar y ejecutar una actividad correctamente en la aplicación de una sola página. (TGT-33718)

* **Modificaciones en clonar**: Ahora puede definir una modificación utilizando el VEC de SPA y luego clonar esa modificación para usarla en otras vistas de la aplicación de una sola página. (TGT-33882)

### VEC móvil

* **Varias versiones de la aplicación**: Ahora puede crear actividades para varias versiones de su aplicación móvil. Esto ahorra tiempo y esfuerzo cuando las versiones son similares y no es necesario cambiar de forma significativa la interfaz de usuario de la aplicación. (TGT-34231)

### ![Insignia Premium](/help/assets/premium.png) Personalización automatizada (AP) y segmentación automática

* **Experiencia específica como control**: Puede seleccionar una experiencia para utilizarla como control mientras crea una actividad de segmentación automática o de segmentación automática. Esta función permite dirigir todo el tráfico de control a una experiencia específica, según el porcentaje de asignación de tráfico configurado en la actividad. Luego puede evaluar los informes de rendimiento del tráfico personalizado contra el tráfico de control a esa experiencia. La opción de control actual (experiencias servidas aleatoriamente) seguirá estando disponible. (TGT-32801 y TGT-26572)

### Otras mejoras, correcciones y cambios

* La `<BODY>` etiqueta ahora se muestra en la ruta DOM que aparece en la parte inferior del VEC cuando hace clic en un elemento de la página, lo que le permite realizar acciones en `<BODY>` la etiqueta. (TGT-33736)

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
