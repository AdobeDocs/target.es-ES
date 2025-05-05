---
keywords: SDK web de Adobe Experience Platform;sdk web de aep;sdk de aep;optimización de los motores de búsqueda;optimización del motor de búsqueda;seo;clústeres edge, clústeres centrales;at.js;mbox.js;
description: Descubra cómo funciona [!DNL Adobe Target] e incluya información sobre bibliotecas de JavaScript (AEP Web SDK at.js), estrategias de uso de llamadas al servidor, uso, centros de datos de Adobe, pruebas de optimización de los motores de búsqueda y bots.
title: ¿Cómo funciona  [!DNL Target] ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: c5cca9b4b95289626ade1654bb508ee9f0bf35f3
workflow-type: tm+mt
source-wordcount: '2215'
ht-degree: 24%

---

# Cómo funciona [!DNL Adobe Target]

Descubra cómo funciona [!DNL Adobe Target], incluidos los detalles de las bibliotecas de JavaScript ([!DNL Adobe Experience Platform Web SDK] y at.js). Este artículo también describe los distintos tipos de actividades que puede crear, las [!DNL Target] estrategias de recuento de uso, la [!DNL Target] detección de Edge Network, SEO y bots.

Los puntos clave incluyen:

* **Bibliotecas JavaScript**: Obtenga información acerca de las [!DNL Target] bibliotecas JavaScript: [!DNL Adobe Experience Platform Web SDK] y at.js.
* **Estrategias de uso de llamadas al servidor**: Descubra cómo [!DNL Target] cuenta varias llamadas al servidor, incluidos los extremos, el mbox único, el mbox por lotes, las llamadas de ejecución, recuperación previa y notificación.
* **Edge Network**: Descubra cómo [!DNL Target] interactúa con [!DNL Adobe Experience Platform Edge Network].
* **Experiencia del usuario protegida**: Descubra cómo [!DNL Adobe] garantiza la disponibilidad y el rendimiento de su infraestructura de segmentación.
* **Directrices de SEO**: Siga las prácticas recomendadas para alinear las actividades de [!DNL Target] con las directrices de SEO.
* **Tráfico de bots**: Descubra cómo Target administra el tráfico de bots para evitar distorsionar las pruebas y los algoritmos de personalización.

## Bibliotecas de JavaScript de [!DNL Adobe Target] {#libraries}

