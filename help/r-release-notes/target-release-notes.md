---
keywords: notas de la versión;versiones;actualizaciones;versión futura;mejoras;nuevas funciones;correcciones
description: Notas de la versión que proporcionan información sobre funciones, mejoras y correcciones para las versiones más recientes o futuras de Adobe Target de DNL.
title: Notas de la versión de evaluación de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 31 de octubre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Plataforma de Target (31 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| Java SDK | El SDK de [!DNL Target] Java permite implementar [!DNL Target] el servidor. Este SDK de Java le ayuda a integrarse fácilmente [!DNL Target] con otras [!DNL Adobe Experience Cloud] soluciones, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]y [!DNL Adobe Audience Manager].<br>El SDK de Java introduce prácticas recomendadas y elimina las complejidades al realizar la integración con [!DNL Target] mediante nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial. Las siguientes son funciones destacadas que presentamos en la versión más reciente:<ul><li>Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché.</li><li>Compatibilidad para optimizar el rendimiento cuando se dispone de una integración híbrida de [!DNL Target] en las páginas web y en el servidor. Estamos introduciendo una configuración llamada `serverState` que se rellena con las experiencias recuperadas a través del servidor para que at.js 2.2 ya no realice una llamada adicional al servidor para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.</li><li>Compatibilidad con la recuperación de actividades creadas por VEC mediante el SDK de Java, lo cual es posible gracias a la nueva API de envío.</li><li>Abra el código fuente para que los desarrolladores puedan contribuir al SDK [Java de](https://github.com/adobe/target-java-sdk)Target.</li></ul>Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)de Java de Target.<br>Obtenga más información sobre el SDK de Java de Target en el blog técnico de Adobe: Optimización del lado del [servidor con el nuevo SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)de Java de Target. |

## Target Standard/Premium 19.10.2 (31 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Distintivo](/help/assets/premium.png) Premium Trabajar con atributos de varios valores | A veces desea trabajar con un campo de varios valores. Veamos los siguientes ejemplos:<ul><li>Puede ofrecer películas a los usuarios. Una película determinada tiene múltiples actores.</li><li>Vendes entradas a conciertos. Un usuario determinado tiene varias bandas favoritas.</li><li>Vendes ropa. Hay una camisa disponible en varios tamaños.</li></ul>Para administrar las recomendaciones en estos escenarios, puede pasar datos de varios valores a Recomendaciones de Target y usar operadores especiales de varios valores. |

## Target Standard/Premium 20.1.1

La versión de Target Standard/Premium 20.1.1 estará disponible en enero de 2020. La fecha exacta, las funciones y las mejoras se anunciarán aquí.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
