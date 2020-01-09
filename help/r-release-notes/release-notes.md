---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 5b13ad02691a685dd76db2b390e030f8aef30dd9

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Target, los SDK, la biblioteca JavaScript (at.js) y otros cambios en la plataforma, si procede.

>[!IMPORTANT]
>
>A partir del 1 de marzo de 2020, Target desactivará la compatibilidad con el cifrado TLS 1.1 y TLS 1.0. Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. Este cambio es necesario para cumplir el estándar de cumplimiento de seguridad generalmente aceptado de TLS 1.2 o superior. Compruebe qué versión de TLS está utilizando actualmente. Si su versión es menor que 1.2, implemente los cambios necesarios antes del 1 de marzo de 2020 para seguir usando Target como se espera.
>
> Para obtener información detallada sobre el posible impacto y los pasos que debe seguir para actualizar la implementación, consulte Cambios [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)de codificación TLS (Transport Layer Security).

Los números entre paréntesis son para uso interno de [!DNL Adobe].

## SDK de Java de Target versión 1.1.0 (16 de diciembre de 2019)

* Se agregó compatibilidad con la configuración proxy debido a una contribución de código abierto de @hisham-hassan.

Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)de Java de Target.

## SDK de Java de Target versión 1.0.1 (11 de noviembre de 2019)

Se ha solucionado el siguiente problema en la versión 1.0.1:

* Envíe un ID de datos suplementario en una solicitud de Target incluso cuando no haya una cookie de API de visitante presente.

Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)de Java de Target.

## Plataforma de Target (31 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| Java SDK | El SDK de [!DNL Target] Java permite implementar [!DNL Target] el servidor. Este SDK de Java le ayuda a integrarse fácilmente [!DNL Target] con otras [!DNL Adobe Experience Cloud] soluciones, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]y [!DNL Adobe Audience Manager].<br>El SDK de Java introduce prácticas recomendadas y elimina las complejidades al realizar la integración con [!DNL Target] mediante nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial. Las siguientes son funciones destacadas que presentamos en la versión más reciente:<ul><li>Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché.</li><li>Compatibilidad para optimizar el rendimiento cuando se dispone de una integración híbrida de [!DNL Target] en las páginas web y en el servidor. Estamos introduciendo una configuración llamada `serverState` que se rellena con las experiencias recuperadas a través del servidor para que at.js 2.2 ya no realice una llamada adicional al servidor para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.</li><li>Compatibilidad con la recuperación de actividades creadas por VEC mediante el SDK de Java, lo cual es posible gracias a la nueva API de envío.</li><li>Abra el código fuente para que los desarrolladores puedan contribuir al SDK [de Java de](https://github.com/adobe/target-java-sdk)Target.</li></ul>Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)de Java de Target.<br>Obtenga más información sobre el SDK de Java de Target en el blog técnico de Adobe: Optimización del lado del [servidor con el nuevo SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)de Java de Target. |

## Target Standard/Premium 19.10.2 (31 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Atributos de varios valores de distintivo](/help/assets/premium.png) Premium | A veces desea trabajar con un campo de varios valores. Veamos los siguientes ejemplos:<ul><li>Puede ofrecer películas a los usuarios. Una película determinada tiene múltiples actores.</li><li>Vendes entradas a conciertos. Un usuario determinado tiene varias bandas favoritas.</li><li>Vendes ropa. Hay una camisa disponible en varios tamaños.</li></ul>Para administrar las recomendaciones en estos escenarios, puede pasar datos de varios valores a Recomendaciones de Target y usar operadores especiales de varios valores.<br>Para obtener más información, consulte [Trabajo con atributos](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md)de varios valores. |

## Target Standard/Premium 19.10.1 (22 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) Recomendaciones<br>basadas en el usuario (24 de octubre de 2019) | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como &quot;Recomendado para usted&quot;.<br>Este criterio le permite entregar contenido y experiencias personalizados tanto a visitantes nuevos como a visitantes que regresan. La lista de recomendaciones se centra en la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el visitante navega por el sitio.<br>Para obtener más información, consulte &quot;Recomendaciones basadas en el usuario&quot; en [Criterios/Algoritmos](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms). |

### Navegación de Adobe Experience Cloud

