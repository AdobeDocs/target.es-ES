---
keywords: debug mbox;troubleshoot mbox;mbox issues;flicker;mboxDebug;mboxTrace;token;debugger;priority;activity priority;Adobe Experience Cloud Debugger;orderConfirmPage mbox;SiteCatalyst  purchase mbox;top selling;top seller
description: Si su página no muestra el contenido esperado, puede seguir algunos pasos para depurar el envío de contenido en Adobe Target.
title: Solución de problemas de envío de contenido en Adobe Target
feature: activities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 60%

---


# Resolución de problemas de la entrega de contenido{#troubleshoot-content-delivery}

Si su página no muestra el contenido esperado, puede seguir algunos pasos que le ayudarán a depurar la publicación de contenido.

* Compruebe detenidamente el código de campaña o de actividad. No se mostrará el contenido esperado si el código tiene un error tipográfico o de cualquier otro tipo.
* Use mboxTrace or mboxDebug to troubleshoot the [!DNL Target] request.
* Use the Adobe Experience Cloud Debugger, an easy-to-use tool that provides much of the same information as mboxDebug, to troubleshoot the [!DNL Target] request.

mboxDebug is especially useful when you are setting up [!DNL Target] on your page to make sure the [!DNL Target] request is firing and the cookie is being set. Sin embargo, no muestra el tipo de detalles que resulta útil cuando se quiere depurar la publicación de contenido. Si su actividad no se muestra en la página o se muestra contenido no deseado, utilice mboxTrace para examinar la página y depurarla en detalle.

## Retrieve the authorization token to use with debugging tools {#section_BED130298E794D1FA229DB7C3358BA54}

Dado que mboxTrace y mboxDebug pueden exponer los datos de la campaña y los datos del perfil a terceros externos, se requiere un token de autorización. El token de autorización se puede obtener desde la interfaz de usuario de [!DNL Target]. El token es válido durante seis horas.

Debe tener uno de los siguientes permisos de usuario para generar un autentificador:

