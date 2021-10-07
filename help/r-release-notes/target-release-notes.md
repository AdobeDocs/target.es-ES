---
keywords: notas de la versión;versiones;actualizaciones;futuras versiones;mejoras;nuevas funciones;correcciones;actualizaciones;versión preliminar
description: Obtenga información sobre las nuevas funciones, mejoras y correcciones que incluirá la próxima versión de Adobe Target, incluidos el SDK, la API y las bibliotecas de JavaScript.
title: ¿Qué nuevas funciones se incluirán en la próxima versión?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd7032b915bf1b333fa5cc3cb4825eaa7e4f83fb
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 43%

---

# Notas de la versión de Target (versión previa)

Este artículo contiene información sobre la versión preliminar. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso.

**Última actualización: 6 de octubre de 2021**

Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma en función del lanzamiento de las versiones. Los números entre paréntesis son para uso interno de [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vida útil de mbox.js**: Desde el 31 de marzo de 2021, [!DNL Adobe Target] no es compatible con la biblioteca mbox.js. Después del 31 de marzo de 2021, todas las llamadas que se realicen desde mbox.js producirán errores y afectarán a las páginas que tengan actividades de [!DNL Target] en ejecución por contenido predeterminado.
>
>Para evitar posibles problemas con sus sitios, migre a la versión más reciente del nuevo [!DNL Adobe Experience Platform Web SDK] o la biblioteca de JavaScript at.js. Para obtener más información, consulte [Información general: Implementación de Target en sitios web del lado del cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.1 (6 de octubre de 2021)

Esta versión incluye las siguientes nuevas funciones:

| Función | Detalles |
| --- | --- |
|  Actualización de audiencias en la interfaz de usuario | Como parte del esfuerzo continuo del equipo [!DNL Adobe Target] para mejorar la experiencia del usuario para los usuarios de [!DNL Target], esta versión actualiza las páginas [!UICONTROL Audiencias] y [!UICONTROL Scripts de perfil] en la interfaz de usuario de [!DNL Target]. Esta actualización unifica y estandariza los patrones de diseño que anteriormente eran incoherentes, a la vez que agrega nuevas mejoras, como:<ul><li>La capacidad de seleccionar y eliminar varias audiencias simultáneamente</li><li>Un [diseño actualizado del generador de audiencias](/help/c-target/c-audiences/create-audience.md)</li><li>Compatibilidad con reglas de exclusión en el [!UICONTROL Audience] generador de reglas de la biblioteca</li><li>Un nuevo filtro &quot;Fuente de audiencia&quot; que permite una detección de audiencias más rápida</li><li>Opciones de filtro y búsqueda persistentes de sesión</li></ul>Para obtener más información, consulte [Audiencias](/help/c-target/target.md).<br>**Nota**: La nueva interfaz de usuario de   Audiencias y  [!UICONTROL Scripts de ] perfil se implementará en todas las regiones la próxima semana. |
| [!UICONTROL Actualización de la interfaz de usuario de ] scripts de perfil | La biblioteca [!UICONTROL Scripts de perfil] también se actualizó e incluye una interfaz actualizada y varias actualizaciones de productividad:<ul><li>La capacidad de seleccionar y eliminar varios scripts de perfil simultáneamente</li><li>Un nuevo editor de código para scripts de perfil</li><li>Resaltado de sintaxis y comprobación de errores dentro del editor de código</li><li>Completar automáticamente los parámetros de tokens (mbox o perfil) mediante métodos abreviados del teclado</li></ul>Para obtener más información, consulte [Perfiles del visitante](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Nota**: La nueva interfaz de usuario de   Audiencias y  [!UICONTROL Scripts de ] perfil se implementará en todas las regiones la próxima semana. |
| ![Distintivo PremiumCriterios de Recommendations crear y editar ](/help/assets/premium.png)  | El flujo de trabajo de creación y edición de [!UICONTROL Recommendations Criteria] se ha optimizado para simplificar la elección del algoritmo de recomendaciones y la configuración adecuados para lograr sus objetivos.<br>Para obtener más información, consulte  [Crear criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Distintivo PremiumVentana retrospectiva de Recommendations y mejoras en la velocidad de actualización del algoritmo ](/help/assets/premium.png)  | Ahora puede ejecutar los algoritmos &quot;Más visitados&quot; y &quot;Principales vendedores&quot; con una ventana retrospectiva de seis horas para capturar el contenido que es más reciente en la tendencia. Cuando se selecciona la ventana retrospectiva de seis horas, los resultados de las recomendaciones se actualizan cada 3-6 horas a lo largo del día.<br>Para obtener más información, consulte  [Fuente ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) de datos en  *Crear criterios*. |

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
