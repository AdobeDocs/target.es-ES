---
description: Si su página no muestra el contenido esperado, puede seguir algunos pasos que le ayudarán a depurar la publicación de contenido.
keywords: depurar mbox;problemas de mbox;solucionar problemas de mbox;parpadeo;mboxDebug;mboxTrace;token;depurador;prioridad;prioridad de actividad;Adobe Experience Cloud Debugger;mbox orderConfirmPage;SiteCatalyst;mbox compra;más vendidos;más vendido
seo-description: Si su página no muestra el contenido esperado, puede seguir algunos pasos para depurar la entrega de contenido en Adobe Target.
seo-title: Solución de problemas de entrega de contenido en Adobe Target
solution: Target
subtopic: Prueba multivariable
title: Resolución de problemas de la entrega de contenido
topic: Standard
uuid: 8837d07a-f793-495e-a6c1-b9c35fbe18b1
translation-type: tm+mt
source-git-commit: 4d0800bd205d6f14ddbc67f9e32510676ffa0d5b

---


# Resolución de problemas de la entrega de contenido{#troubleshoot-content-delivery}

Si su página no muestra el contenido esperado, puede seguir algunos pasos que le ayudarán a depurar la publicación de contenido.

* Compruebe detenidamente el código de campaña o de actividad. No se mostrará el contenido esperado si el código tiene un error tipográfico o de cualquier otro tipo.
* Utilice mboxTrace o mboxDebug para solucionar el problema con mbox.
* Use Adobe Experience Cloud Debugger, una herramienta muy sencilla que ofrece casi toda la información que proporciona mboxDebug, para solucionar los problemas de mbox.

mboxDebug resulta especialmente útil cuando está configurando Target en su página, para asegurarse de que mbox se activa y se establece la cookie. Sin embargo, no muestra el tipo de detalles que resulta útil cuando se quiere depurar la publicación de contenido. Si su actividad no se muestra en la página o se muestra contenido no deseado, utilice mboxTrace para examinar la página y depurarla en detalle.

## Recuperar el token de autorización para utilizarlo con las herramientas de depuración {#section_BED130298E794D1FA229DB7C3358BA54}

Dado que mboxTrace y mboxDebug pueden exponer los datos de la campaña y los datos del perfil a terceros externos, se requiere un token de autorización. El token de autorización se puede obtener desde la interfaz de usuario de [!DNL Target]. El token es válido durante seis horas.

Para obtener el token de autorización:

1. Haga clic en **[!UICONTROL Configuración]** &gt; **[!UICONTROL Implementación]**.
1. Seleccione **[!UICONTROL mbox.js]** o **[!UICONTROL at.js]**.
1. Haga clic en **[!UICONTROL Generar token de autorización]**.

   ![Generar Token de autorización](/help/c-activities/c-troubleshooting-activities/assets/generate-auth-token.png)

