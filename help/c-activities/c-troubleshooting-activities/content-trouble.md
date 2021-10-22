---
keywords: depurar mbox;problemas de mbox;solucionar problemas de mbox;parpadeo;mboxDebug;mboxTrace;token;depurador;prioridad;prioridad de actividad;Adobe Experience Cloud Debugger;mbox orderConfirmPage;SiteCatalyst;mbox compra;más vendidos;más vendido
description: Busque sugerencias para solucionar problemas si la página no muestra el contenido esperado. Aprenda a depurar la entrega de contenido en Adobe Target.
title: ¿Cómo se pueden solucionar los problemas en la entrega de contenido?
feature: Activities
exl-id: 887b7956-1d61-439a-8339-c150deb9a378
source-git-commit: b91e1be7d28085902110eb9d000dfa1113a54938
workflow-type: tm+mt
source-wordcount: '1628'
ht-degree: 68%

---

# Resolución de problemas de la entrega de contenido

Si su página no muestra el contenido esperado, puede seguir algunos pasos que le ayudarán a depurar la publicación de contenido.

* Compruebe detenidamente el código de campaña o de actividad. No se mostrará el contenido esperado si el código tiene un error tipográfico o de cualquier otro tipo.
* Utilice mboxTrace o mboxDebug para solucionar los problemas de la petición de [!DNL Target].
* Use Adobe Experience Cloud Debugger, una sencilla herramienta que ofrece gran parte de la información que proporciona mboxDebug, para solucionar los problemas de petición de [!DNL Target].

mboxDebug es especialmente útil cuando se configura [!DNL Target] en su página para asegurarse de que la solicitud de Target se está activando y que la cookie se está configurando. Sin embargo, no muestra el tipo de detalles que resulta útil cuando se quiere depurar la publicación de contenido. Si su actividad no se muestra en la página o se muestra contenido no deseado, utilice mboxTrace para examinar la página y depurarla en detalle.

## Recuperar el token de autorización para utilizarlo con las herramientas de depuración {#section_BED130298E794D1FA229DB7C3358BA54}

Dado que mboxTrace y mboxDebug pueden exponer los datos de la campaña y los datos del perfil a terceros externos, se requiere un token de autorización. El token de autorización se puede obtener desde la interfaz de usuario de [!DNL Target]. El token es válido durante seis horas.

Debe tener uno de los siguientes permisos de usuario para generar un token de autenticación:

