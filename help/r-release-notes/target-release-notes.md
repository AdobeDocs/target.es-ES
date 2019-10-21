---
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target.
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones
seo-description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target de DNL.
seo-title: Notas de la versión de evaluación de Adobe Target
solution: Target
title: Notas de la versión de Target (versión previa)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 956a6b88fac9a13b98ede655e930aa016fe82533

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 17 de octubre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Target Standard/Premium 19.10.1 (22 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Recomendaciones<br>basadas en el usuario (24 de octubre de 2019) | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como "Recomendado para usted".<br>Este criterio le permite entregar contenido y experiencias personalizados tanto a visitantes nuevos como a visitantes que regresan. La lista de recomendaciones se centra en la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el visitante navega por el sitio.<br>Para obtener más información, consulte "Recomendaciones basadas en el usuario" en [Criterios y algoritmos](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms). |

### Mejoras, correcciones y cambios

* Al iniciar sesión en el [!DNL Adobe Experience Cloud], se le dirigirá a la nueva navegación de encabezado. Se parece mucho a la navegación anterior con la barra negra en la parte superior, pero ofrece las siguientes mejoras:

   * Cambio más fácil entre organizaciones [!DNL Identity Management System] (IMS) o una solución diferente.
   * Se ha mejorado la ayuda del usuario: Los resultados de la búsqueda incluyen los resultados de la documentación del [!DNL Target] producto, así como los foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido [!DNL Target]. También hemos agregado un mecanismo de comentarios en el menú [!UICONTROL Ayuda] , lo que facilita informar sobre problemas o compartir ideas.

   * Se ha mejorado la funcionalidad de comentarios de Net Promoter Score (NPS), de modo que el modo de estudio no interrumpe el flujo de trabajo.
   * Se ha mejorado el flujo de inicio de sesión. Anteriormente, todos [!DNL Target] los clientes aterrizaban en la página de aterrizaje de Target después de hacer clic en el [!DNL Target] icono del encabezado. A continuación, esta página permite a los clientes avanzar con [!DNL Target Standard/Premium], [!DNL Search&Promote]o [!DNl Recommendations Classic], como se muestra a continuación:

      ![Página de destino](/help/r-release-notes/assets/landing.png)

      Hemos eliminado esta página de aterrizaje para todos nuestros clientes. Ahora siempre se le dirigirá directamente a la página Lista [!UICONTROL de] actividades haciendo clic en el [!DNL Target] icono de la nueva barra de navegación de encabezado.

      Si utiliza [!DNL Recommendations Classic], puede ir directamente a la solución o puede ir desde el vínculo corto creado en la ficha [!UICONTROL Recomendaciones] , como se muestra a continuación:

      ![Vínculo profundo de Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si utiliza [!DNL Search&Promote], debe ir directamente al vínculo. Se ha eliminado completamente la ruta [!DNL Search&Promote] de acceso desde el interior de [!DNL Adobe Target] .

   * Las notificaciones para [!DNL Target] no están disponibles actualmente en la lista desplegable [!UICONTROL Notificaciones] del encabezado.
   >[!NOTE]
   >
   >Estas funciones no se implementarán a la vez ni se distribuirán a todos los clientes. Estas funciones se implementarán en los próximos días a partir de la versión [!DNL Target Standard/Premium] 19.10.1 (22 de octubre de 2019).
   >
   >Como parte de la implementación de la nueva barra de navegación, también verá algunos cambios en la dirección URL. Todos los vínculos con marcador anteriores siguen funcionando pero le recomendamos que marque nuevos vínculos para una apertura más rápida.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
