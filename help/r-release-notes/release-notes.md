---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Adobe Target Standard y Target Premium.
title: 'Notas de la versión de Adobe Target (actual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: dd8d7dfe058114183b75d104206393309bb8a789

---


# Notas de la versión de Target (actual){#target-release-notes-current}

Estas notas de la versión proporcionan información sobre características, mejoras, correcciones y problemas conocidos para todas las versiones de Target Standard y Target Premium. Además, también se incluyen las notas de la versión de las API de Target, los SDK, la biblioteca JavaScript (at.js) y otros cambios en la plataforma, cuando corresponde.

>[!NOTE]
>
>* **Cambios** de compatibilidad con TLS: A partir del 1 de marzo de 2020, Target desactivará la compatibilidad con el cifrado TLS 1.1 y TLS 1.0. Seguridad de capa de transporte (TLS) es el protocolo de seguridad más implementado que se usa hoy en día para navegadores web y otras aplicaciones que requieren que los datos se intercambien de forma segura en una red. Este cambio es necesario para cumplir el estándar de cumplimiento de seguridad generalmente aceptado de TLS 1.2 o superior. Compruebe qué versión de TLS está utilizando actualmente. Si su versión es menor que 1.2, implemente los cambios necesarios antes del 1 de marzo de 2020 para seguir usando Target como se espera.
   >
   >   
   Para obtener información detallada sobre el posible impacto y los pasos que debe seguir para actualizar la implementación, consulte Cambios [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)de codificación TLS (Transport Layer Security).
   >
   >
* **Desaprobación** de mbox.js: El 30 de agosto de 2020, Adobe Target ya no admitirá la biblioteca mbox.js. Después del 30 de agosto de 2020, todas las llamadas realizadas desde mbox.js producirán errores e impactarán en las páginas que tengan actividades de Target en ejecución. Recomendamos que todos los clientes migren a la versión más reciente de la biblioteca at.js antes de esta fecha para evitar problemas potenciales con sus sitios. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Aunque actualmente se admite mbox.js, no hemos proporcionado actualizaciones de funciones a esta biblioteca desde julio de 2017. La versión más reciente de at.js ofrece muchas ventajas con respecto a mbox.js. Entre otras ventajas, at.js mejora los tiempos de carga de página para implementaciones web, mejora la seguridad y proporciona mejores opciones de implementación para aplicaciones de una sola página.
   >
   >   
   Al trasladar a todos los clientes a at.js, nuestros ingenieros y el personal de asistencia técnica podrán proporcionarle nuevas funciones y ofrecerle la asistencia que espera de Adobe.
   >
   >
* Los números entre paréntesis son para uso interno de [!DNL Adobe].


## Target Standard/Premium 20.2.1 (9 de marzo de 2020). 

>[!IMPORTANT]
>
>Consulte la información anterior sobre la desaprobación de mbox.js.

Esta versión contiene las siguientes mejoras, correcciones y cambios:

* Se ha corregido un problema que impedía a los clientes seleccionar una colección al realizar una búsqueda en el catálogo. (TGT-36230)
* Se corrigió un problema en el cual un criterio creado mediante API, pero al que una actividad creada en la interfaz de usuario de Target no hace referencia, podía eliminarse erróneamente de la interfaz de usuario. (TGT-35917)
* Se han implementado mejoras de seguridad en la directiva de seguridad de contenido (CSP). (TGT-36190)
* Se ha corregido un problema que hacía que se mostrara &quot;NaN%&quot; al desplazar la barra de porcentaje Ponderación de atributo al extremo izquierdo. (TGT-36211)
* Se han resuelto problemas de localización para que el texto de la interfaz de usuario en varios idiomas se muestre correctamente.
* Las siguientes métricas de Adobe Analytics ya no son compatibles con Analytics para Target (A4T) con efecto a partir de la versión de Target de marzo de 2020:
   * averagevisitdepth
   * bots
* Las siguientes métricas ya no son compatibles y se convierten automáticamente en nuevas versiones de la métrica la primera vez que un usuario modifica una actividad que contiene la métrica:

   | Métrica obsoleta | Nueva métrica |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (nota: medida en minutos en lugar de segundos) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Navegación de Adobe Experience Cloud (22 de febrero de 2019)

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
   >Como parte de la implementación de la nueva barra de navegación, también verá algunos cambios en la dirección URL. Todos los vínculos con marcador anteriores siguen funcionando pero le recomendamos que marque nuevos vínculos para una apertura más rápida.

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