* Al menos el permiso de [!UICONTROL Editor] (o [!UICONTROL Aprobador])

   Para obtener más información para los clientes de [!DNL Target Standard], consulte [Especificar funciones y permisos](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) en *Usuarios*. Para obtener más información para los clientes de [!DNL Target Premium], consulte [Configuración de permisos de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Función de administrador en el nivel de espacio de trabajo/perfil de producto

   Los espacios de trabajo solo están disponibles para los clientes de [!DNL Target Premium]. Para obtener más información, consulte [Permisos de usuario de Enterprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

* Derechos de administrador (permiso Sysadmin) en el nivel de producto [!DNL Adobe Target]

Para obtener el token de autorización:

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Implementación]**.
1. En la sección Herramientas de depurador, haga clic en **[!UICONTROL Generar nuevo token de autenticación]**.

   ![Generar nuevo token de autenticación](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/debugger-auth-token.png)

1. Agregue el token generado como un parámetro a la URL para habilitar una de las herramientas de depuración avanzadas.

   ![Token de autorización](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/assets/auth-token.png)

## mboxTrace {#section_256FCF7C14BB435BA2C68049EF0BA99E}

Con mboxTrace puede recibir información de seguimiento adjunta a las respuestas de [!DNL Target]. La información de seguimiento refleja el resultado de una llamada de [!DNL Target] (por ejemplo, una conversión o una impresión) y cualquier dato adicional que pueda ayudar a determinar por qué se produjo este resultado concreto, como un conjunto de ramas disponibles entre las que se realizó la selección en una campaña. Utilice esta información para depurar la publicación de contenido.

Están disponibles los siguientes parámetros:

| Opciones de mboxTrace | Resultado |
|--- |--- |
| `?mboxTrace=console` | Imprime en el registro de la consola como objetos.<br>Para at.js, en lugar de abrir una nueva ventana del explorador o generar la salida a la consola, como se hacía en mbox.js, debe inspeccionar la solicitud de red y mirar en la opción de vista previa (Chrome) o en la opción de respuesta (Firefox). |
| `?mboxTrace=json` | Imprime en el registro de la consola como una cadena JSON literal |
| `?mboxTrace=window` | Imprime en una ventana emergente como una cadena JSON |
| `?mboxTrace=disable` | Desactiva el modo de sesión de seguimiento. |

**Ejemplo de llamada de mboxTrace**

`https://www.mysite.com/page.html?mboxTrace=window&authorization=f543abf-0111-4061-9619-d41d665c59a6`

El resultado muestra información detallada sobre el contenido. mboxTrace muestra detalles sobre su campaña o actividad y perfil. También proporciona una instantánea del perfil antes de la ejecución y una instantánea de los cambios después de la ejecución. También muestra qué campañas o actividades se evaluaron para cada ubicación.

Entre esta información se incluyen los ID de objetivo y los segmentos con coincidencia y sin coincidencia.

* **SegmentId**: los ID de segmentos, procedentes de la biblioteca de segmentos reutilizables o segmentos anónimos creados para esa campaña en particular.
* **TargetId**: los ID de objetivos, procedentes de la biblioteca de expresiones de objetivos u objetivos anónimos para cualquier segmento de una campaña.
* **Unmatched**: la solicitud no cumplió los requisitos en esta llamada para aquellos segmentos u objetivos.
* **Matched**: la solicitud cumplió los requisitos para los segmentos u objetivos especificados.

**Uso de mboxTrace en las páginas de recomendaciones**: Al agregar mboxTrace como un parámetro de consulta en páginas con recomendaciones, se sustituye el diseño de Recommendations de la página por una ventana de detalles de mboxTrace que muestra información exhaustiva sobre sus recomendaciones, incluido lo siguiente:

* Recomendaciones devueltas frente a recomendaciones solicitadas
* La clave utilizada y si está generando recomendaciones
* Recomendaciones generadas a partir de criterios frente a recomendaciones de copia de seguridad
* Configuración de los criterios
* Exclusiones e inclusiones aplicadas
* Reglas de recopilación

No tiene que incluir  `=console`, `=json` ni `=window` en el parámetro de consulta. Cuando termine con los detalles de mboxTrace, agregue `=disable` y pulse **[!UICONTROL Intro]** para volver al modo de visualización normal.

mboxTrace no afecta a la apariencia ni al funcionamiento normal de su sitio. Los visitantes ven su diseño normal de Recommendations.

## mboxDebug {#mboxdebug}

Para usar mboxDebug, añada un parámetro de mboxDebug al final de la dirección URL. La tabla siguiente contiene información sobre los parámetros de URL relacionados con la respuesta [!DNL Target].

>[!NOTE]
>
>Algunos parámetros de mboxDebug están disponibles con o sin autenticación.

| Parámetros de URL | Finalidad |
|--- |--- |
| `mboxDebug=1` | Debugger<br>Si se añade este parámetro a cualquier dirección URL con peticiones de Target definidas, se abrirá una ventana emergente con detalles importantes sobre la depuración. Se detalla la información de cookies y los valores PCid y Session ID. Además, todas las direcciones URL de están visibles. Haga clic en una URL de petición de Target si desea mostrar la respuesta para dicha petición de [!DNL Target]. En [mbox_debug.pdf](/help/assets/mbox_debug.pdf) encontrará más información. |
| `mboxDebug=x-cookie` | Modifique la cookie |
| `mboxDisable=1` | Deshabilitar los mboxes de la página |
| `mboxDebug=x-profile` | Ver los perfiles definidos. |
| `mboxDebug=x-time` | Mostrar el tiempo de respuesta de cada petición de [!DNL Target] |
| `mboxOverride.browserIp=<Insert IP address>` | Pruebe el targeting geográfico<br>Pruebe el targeting geográfico con este parámetro de URL. Escriba una dirección IP como valor para este atributo. El targeting geográfico de Test&amp;Target evalúa esa dirección IP para compararla con cualquier targeting geográfico o conjunto de segmentación definido en una campaña. |

>[!NOTE]
>
>Asegúrese de que el fragmento de URL está después de los parámetros de cadena de consulta. Todo lo que haya después del primer `#` es un identificador de fragmento y hace que los parámetros de depuración no funcionen correctamente.

## Adobe Experience Cloud Debugger.  {#section_A2798ED3A431409690A4BE08A1BFCF17}

Adobe Experience Cloud Debugger le permite entender de forma rápida y sencilla su implementación de Target. Puede ver rápidamente la configuración de la biblioteca, examinar las solicitudes para asegurarse de que los parámetros personalizados se pasan correctamente, activar el registro de consola y desactivar todas las solicitudes de Target. Si se autentica en Experience Cloud, podrá utilizar la potente herramienta MboxTrace para inspeccionar su actividad, las cualificaciones de audiencia y el perfil del visitante.

Para obtener más información, consulte los vídeos de formación siguientes:

Para obtener información más detallada, consulte [Depurar at.js con Adobe Experience Cloud Debugger](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md).

## Los principales vendedores no aparecen en Recommendations.  {#section_3920C857270A406C80BE6CBAC8221ECD}

No se puede usar la llamada de *`SiteCatalyst: purchase`* para los datos del tráfico del algoritmo Compra. Utilice la llamada *`orderConfirmPage`* en su lugar.

## Comprobación de la prioridad de las actividades {#section_3D0DD07240F0465BAF655D0804100AED}

Las actividades basadas en formularios y creadas con [!DNL Target Standard/Premium] pueden chocar con las actividades creadas en la interfaz de usuario de [!DNL Target Classic] que tienen la misma prioridad y usan la misma petición de [!DNL Target].

## El código personalizado no produce los resultados esperados en Internet Explorer 8. {#section_FAC3651F19144D12A37A3E4F14C06945}

Target ya no admite IE8.

## La cookie de Target no se puede establecer {#section_77AFEB541C0B495EB67E29A4475DF960}

Si su sitio tiene un subdominio, como [!DNL us.domain.com], pero necesita establecer la cookie de Target en [!DNL domain.com] (en lugar de [!DNL us.domain.com]), tiene que anular el valor de configuración `cookieDomain`. Para obtener más información, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## El contenido de Target parpadea o no se muestra si un elemento también es parte de una personalización de Adobe Experience Manager. {#section_9E1DABEB75AB431FB9F09887E6DD07D3}

Si un elemento DOM es parte de una segmentación de personalización de Adobe Experience Manager (AEM) y una actividad de Target, el contenido de Target puede parpadear o no mostrarse.

Para solucionar esta situación, puede desactivar AEM personalización en las páginas en las que se está ejecutando Target.

## Las ofertas de redirección y remotas no se pueden entregar debido a una dirección URL no válida.  {#section_7D09043B687F43B39DAEDF17D00375AC}

Si la oferta de redirección o remota utiliza una dirección URL no válida, es posible que no se pueda entregar.

Para las ofertas de redirección, la respuesta [!DNL Target] puede contener `/* invalid redirect offer URL */`

O

Para ofertas remotas, la respuesta [!DNL Target] puede contener `/* invalid remote offer URL */`

Puede comprobar la respuesta [!DNL Target] en el explorador, o utilizando mboxTrace. Consulte [https://tools.ietf.org/html/std66](https://tools.ietf.org/html/std66) para obtener más información sobre las direcciones URL válidas.

## [!DNL Target]Las solicitudes de no se activan en mi sitio.

at.js no activa solicitudes de Target si utiliza un doctype no válido. at.js requiere el tipo de documento HTML 5.

## Asegúrese de que [!DNL Target] las actividades gestionan correctamente las direcciones URL con parámetros de cadena de consulta {#query-strings}

La variable [!UICONTROL URL de actividad] determina la página que clasifica a los visitantes para la actividad y presenta las experiencias de actividad a los usuarios. Cuando se le solicita durante la creación de la actividad, escribir la dirección URL completa no siempre garantiza que el contenido se envíe en esa página del sitio, especialmente con las direcciones URL que contienen parámetros de cadena de consulta.

De forma predeterminada, la variable [!UICONTROL Compositor de experiencias visuales] (VEC) abre la página que se especifica en su [Configuración del Compositor de experiencias visuales](/help/administrating-target/visual-experience-composer-set-up.md). También puede especificar una página diferente durante la creación de la actividad.

Para mostrar una página diferente después de que se abra el VEC, haga clic en el **[!UICONTROL Configuración del icono de engranaje]** > seleccione **[!UICONTROL Entrega de páginas]** > y luego especifique la dirección URL que desee en la [!UICONTROL URL de actividad] campo .

![Configuración de la interfaz de usuario de Entrega de páginas](assets/configure-page-delivery.png)

Pero, ¿qué sucede si la dirección URL contiene parámetros de cadena de consulta? ¿Funcionará y mostrará el contenido personalizado? En este escenario, independientemente de la audiencia de destino, puede incluir reglas de plantilla además de la dirección URL base para definir los parámetros de consulta.

Se pueden utilizar las siguientes opciones para incluir reglas de plantilla adicionales:

### Opción 1: Repita la dirección URL y manténgala en la regla de plantilla con la opción &quot;contiene&quot;.

Esta opción garantiza que esta dirección URL cumpla los requisitos de la actividad, pero tenga en cuenta que hay casos de esquina que pueden influir en los datos de informes con registros adicionales a las direcciones URL que contienen la dirección URL base.

En este caso, la dirección URL es `https://shopping.mycart.com?type=Summers%20Offers` y reglas de plantilla adicionales &quot;contiene&quot; la misma dirección URL, separada por un operador OR:

![Replicar URL en reglas de plantilla](assets/option1.png)

### Opción 2: Restringir la condición &quot;contiene&quot; de la dirección URL con solo la cadena de consulta.

El caso de esquina que se discute en la opción anterior se aplica en esta opción, pero aquí la configuración condicional está limitada únicamente a la cadena de consulta.

En este caso, la dirección URL es `https://shopping.mycart.com?type=Summers%20Offers` y reglas de plantilla adicionales &quot;contiene&quot; solamente la cadena de consulta, separada por un operador OR:

![La regla de plantilla solo contiene la cadena de consulta](assets/option2.png)

### Opción 3: En lugar de segmentar la dirección URL completa, aproveche una parte específica de la dirección URL.

En este caso, la dirección URL es `https://shopping.mycart.com?type=Summers%20Offers` y las reglas de plantilla adicionales especifican un [!UICONTROL Consulta] con [!UICONTROL type] > [!UICONTROL es (con distinción de mayúsculas y minúsculas)] > type=Summers%20Offers, separadas por un operador OR:

![Regla de plantilla que aprovecha una parte específica de la URL](assets/option3.png)

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Agregar la extensión  ![Distintivo de tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23114t2/)

### ![Insignia](/help/assets/tutorial.png) del tutorial de depuración básica de Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/23115t2/)

### Mbox Trace ![Distintivo del tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/23113t2/)