1. Agregue el token generado como un parámetro a la URL para habilitar una de las herramientas de depuración avanzadas.

   ![Token de autorización](/help/c-activities/c-troubleshooting-activities/assets/gen-auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

Con mboxTrace, puede recibir información de seguimiento adjunta a las respuestas de mbox. La información de seguimiento refleja el resultado de una llamada de mbox (por ejemplo, una conversión o una impresión) y cualquier otro dato que pueda resultar útil para determinar por qué se produjo este resultado concreto, como un conjunto de ramas disponibles junto con la selección que se realizó en una campaña. Utilice esta información para depurar la publicación de contenido.

Están disponibles los siguientes parámetros:

| Opciones de mboxTrace | Resultado |
|--- |--- |
| `?mboxTrace=console` | Imprime en el registro de la consola como objetos.<br>Para at.js, en lugar de abrir una nueva ventana del navegador o generar la salida a la consola, como en mbox.js, deberá inspeccionar la solicitud de red y mirar en la opción de vista previa (Chrome) o en la opción de respuesta (Firefox). |
| `?mboxTrace=json` | Imprime en el registro de la consola como una cadena JSON literal |
| `?mboxTrace=window` | Imprime en una ventana emergente como una cadena JSON |
| `?mboxTrace=disable` | Desactiva el modo de sesión de seguimiento. |

**Ejemplo de llamada de mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

El resultado muestra información muy detallada sobre su contenido. mboxTrace muestra los detalles sobre su campaña o su actividad y perfil. También ofrece una instantánea del perfil antes de la ejecución y una instantánea de lo que cambió después de la ejecución. También muestra qué campañas o actividades se evaluaron para cada ubicación.

Entre esta información se incluyen los ID de objetivo y los segmentos con coincidencia y sin coincidencia.

* **SegmentId**: los ID de segmentos, procedentes de la biblioteca de segmentos reutilizables o segmentos anónimos creados para esa campaña en particular.
* **TargetId**: los ID de objetivos, procedentes de la biblioteca de expresiones de objetivos u objetivos anónimos para cualquier segmento de una campaña.
* **Unmatched**: la solicitud no cumplió los requisitos en esta llamada para aquellos segmentos u objetivos.
* **Matched**: la solicitud cumplió los requisitos para los segmentos u objetivos especificados.

**Uso de mboxTrace en las páginas de Recommendations**: al agregar mboxTrace como un parámetro de consulta en páginas con recomendaciones, se sustituye el diseño de Recommendations de la página por una ventana de detalles de mboxTrace, que muestra información exhaustiva sobre sus recomendaciones, incluido lo siguiente:

* Recomendaciones devueltas frente a recomendaciones solicitadas
* La clave utilizada y si está generando recomendaciones
* Recomendaciones generadas a partir de criterios frente a recomendaciones de copia de seguridad
* Configuración de los criterios
* Exclusiones e inclusiones aplicadas
* Reglas de recopilación

No tiene que incluir  `=console`, `=json` ni `=window` en el parámetro de consulta. Cuando termine con los detalles de mboxTrace, agregue `=disable` y pulse **[!UICONTROL Intro]** para volver al modo de visualización normal.

mboxTrace no afecta a la apariencia ni al funcionamiento normal de su sitio. Los visitantes verán su diseño habitual de Recommendations.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, añada un parámetro de mboxDebug al final de la dirección URL. La tabla siguiente contiene información sobre los parámetros de URL relacionados con mbox.

>[!NOTE]
>
>Algunos parámetros de mboxDebug están disponibles con o sin autenticación.

| Parámetros de URL | Finalidad |
|--- |--- |
| `mboxDebug=1` | Debugger<br>Si se añade este parámetro a cualquier dirección URL con mboxes definidos, se abrirá una ventana emergente con detalles importantes sobre la depuración. Se detalla la información de cookies y los valores PCid y Session ID. Además, todas las direcciones URL de mbox están visibles. Haga clic en una dirección URL de mbox si desea mostrar las respuestas para ese mbox. En [mbox_debug.pdf](/help/assets/mbox_debug.pdf) encontrará más información. |
| `mboxDebug=x-cookie` | Modifique la cookie |
| `mboxDisable=1` | Deshabilitar los mboxes de la página |
| `mboxDebug=x-profile` | Ver los perfiles definidos. |
| `mboxDebug=x-time` | Mostrar el tiempo de respuesta de cada solicitud de mbox |
| `mboxOverride.browserIp=<Insert IP address>` | Pruebe Geotargeting<br>Pruebe Geotargeting con este parámetro de URL. Escriba una dirección IP como valor para este atributo. La segmentación geográfica de Test&amp;Target evalúa esa dirección IP para compararla con cualquier segmentación geográfica o conjunto de segmentación definido en una campaña. |

>[!NOTE]
>
>Asegúrese de que el fragmento de URL se encuentra después de los parámetros de cadena de consulta. Cualquier cosa después de la primera `#` es un identificador de fragmento y hace que los parámetros de depuración no funcionen correctamente.

## Adobe Experience Cloud Debugger.  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger le permite entender de forma rápida y sencilla su implementación de Target. Puede ver rápidamente la configuración de la biblioteca, examinar las solicitudes para asegurarse de que los parámetros personalizados se pasan correctamente, activar el registro de consola y desactivar todas las solicitudes de Target. Si se autentica en Experience Cloud, podrá utilizar la potente herramienta Mbox Trace para inspeccionar su actividad, las cualificaciones de audiencia y el perfil del visitante.

Para obtener más información, consulte los vídeos de formación siguientes:

Para obtener más información, consulte [Depuración de at.js con el depurador](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md)de Adobe Experience Cloud.

## Si target.js no se puede cargar durante la entrega {#section_ABBA5EFDFFB749D8BEE172DB1F973058}

Mbox.js envía una cookie denominada “em-disabled” al visitante si target.js no se puede cargar durante la entrega. Esta cookie impide que las ofertas creadas con el Compositor de experiencias visuales se procesen en el sitio. Los visitantes con esta cookie no ven el contenido de prueba ni se cuentan en esos informes de actividades. Todo el demás contenido de ofertas (de campañas en Target Classic, por ejemplo) sigue cargándose. La cookie tiene una vida útil de 30 minutos desde el momento del error en la carga.

## Los principales vendedores no aparecen en Recommendations.  {#section_3920C857270A406C80BE6CBAC8221ECD}

No se puede usar el *`SIteCatalyst: purchase`* de mbox para los datos del tráfico del algoritmo Compra. Utilice el *`orderConfirmPage`* de mbox en su lugar.

## Comprobar la prioridad de las actividades {#section_3D0DD07240F0465BAF655D0804100AED}

Las actividades basadas en formularios y creadas con [!DNL Target Standard/Premium] pueden chocar con las actividades creadas en la interfaz de usuario de [!DNL Target Classic] que tienen la misma prioridad y usan el mismo mbox.

## El código personalizado no produce los resultados esperados en Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target ya no admite IE8.

## El contenido de JavaScript que entrega el mbox global no se carga al usar mbox.js. {#section_03EC9B9C410B4F52A7FCD81840311709}

Actualice a la versión 58 o posterior de [!DNL mbox.js].

Las versiones 58 y posteriores de mbox.js ejecutan contenido que no es de JavaScript para el mbox global inmediatamente después de la etiqueta `BODY` de HTML. El contenido de JavaScript que está dentro de las etiquetas `<script>` para el mbox global se ejecuta una vez activado el evento `DOMContentLoaded`. Este orden en la entrega de contenido garantiza que el contenido de JavaScript para el mbox global se entregue y represente adecuadamente.

## La cookie de Target no se puede establecer.  {#section_77AFEB541C0B495EB67E29A4475DF960}

Si su sitio tiene un subdominio, como [!DNL us.domain.com], pero necesita establecer la cookie de Target en [!DNL domain.com] (en lugar de [!DNL us.domain.com]), tiene que anular el valor de configuración `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## El contenido de Target parpadea o no se muestra si un elemento también es parte de una personalización AEM. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Si un elemento DOM es parte de una segmentación de personalización de Adobe Experience Manager (AEM) y una actividad de Target, el contenido de Target puede parpadear o no mostrarse.

A fin de remediar esto, puede deshabilitar la personalización de AEM en las páginas en las que Target se está ejecutando.

## Las ofertas de redirección y remotas no se pueden entregar debido a una dirección URL no válida.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Si la oferta de redirección o remota utiliza una dirección URL no válida, es posible que no se pueda entregar.

Para las ofertas de redireccionamiento, la respuesta de mbox puede contener `/* invalid redirect offer URL */`

O

Para ofertas remotas, la respuesta de mbox puede contener `/* invalid remote offer URL */`

Puede comprobar la respuesta del mbox en el navegador o utilizar mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obtener más información sobre las direcciones URL válidas.

## mboxes no se activan en mi sitio.

at.js no activa mboxes de Target si utiliza un doctype no válido. at.js requiere el tipo de documento HTML 5.

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Agregar la extensión

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/?captions=spa)

### Depuración básica de Target

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/?captions=spa)

### Mbox Trace

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/?captions=spa)