* Al menos [!UICONTROL permiso del editor] (o [!UICONTROL aprobador])

   Para obtener más información sobre [!DNL Target Standard] los clientes, consulte [Especificación de funciones y permisos](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *usuarios*. Para obtener más información sobre [!DNL Target Premium] los clientes, consulte [Configuración de permisos](/help/administrating-target/c-user-management/property-channel/properties-overview.md)de empresa.

* Función de administrador en el nivel de espacio de trabajo/perfil del producto

   Los espacios de trabajo solo están disponibles para [!DNL Target Premium] los clientes. For more information, see [Configure enterprise permissions](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Derechos de administrador (permiso de Sysadmin) en el nivel de [!DNL Adobe Target] producto

Para obtener el token de autorización:

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.
1. En la sección Herramientas del depurador, haga clic en **[!UICONTROL Generar nuevo autentificador]**.

   ![Generar nuevo token de autenticación](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Agregue el token generado como un parámetro a la URL para habilitar una de las herramientas de depuración avanzadas.

   ![Token de autorización](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

mboxTrace enables you to receive trace information attached to [!DNL Target] responses. Trace information reflects the outcome of a [!DNL Target] call (for example, a conversion or an impression) and any additional data that may help in determining why this particular outcome happened, such as a set of available branches among which the selection was made in a campaign. Utilice esta información para depurar la publicación de contenido.

Están disponibles los siguientes parámetros:

| Opciones de mboxTrace | Resultado |
|--- |--- |
| `?mboxTrace=console` | Imprime en el registro de la consola como objetos.<br>Para at.js, en lugar de abrir una nueva ventana del navegador o generar la salida a la consola, como en mbox.js, deberá inspeccionar la solicitud de red y mirar en la opción de vista previa (Chrome) o en la opción de respuesta (Firefox). |
| `?mboxTrace=json` | Imprime en el registro de la consola como una cadena JSON literal |
| `?mboxTrace=window` | Imprime en una ventana emergente como una cadena JSON |
| `?mboxTrace=disable` | Desactiva el modo de sesión de seguimiento. |

**Ejemplo de llamada a mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

El resultado muestra información muy detallada sobre su contenido. mboxTrace muestra los detalles sobre su campaña o su actividad y perfil. También ofrece una instantánea del perfil antes de la ejecución y una instantánea de lo que cambió después de la ejecución. También muestra qué campañas o actividades se evaluaron para cada ubicación.

Entre esta información se incluyen los ID de objetivo y los segmentos con coincidencia y sin coincidencia.

* **SegmentId**: los ID de segmentos, procedentes de la biblioteca de segmentos reutilizables o segmentos anónimos creados para esa campaña en particular.
* **TargetId**: los ID de objetivos, procedentes de la biblioteca de expresiones de objetivos u objetivos anónimos para cualquier segmento de una campaña.
* **Unmatched**: la solicitud no cumplió los requisitos en esta llamada para aquellos segmentos u objetivos.
* **Matched**: la solicitud cumplió los requisitos para los segmentos u objetivos especificados.

**Uso de mboxTrace en páginas** de recomendaciones: Al añadir mboxTrace como parámetro de consulta en páginas con recomendaciones, se reemplaza el diseño de Recommendations en la página por una ventana de detalles de mboxTrace, que muestra información detallada sobre las recomendaciones, como:

* Recomendaciones devueltas frente a recomendaciones solicitadas
* La clave utilizada y si está generando recomendaciones
* Recomendaciones generadas a partir de criterios frente a recomendaciones de copia de seguridad
* Configuración de los criterios
* Exclusiones e inclusiones aplicadas
* Reglas de recopilación

No tiene que incluir  `=console`, `=json` ni `=window` en el parámetro de consulta. Cuando termine con los detalles de mboxTrace, agregue `=disable` y pulse **[!UICONTROL Intro]** para volver al modo de visualización normal.

mboxTrace no afecta a la apariencia ni al funcionamiento normal de su sitio. Los visitantes verán su diseño habitual de Recommendations.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, añada un parámetro de mboxDebug al final de la dirección URL. The following table contains information about [!DNL Target] response-related URL parameters.

>[!NOTE]
>
>Algunos parámetros de mboxDebug están disponibles con o sin autenticación.

| Parámetros de URL | Finalidad |
|--- |--- |
| `mboxDebug=1` | <br>DepuradorAl agregar este parámetro a cualquier URL con solicitudes de Destinatario definidas, se abre una ventana emergente con detalles de depuración valiosos. Se detalla la información de cookies y los valores PCid y Session ID. Además, todas las direcciones URL de están visibles. Click on a Target request URL to show the response for that [!DNL Target] request. En [mbox_debug.pdf](/help/assets/mbox_debug.pdf) encontrará más información. |
| `mboxDebug=x-cookie` | Modifique la cookie |
| `mboxDisable=1` | Deshabilitar los mboxes de la página |
| `mboxDebug=x-profile` | Ver los perfiles definidos. |
| `mboxDebug=x-time` | Show response time for each [!DNL Target] request |
| `mboxOverride.browserIp=<Insert IP address>` | Pruebe Geotargeting<br>Pruebe Geotargeting con este parámetro de URL. Escriba una dirección IP como valor para este atributo. La segmentación geográfica de Test&amp;Target evalúa esa dirección IP para compararla con cualquier segmentación geográfica o conjunto de segmentación definido en una campaña. |

>[!NOTE]
>
>Asegúrese de que el fragmento de URL se encuentra después de los parámetros de cadena de consulta. Cualquier cosa después de la primera `#` es un identificador de fragmento y hace que los parámetros de depuración no funcionen correctamente.

## Adobe Experience Cloud Debugger.  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger le permite entender de forma rápida y sencilla su implementación de Target. Puede ver rápidamente la configuración de la biblioteca, examinar las solicitudes para asegurarse de que los parámetros personalizados se pasan correctamente, activar el registro de consola y desactivar todas las solicitudes de Target. Autentique al Experience Cloud y puede utilizar la poderosa herramienta MboxTrace para inspeccionar sus calificaciones de actividad y audiencia, así como su perfil de visitante.

Para obtener más información, consulte los vídeos de formación siguientes:

Para obtener más información, consulte [Depuración de at.js mediante el depurador](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)de Adobe Experience Cloud.

## Si target.js no se puede cargar durante la entrega {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

Mbox.js envía una cookie denominada “em-disabled” al visitante si target.js no se puede cargar durante la entrega. Esta cookie impide que las ofertas creadas con el Compositor de experiencias visuales se procesen en el sitio. Los visitantes con esta cookie no ven el contenido de prueba ni se cuentan en esos informes de actividades. Todo el demás contenido de ofertas (de campañas en Target Classic, por ejemplo) sigue cargándose. La cookie tiene una vida útil de 30 minutos desde el momento del error en la carga.

## Los principales vendedores no aparecen en Recommendations.  {#section_3920C857270A406C80BE6CBAC8221ECD}

The *`SiteCatalyst: purchase`* call can&#39;t be used for Purchase algorithm traffic data. En su lugar, utilice la *`orderConfirmPage`* llamada.

## Check activity priority {#section_3D0DD07240F0465BAF655D0804100AED}

Form-based activities created with [!DNL Target Standard/Premium] might collide with activities created in the [!DNL Target Classic] UI that have the same priority and use the same [!DNL Target] request.

## El código personalizado no produce los resultados esperados en Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target ya no admite IE8.

## JavaScript content delivered by the global [!DNL Target] request doesn&#39;t load when using mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Actualice a la versión 58 o posterior de [!DNL mbox.js].

mbox.js version 58 and later executes non-JavaScript content for the global [!DNL Target] request immediately after the HTML `BODY` tag is present. JavaScript content inside `<script>` tags for the global [!DNL Target] request executes after the `DOMContentLoaded` event is fired. This order of content delivery ensures that JavaScript content for the global [!DNL Target] request is delivered and rendered properly.

## Target cookie does not get set {#section_77AFEB541C0B495EB67E29A4475DF960}

Si su sitio tiene un subdominio, como [!DNL us.domain.com], pero necesita establecer la cookie de Target en [!DNL domain.com] (en lugar de [!DNL us.domain.com]), tiene que anular el valor de configuración `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## El contenido de Target parpadea o no se muestra si un elemento también es parte de una personalización AEM. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Si un elemento DOM es parte de una segmentación de personalización de Adobe Experience Manager (AEM) y una actividad de Target, el contenido de Target puede parpadear o no mostrarse.

A fin de remediar esto, puede deshabilitar la personalización de AEM en las páginas en las que Target se está ejecutando.

## Las ofertas de redirección y remotas no se pueden entregar debido a una dirección URL no válida.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Si la oferta de redirección o remota utiliza una dirección URL no válida, es posible que no se pueda entregar.

For redirect offers, the [!DNL Target] response can contain `/* invalid redirect offer URL */`

O

For remote offers, the [!DNL Target] response can contain `/* invalid remote offer URL */`

You can check the [!DNL Target] response in the browser or using mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obtener más información sobre las direcciones URL válidas.

## Las solicitudes de destinatario no se activan en mi sitio.

at.js no activa solicitudes de Destinatario si está utilizando un tipo de documento no válido. at.js requiere el tipo de documento HTML 5.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Agregar la extensión ![Insignia de tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### Distintivo de ![tutorial básico de depuración de Destinatario](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Distintivo de ![tutorial de seguimiento de mbox](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)