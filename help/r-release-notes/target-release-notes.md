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
source-git-commit: 0a9cf0e98f5f833402b96f37df5513325222ad19

---


# Notas de la versión de Target (versión previa){#target-release-notes-prerelease}

En estas notas de la versión se proporciona información acerca de las funciones, las mejoras, las correcciones y los problemas conocidos de las últimas o de las próximas versiones de [!DNL Adobe Target].

**Última actualización: 17 de octubre de 2019**

>[!NOTE]
>
>Las presentes notas de la versión contienen información previa al lanzamiento. Las fechas del lanzamiento, las características y otras informaciones están sujetas a cambios sin previo aviso. Para obtener información acerca de la versión actual, consulte [Notas de la versión de Target](release-notes.md). La información de estas páginas puede ser la misma o diferir, según la hora de las versiones.
>
>Los números entre paréntesis son para uso interno de [!DNL Adobe].

## Plataforma de destino

| Función.  / Mejora | Descripción |
| --- | --- |
| SDK de Node.js versión 1.0<br>(9 de octubre de 2019) | El SDK de Node.js de Target permite implementar Target en el servidor.<br>Este SDK de Node.js ayuda a integrar fácilmente Target con otras soluciones de Experience Cloud, como el servicio de identidad de Adobe Experience Cloud, Adobe Analytics y Adobe Audience Manager.<br>El SDK de Node.js introduce prácticas recomendadas y elimina las complejidades al integrarse con Adobe Target a través de nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial. Las siguientes son funciones destacadas que presentamos en la versión más reciente:<ul><li>Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché.</li><li>Compatibilidad para optimizar el rendimiento cuando se dispone de una integración híbrida de Target en las páginas web y en el servidor. Estamos introduciendo una configuración llamada `serverState` que se rellenará con las experiencias recuperadas a través del servidor para que at.js 2.2 ya no realice una llamada adicional al servidor para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.</li><li> Compatibilidad con la recuperación de actividades creadas por VEC mediante el SDK de Node.js, lo cual es posible gracias a la nueva API de envío.</li><li>Abra source para que los desarrolladores puedan contribuir al SDK de Node.js.</li></ul>Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)de Target Node.js. |
| API<br>de envío (9 de octubre de 2019) | En la producción habrá disponible un extremo de la API de entrega completamente nuevo (/v1/delivery). Las características destacables son:<ul><li>Un punto final para recuperar experiencias para uno o varios mboxes.</li><li>Recupere actividades creadas por VEC mediante la API.</li><li>Compatibilidad con un objeto completamente nuevo llamado Vistas que se utiliza en aplicaciones de una sola página (SPA) y aplicaciones móviles.</li></ul>Para obtener más información, consulte [Notas de la versión: API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)de servidor de Target. |
| Versión 2.2.<br><br>y at.js de at.js versión 1.8<br>(10 de octubre de 2019) | Estas versiones de at.js proporcionan:<ul><li>Se ha mejorado el rendimiento al usar tanto el servicio Experience Cloud ID (ECID) v4.4 como at.js 2.2 o at.js 1.8 en las páginas web.</li><li>Anteriormente, el ECID realizaba dos llamadas de bloqueo antes de que at.js pudiera recuperar experiencias. Esto se ha reducido a una sola llamada, lo que mejora significativamente el rendimiento.</li></ul> Para aprovechar estas mejoras de rendimiento, actualice a at.js 2.2 o at.js 1.8 junto con la biblioteca ECID v4.4.<br>at.js 2.2 proporciona:<ul><li>**serverState**: Una configuración disponible en at.js v2.2+ que se puede utilizar para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Target. La integración híbrida significa que está utilizando at.js v2.2+ en el cliente y la API de entrega o un SDK de Target en el servidor para ofrecer experiencias. `serverState` proporciona a at.js v2.2+ la capacidad de aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está ofreciendo.<br>Para obtener más información, consulte "serverState" en [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |


## Target Standard/Premium 19.10.1 (22 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Premium](/help/assets/premium.png) Recomendaciones basadas en el usuario | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como "Recomendado para usted".<br>Este criterio le permite entregar contenido y experiencias personalizados tanto a visitantes nuevos como a visitantes que regresan. La lista de recomendaciones se centra en la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el visitante navega por el sitio. |

### Mejoras, correcciones y cambios

* Cambios en el shell unificado de Adobe.

   Adobe está actualizando el shell existente (la barra negra en la parte superior de [!DNL Experience Cloud] las soluciones) para unificar y mejorar su experiencia en todas [!DNL Adobe Experience Cloud] las soluciones.

   No hay cambios en los flujos de trabajo actuales y estos cambios aparentemente sencillos están diseñados para facilitar su vida de maneras pequeñas pero importantes.

   Al iniciar sesión en el [!DNL Adobe Experience Cloud], se le dirigirá al nuevo shell unificado. Tiene un aspecto muy similar al anterior Shell con la barra negra en la parte superior, pero ofrece las siguientes mejoras:

   * Cambio más fácil entre las organizaciones de Identity Management System (IMS) o una solución de Experience Cloud [!E] diferente.
   * Se ha mejorado la ayuda del usuario: Los resultados de la búsqueda incluyen los resultados de la documentación del [!DNL Target] producto, así como los foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido [!DNL Target]. También hemos agregado un mecanismo de comentarios en el menú Ayuda, lo que facilita informar sobre problemas o compartir ideas.
   * Se ha mejorado la funcionalidad de Net Promoter Score (NPS). A veces, algunos clientes veían [!DNL Target] las encuestas con una frecuencia mayor de la que esperábamos. Además, el modo de estudio utilizado para perturbar el flujo de trabajo. Hemos actualizado esta funcionalidad completamente para que se convierta en un pequeño estudio que ya no sea intrusivo. Además, con el nuevo diseño, podemos asegurar que la frecuencia del estudio esté mejor controlada.
   * Se ha mejorado el flujo de inicio de sesión. Anteriormente, todos [!DNL Target] los clientes aterrizaban en la página de aterrizaje de Target después de hacer clic en el icono [!DNL Target] del Shell. A continuación, esta página permite a los clientes continuar con [!DNL Target Standard/Premium], [!DNl Recommendations Classic]o [!DNL Search&Promote], como se muestra a continuación:

      ![Página de destino](/help/r-release-notes/assets/landing.png)

      Hemos eliminado esta página de aterrizaje para todos nuestros clientes. Ahora siempre se le dirigirá directamente a la página Lista [!UICONTROL de] actividades haciendo clic en el [!DNL Target] icono .

      Si utiliza [!DNL Recommendations Classic], puede ir directamente a la solución o puede ir desde el vínculo corto creado en la ficha [!UICONTROL Recomendaciones] , como se muestra a continuación:

      ![Vínculo profundo de Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si utiliza [!DNL Search&Promote], debe ir directamente al vínculo. La ruta para llegar a Search&amp;Promote desde dentro de [!DNL Adobe Target] se ha eliminado completamente.
   * Las notificaciones de ya no [!DNL Target] están visibles en la lista desplegable [!UICONTROL Notificaciones] en Shell.
   >[!NOTE]
   >
   >Estas funciones no se implementarán a la vez ni se distribuirán a todos los clientes. Estas funciones se implementarán en los próximos días a partir de la versión [!DNL Target Standard/Premium] 19.10.1 (22 de octubre de 2019).
   >
   >Como parte de la implementación del nuevo shell, también verá algunos cambios en la dirección URL. Todos los vínculos con marcador anteriores siguen funcionando pero le recomendamos que marque nuevos vínculos para una apertura más rápida.

## Información previa al lanzamiento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