* Al iniciar sesión en el [!DNL Adobe Experience Cloud], se le dirigirá a la nueva navegación de encabezado. Se parece mucho a la navegación anterior con la barra negra en la parte superior, pero ofrece las siguientes mejoras:

   * Cambio más fácil entre organizaciones [!DNL Identity Management System] (IMS) o con una solución diferente.
   * Se ha mejorado la ayuda del usuario: Los resultados de la búsqueda incluyen los resultados de la documentación del [!DNL Target] producto, así como los foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido [!DNL Target]. También hemos agregado un mecanismo de comentarios en el menú [!UICONTROL Ayuda] , lo que facilita informar sobre problemas o compartir ideas.

   * Se ha mejorado la funcionalidad de comentarios de Net Promoter Score (NPS), de modo que el modo de estudio no interrumpe el flujo de trabajo.
   * Se ha mejorado el flujo de inicio de sesión. Anteriormente, todos [!DNL Target] los clientes aterrizaban en la página de aterrizaje de Target después de hacer clic en el [!DNL Target] icono del encabezado. A continuación, esta página permite a los clientes avanzar con [!DNL Target Standard/Premium], [!DNL Search&Promote]o [!DNL Recommendations Classic], como se muestra a continuación:

      ![Página de destino](/help/r-release-notes/assets/landing.png)

      Hemos eliminado esta página de aterrizaje para todos nuestros clientes. Ahora siempre se le dirigirá directamente a la página Lista [!UICONTROL de] actividades haciendo clic en el [!DNL Target] icono de la nueva barra de navegación de encabezado.

      Si utiliza [!DNL Recommendations Classic], puede ir directamente a la solución o puede ir desde el vínculo corto creado en la ficha [!UICONTROL Recomendaciones] , como se muestra a continuación:

      ![Vínculo profundo de Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Si utiliza [!DNL Search&Promote], debe ir directamente a la dirección URL [de](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). Se ha eliminado completamente la ruta [!DNL Search&Promote] de acceso desde el interior de [!DNL Adobe Target] .

   * Las notificaciones para [!DNL Target] no están disponibles actualmente en la lista desplegable [!UICONTROL Notificaciones] del encabezado.
   >[!NOTE]
   >
   >Estas funciones no se implementarán a la vez ni se distribuirán a todos los clientes. Estas funciones se implementarán durante las próximas semanas, a partir de la versión [!DNL Target Standard/Premium] 19.10.1 (22 de octubre de 2019).
   >
   >Como parte de la implementación de la nueva barra de navegación, también verá algunos cambios en la dirección URL. Todos los vínculos con marcador anteriores siguen funcionando pero le recomendamos que marque nuevos vínculos para una apertura más rápida.

## Versión 2.2 y 1.8 de at.js (10 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| Versión 2.2.<br><br>y at.js versión 1.8 de at.js | Estas versiones de at.js proporcionan:<ul><li>Se ha mejorado el rendimiento al usar tanto el servicio Experience Cloud ID (ECID) v4.4 como at.js 2.2 o at.js 1.8 en las páginas web.</li><li>Anteriormente, el ECID realizaba dos llamadas de bloqueo antes de que at.js pudiera recuperar experiencias. Esto se ha reducido a una sola llamada, lo que mejora significativamente el rendimiento.</li></ul> Para aprovechar estas mejoras de rendimiento, actualice a at.js 2.2 o at.js 1.8 junto con la biblioteca ECID v4.4.<br>at.js 2.2 proporciona:<ul><li>**serverState**: Una configuración disponible en at.js v2.2+ que se puede utilizar para optimizar el rendimiento de la página cuando se implementa una integración híbrida de Target. La integración híbrida significa que está utilizando at.js v2.2+ en el cliente y la API de entrega o un SDK de Target en el servidor para ofrecer experiencias. `serverState` proporciona a at.js v2.2+ la capacidad de aplicar experiencias directamente desde el contenido recuperado en el servidor y devuelto al cliente como parte de la página que se está ofreciendo.<br>Para obtener más información, consulte &quot;serverState&quot; en [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |

## Plataforma de Target (9 de octubre de 2019)

| Función.  / Mejora | Descripción |
| --- | --- |
| SDK de Node.js versión 1.0 | El SDK de Node.js de Target permite implementar Target en el servidor.<br>Este SDK de Node.js ayuda a integrar fácilmente Target con otras soluciones de Experience Cloud, como el servicio de identidad de Adobe Experience Cloud, Adobe Analytics y Adobe Audience Manager.<br>El SDK de Node.js introduce prácticas recomendadas y elimina las complejidades al integrarse con Adobe Target a través de nuestra API de entrega, de modo que sus equipos de ingeniería puedan centrarse en la lógica empresarial. Las siguientes son funciones destacadas que presentamos en la versión más reciente:<ul><li>Compatibilidad con la recuperación previa y las notificaciones que le permiten optimizar el rendimiento mediante almacenamiento en caché.</li><li>Compatibilidad para optimizar el rendimiento cuando se dispone de una integración híbrida de Target en las páginas web y en el servidor. Estamos introduciendo una configuración llamada `serverState` que se rellenará con las experiencias recuperadas a través del servidor para que at.js 2.2 ya no realice una llamada adicional al servidor para recuperar las experiencias. Este método optimiza el rendimiento de carga de la página.</li><li> Compatibilidad con la recuperación de actividades creadas por VEC mediante el SDK de Node.js, lo cual es posible gracias a la nueva API de envío.</li><li>Abra source para que los desarrolladores puedan contribuir al SDK de Node.js.</li></ul><br>Para obtener más información, consulte [Notas de la versión: SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)de Target Node.js.<br>Obtenga más información sobre el SDK de Node.js de Target en el blog de tecnología de Adobe: [Abrir desde el nuevo SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)de Node.js de Adobe Target. |
| API de envío | Hay disponible un punto final de la API de entrega completamente nuevo (/v1/delivery) en producción. Las características destacables son:<ul><li>Un punto final para recuperar experiencias para uno o varios mboxes.</li><li>Recupere actividades creadas por VEC mediante la API.</li><li>Compatibilidad con un objeto completamente nuevo llamado Vistas que se utiliza en aplicaciones de una sola página (SPA) y aplicaciones móviles.</li></ul><br>Para obtener más información, consulte [Notas de la versión: API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)de servidor de Target. |

## Notas de la versión adicionales y detalles de la versión

| Recurso | Detalles |
|--- |--- |
| [Notas de la versión: API de servidor de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de la versión relacionadas con las API del servidor de Adobe Target. |
| [Notas de la versión: SDK de Node.js de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de la versión relacionadas con el SDK Node.js de Adobe Target. |
| [Notas de la versión: SDK de Java de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de la versión relacionadas con el SDK de Java de Adobe Target. |
| [Detalles de las versiones de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalles sobre los cambios en cada versión de la biblioteca JavaScript de Adobe Target at.js. |
| [Detalles de la versión de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página muestra cambios realizados a cada versión de mbox.js.<br>Tenga en cuenta que la biblioteca mbox.js ya no se está desarrollando. Todos los clientes deberían migrar de mbox.js a at.js. |

## Cambios de la documentación, notas de versiones anteriores y notas de la versión de Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Además de las notas de cada versión, los recursos siguientes también contienen información adicional:

| Recurso | Detalles |
|--- |--- |
| Cambios de la documentación | Vea información detallada sobre las actualizaciones hechas a esta guía que pueden no haberse incluido en estas notas de la versión.<br>Para obtener más información, consulte [Cambios de la documentación](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de la versión para versiones anteriores | Vea información sobre las nuevas funciones y mejoras de las versiones anteriores de Target Standard y Target Premium.<br>Para obtener más información, consulte [Notas de versiones anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de la versión de Adobe Experience Cloud | Vea las notas de la última versión de las soluciones de Adobe Experience Cloud.<br>Para obtener más información, consulte las Notas de la versión [de Experience Cloud](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html). |

## Información previa a la publicación {#section_5D588F0415A2435B851A4D0113ACA3A0}

Los siguientes recursos le permiten ver qué novedades hay en la próxima versión de Target.

| Recurso | Detalles |
|--- |--- |
| Lista Adobe Priority Product Update | Para recibir notificaciones avanzadas sobre futuras mejoras de productos en Target y otras soluciones de Adobe Experience Cloud, regístrese en Adobe Priority Product Update:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Próximas notas de la versión | Si desea obtener información sobre las versiones de Target publicadas en el mes actual, como la información sobre la versión preliminar, visite la página de [Notas de la versión de Target: versión previa](/help/r-release-notes/target-release-notes.md). |