Target se integra con los sitios web que utilizan [!DNL Experience Platform Web SDK] o at.js:

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}**: Esta biblioteca JavaScript del lado del cliente permite que [!DNL Adobe Experience Cloud] clientes interactúen con varios servicios a través de [!DNL Experience Platform Edge Network]. [!DNL Adobe] recomienda que los nuevos clientes de [!DNL Target] implementen [!DNL Experience Platform Web SDK].
* **[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=es){target=_blank}**: esta biblioteca de implementación para [!DNL Target] mejora los tiempos de carga de página en implementaciones web y ofrece mejores opciones en aplicaciones de una sola página. Actualizado con frecuencia con nuevas funcionalidades, [!DNL Adobe] recomienda que todos los usuarios de [at.js actualicen a la última versión](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

>[!NOTE]
>
>La biblioteca mbox.js es una implementación heredada para [!DNL Target] y ya no es compatible a partir del 31 de marzo de 2021. Actualice a [!UICONTROL Experience Platform Web SDK] (preferido) o a la última versión de at.js.

Haga referencia a [!UICONTROL Experience Platform Web SDK] o at.js en todas las páginas del sitio. Por ejemplo, añada una de estas bibliotecas al encabezado global. También puede usar [tags en Adobe Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/tags/home){target=_blank} para implementar [!DNL Target].

Los siguientes recursos contienen información detallada para ayudarle a implementar el [!DNL Experience Platform Web SDK] o at.js:

* Extensión de [[!DNL Adobe Experience Platform Web SDK] ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=es){target=_blank}
* [Implementación [!DNL Target]  mediante  [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/es/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

Cada vez que un visitante solicita una página optimizada para [!DNL Target], se envía una solicitud en tiempo real al sistema de segmentación para determinar el contenido que se va a servir. Esta solicitud se realiza y se completa cada vez que se carga una página, regida por actividades y experiencias controladas por expertos en marketing. El contenido está dirigido a visitantes de sitio individuales, lo que maximiza las tasas de respuesta, las tasas de adquisición y los ingresos. El contenido personalizado ayuda a garantizar que los visitantes respondan, interactúen o realicen compras.

En [!DNL Target], cada elemento de la página es parte de una sola experiencia, que puede incluir varios elementos.

El contenido mostrado depende del tipo de actividad que cree:

### [!UICONTROL A/B Test]

En una prueba A/B básica, el contenido se elige aleatoriamente entre las experiencias asignadas. Puede establecer porcentajes de asignación de tráfico para cada experiencia. Inicialmente, el tráfico puede distribuirse de forma desigual debido a la división aleatoria, pero se iguala a medida que aumenta el tráfico. Por ejemplo, con dos experiencias, la experiencia de inicio se elige de forma aleatoria. Un tráfico bajo puede inclinar los porcentajes de visitantes hacia una experiencia, pero esta situación se equilibra con un mayor tráfico.

Especifique objetivos de porcentaje para cada experiencia. Se genera un número aleatorio para seleccionar la experiencia que se va a mostrar. Aunque los porcentajes resultantes pueden no coincidir exactamente con los objetivos, un tráfico mayor conduce a una división más cercana a los objetivos.

1. Un cliente solicita una página al servidor, que se muestra en el explorador.
1. Se establece una cookie de origen en el explorador del cliente para almacenar su comportamiento.
1. La página realiza una llamada al sistema de segmentación.
1. El contenido se muestra en función de las reglas de actividad.

Para obtener más información, consulte [Creación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifica la experiencia ganadora entre dos o más opciones. A continuación, reasigna automáticamente más tráfico al ganador, lo que aumenta las conversiones a medida que la prueba sigue ejecutándose y aprendiendo.

Consulte [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obtener más información.

### [!UICONTROL Auto-Target] (AT)

[!UICONTROL Auto-Target] aprovecha el aprendizaje automático avanzado para elegir entre varias experiencias de alto rendimiento definidas por expertos en marketing. [!UICONTROL Auto-Target] ofrece a cada visitante la experiencia más adaptada en función de los perfiles de clientes individuales y del comportamiento de los visitantes anteriores con perfiles similares. Use [!UICONTROL Auto-Target] para personalizar contenido y dirigir conversiones.

Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) combina ofertas o mensajes y utiliza aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante. AP personaliza el contenido en función de perfiles de clientes individuales para dirigir el alza.

Para obtener más información, consulte [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Experience Targeting] (XT)

[!UICONTROL Experience Targeting] (XT) ofrece contenido a audiencias específicas en función de reglas y criterios definidos por expertos en marketing. Incluido el targeting geográfico, XT es útil para definir reglas que dirigen experiencias o contenido específicos a audiencias específicas. En una actividad se pueden establecer varias reglas para entregar distintas variaciones de contenido a distintas audiencias. Cuando los visitantes ven el sitio, XT los evalúa para determinar si cumplen con los criterios. Si cumplen los requisitos, entran en la actividad y ven la experiencia diseñada para ellos. Puede crear experiencias para varias audiencias dentro de una misma actividad.

Consulte [direccionamiento de experiencias](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obtener más información.

### [!UICONTROL Multivariate Test] (MVT)

[!UICONTROL Multivariate Testing] (MVT) compara combinaciones de ofertas en elementos de página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica. MVT ayuda a identificar qué elemento tiene el mayor impacto en el éxito de la actividad.

Consulte [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obtener más información.

### [!UICONTROL Recommendations]

Las actividades de [!UICONTROL Recommendations] muestran automáticamente productos o contenido que podría interesar a los clientes en función de su actividad anterior u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no descubran de otra manera.

Para obtener más información, consulte [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## La red de Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Una &quot;Edge&quot; es una arquitectura de servidores distribuidos geográficamente que garantiza tiempos de respuesta óptimos para visitantes que solicitan contenido desde cualquier ubicación.

Para mejorar los tiempos de respuesta, Edge [!DNL Target] almacena solo la lógica de la actividad, los perfiles en caché y la información de las ofertas.

Las bases de datos de actividades y contenido, los datos de [!DNL Analytics], las API y las interfaces de usuario de los especialistas en marketing se hospedan en [!DNL Adobe] clústeres centrales. Las actualizaciones se envían a [!DNL Target] Edges, que se sincronizan automáticamente con los clústeres centrales para actualizar de forma continua los datos de actividades en caché. Todo el modelado 1:1 también se almacena en cada Edge, lo que permite que las solicitudes complejas se procesen localmente.

Cada clúster de Edge contiene toda la información necesaria para responder a las solicitudes de contenido de los visitantes y realizar un seguimiento de los datos de análisis. Las solicitudes de los visitantes se dirigen al clúster de Edge más próximo.

Para obtener más información, consulte el documento técnico [Información general sobre la seguridad de Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

[!DNL Target] está alojado en centros de datos de todo el mundo que Adobe tiene alquilados o en propiedad de Adobe.

Las ubicaciones del clúster central albergan centros de recopilación y procesamiento de datos. Las ubicaciones del clúster de Edge solo contienen centros de recopilación de datos. Cada grupo de informes está asignado a un centro de procesamiento de datos específico.

Los datos de actividad del sitio del cliente los recopila el más cercano de siete clústeres de Edge. Estos datos se dirigen a un destino de clúster central predeterminado (Oregón, Dublín o Singapur) para su procesamiento. Los datos del perfil del visitante se almacenan en el clúster de Edge más cercano al visitante del sitio. Entre las ubicaciones del clúster de Edge se incluyen las del clúster central, así como Virginia, Bombay, Sídney y Tokio.

En lugar de procesar todas las solicitudes de segmentación desde una sola ubicación, las solicitudes se gestionan mediante el clúster de Edge más cercano al visitante. Este enfoque mitiga el impacto del tiempo de viaje en red y por Internet.

![Mapa que muestra los diferentes tipos de servidores de Target](/help/main/c-intro/assets/target-servers.png)

[!DNL Target] Los clústeres centrales, alojados en Amazon Web Services (AWS), incluyen:

* Oregón, EE. UU.
* Dublín, Irlanda
* República de Singapur

[!DNL Target] Los clústeres de Edge, alojados en AWS, incluyen:

* Bombay, India
* Tokio, Japón
* Virginia, EE. UU.
* Oregón, EE. UU.
* Sídney, Australia
* Dublín, Irlanda
* República de Singapur

El servicio de [!DNL Target Recommendations] está alojado en un centro de datos de [!DNL Adobe] en Oregón.

>[!IMPORTANT]
>
>[!DNL Target] carece actualmente de un clúster de Edge en China, lo que limita el rendimiento del visitante para [!DNL Target] clientes en la región. El cortafuegos y la ausencia de clústeres de Edge pueden afectar a las experiencias del sitio, lo que provoca una lentitud de procesamiento y tiempos de carga de las páginas. Además, los especialistas en marketing pueden experimentar latencia al utilizar la interfaz de usuario de creación de [!DNL Target].

Si lo desea, puede incluir en las listas de permitidos los clústeres de Edge de [!DNL Target]. Para obtener más información, consulte cómo [incluir en la lista de permitidos los nodos de Edge de Target](https://experienceleague.adobe.com/es/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}.

## Experiencia del usuario protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] garantiza que la disponibilidad y el rendimiento de su infraestructura de segmentación sea lo más confiable posible. Sin embargo, los desgloses de comunicación entre el explorador de un visitante y los servidores de [!DNL Adobe] pueden interrumpir la entrega de contenido.

Para evitar interrupciones del servicio y problemas de conectividad, todas las ubicaciones están configuradas para incluir contenido predeterminado (definido por el cliente). Este contenido predeterminado se muestra si el explorador del visitante no se puede conectar a [!DNL Target].

No se realiza ningún cambio en la página si el explorador del visitante no se puede conectar en un plazo de tiempo de espera definido (predeterminado: 15 segundos). Si se alcanza este umbral de tiempo de espera, se muestra el contenido de ubicación predeterminado.

[!DNL Adobe] protege la experiencia del usuario al optimizar y garantizar el rendimiento.

* [!DNL Adobe] garantiza puntos de referencia de rendimiento basados en estándares del sector, garantizados por [!UICONTROL Adobe Service Level Agreement].
* La red de Edge garantiza que la entrega de datos se realice a tiempo.
* [!UICONTROL Adobe] emplea un enfoque de varios niveles para proteger sus aplicaciones, proporcionando el nivel más alto de disponibilidad y confiabilidad para sus clientes.
* Los servicios de asesoramiento de [!DNL Target] ofrecen asistencia para la implementación y soporte continuado para los productos.

## Pruebas sencillas para la optimización del motor de búsqueda (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] se adhiere a las directrices de motores de búsqueda en las pruebas. [!DNL Google] promueve las pruebas de usuario y afirma que A/B y [!UICONTROL Multivariate Testing] no perjudican las clasificaciones de los motores de búsqueda orgánica si se siguen determinadas directrices.

[!DNL Adobe Target] se adhiere a las directrices de motores de búsqueda en las pruebas.

Para obtener más información, consulte los siguientes recursos de Google:

* [Pruebas en sitios web y Búsqueda de Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos y encubrimiento](https://support.google.com/analytics/answer/12979939?hl)


Las directrices se publicaron en una entrada del [blog Google Webmaster Central](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Aunque la publicación data de 2012, sigue siendo la declaración más reciente de [!DNL Google] sobre el tema y las directrices siguen siendo pertinentes.

* **Sin encubrimiento**: El encubrimiento implica mostrar un conjunto de contenido a los usuarios y otro conjunto diferente a los bots de los motores de búsqueda, para lo cual se identifican específicamente los bots y se les proporciona contenido diferente.

  [!DNL Target] está configurado para tratar los bots de los motores de búsqueda como a cualquier usuario. Por lo tanto, los bots se pueden incluir en las actividades si se seleccionan aleatoriamente y &quot;ven&quot; las variaciones de la prueba.

* **Usar rel=&quot;canonical&quot;**: algunas veces, una prueba A/B requiere direcciones URL diferentes para las variaciones. En estos casos, todas las variaciones deben incluir una etiqueta rel=&quot;canonical&quot; que haga referencia a la URL (de control) original. Por ejemplo, si [!DNL Adobe] está probando su página principal con distintas direcciones URL para cada variación, la siguiente etiqueta canónica para la página principal debe colocarse en la etiqueta `<head>` de cada variación:

  `<link rel="canonical" href="https://www.adobe.com" />`

* **Usar redirecciones 302 (temporales)**: Cuando se usan direcciones URL distintas para las páginas de variación en una prueba, [!DNL Google] recomienda usar una redirección 302 para redirigir el tráfico a las variaciones de prueba. La redirección 302 informa a los motores de búsqueda de que el redireccionamiento es temporal y está activo solo mientras se ejecuta la prueba.

  Una redirección 302 se realiza en el lado del servidor, mientras que [!DNL Target] y la mayoría de los proveedores de optimización utilizan capacidades del lado del cliente. Por lo tanto, [!DNL Target] no es totalmente compatible con las recomendaciones de [!DNL Google] para redirecciones. Sin embargo, esto solo afecta a una pequeña parte de las pruebas. El método estándar para ejecutar pruebas a través de [!DNL Target] consiste en cambiar el contenido dentro de una sola dirección URL, lo que elimina la necesidad de redirecciones. En los casos en que se requieren varias direcciones URL para las variaciones de prueba, [!DNL Target] usa el comando JavaScript `window.location`, que no especifica si la redirección es de tipo 301 o 302.

  [!DNL Adobe] está buscando activamente soluciones para cumplir completamente con las directrices de los motores de búsqueda. Para los clientes que necesitan direcciones URL independientes para realizar pruebas, [!DNL Adobe] cree que la implementación correcta de las etiquetas canónicas mitiga los riesgos asociados.

* **Ejecutar experimentos solo cuando sea necesario**: [!DNL Adobe] define &quot;cuando sea necesario&quot; como el tiempo necesario para alcanzar la relevancia estadística. [!DNL Target] ofrece prácticas recomendadas y [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) para determinar cuándo la prueba ha alcanzado este punto. [!DNL Adobe] recomienda incorporar la implementación incrustada en el código de las pruebas ganadoras en el flujo de trabajo de pruebas y asignar los recursos apropiados.

  No se recomienda usar [!DNL Target] para &quot;publicar&quot; pruebas ganadoras como solución permanente. Si la prueba ganadora se publica para el 100 % de los usuarios todo el tiempo, este método se puede utilizar temporalmente mientras se codifica de forma rígida la prueba ganadora.

  Considere lo que la prueba ha cambiado. Las actualizaciones menores, como los colores de los botones, no afectan a las clasificaciones orgánicas. Sin embargo, los cambios de texto deben estar codificados.

  Además, considere la accesibilidad de la página que está probando. Si la página no es accesible para los motores de búsqueda y nunca tuvo la intención de clasificarse en la búsqueda orgánica, estas consideraciones no se aplican. Un ejemplo es una página de aterrizaje dedicada para una campaña de correo electrónico.

Desde Google afirman que estas directrices “harán que las pruebas tengan un impacto mínimo o nulo en los resultados de búsqueda del sitio”.

Además de estas directrices, Google también proporciona otra pauta en la documentación de la herramienta Experimentos con contenido:

* “Las páginas de variación deben mantener la esencia del contenido en las páginas originales. Estas variaciones no deben cambiar la percepción general ni el significado de esta que el usuario tiene del contenido original”.

Google pone el ejemplo de que “si la página original de un sitio se carga con palabas clave que no están relacionadas con las combinaciones que se muestran a los usuarios, nos reservamos el derecho a eliminar el sitio de nuestro índice”.

[!UICONTROL Adobe] considera que sería difícil cambiar de forma involuntaria el significado del contenido original dentro de las variaciones de prueba. Sin embargo, [!UICONTROL Adobe] recomienda tener en cuenta las temáticas de palabras clave de una página y mantenerlas. Al cambiar el contenido de una página, especialmente añadiendo o eliminando palabras clave importantes, puede variar la clasificación de la URL en la búsqueda orgánica. [!DNL Adobe] recomienda que incluya a su socio de optimización de los motores de búsqueda en el protocolo de prueba.

## Bots {#bots}

[!DNL Target] usa la métrica [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) &quot;isRobot&quot; para detectar bots conocidos basados en la cadena del agente de usuario pasada en el encabezado de la solicitud.

>[!NOTE]
>
> Para las solicitudes [!DNL Server-Side], el valor pasado en el nodo [“Contexto” de la solicitud](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tiene prioridad sobre la cadena del agente de usuario para la detección de bots.

El tráfico identificado como generado por el bot sigue siendo contenido servido. Los bots se tratan como usuarios normales para garantizar que [!DNL Target] se ajuste a las directrices de optimización de los motores de búsqueda. Sin embargo, el tráfico de bots puede distorsionar las pruebas A/B o los algoritmos de personalización, si se tratan como usuarios normales. Por lo tanto, el tráfico de bots conocido en su actividad [!DNL Target] se trata de manera diferente. La eliminación del tráfico de bots proporciona una medida más precisa de la actividad del usuario.

Para el tráfico de bots conocido, [!DNL Target] no:

* Crea ni recupera un perfil del visitante
* Registrar atributos de perfil o ejecutar scripts de perfil
* Busca segmentos de [!DNL Adobe Audience Manager] (AAM) (si corresponde)
* Utiliza el tráfico de bots para modelar o ofrecer contenido personalizado para las actividades [!UICONTROL Recommendations], [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] o [!UICONTROL Auto-Allocate]
* Registra una visita de actividad para la creación informes
* Registra datos que se enviarán a la plataforma de [!DNL Adobe Experience Cloud]

Para el tráfico de bots conocido, al usar [!UICONTROL Analytics for Target] (A4T), [!DNL Target] no:

* Envía eventos a [!DNL Analytics]

Para el tráfico de bots conocido al usar el registro de `client_side`, [!DNL Target] no devuelve:

* `tnta payload`
