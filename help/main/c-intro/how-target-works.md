---
keywords: SDK web de Adobe Experience Platform;sdk web de aep;sdk de aep;optimización de los motores de búsqueda;optimización del motor de búsqueda;seo;clústeres edge, clústeres centrales;at.js;mbox.js;
description: Descubra cómo funciona  [!DNL Adobe Target] , incluida información acerca de bibliotecas de JavaScript (SDK web de AEP at.js), centros de datos de Adobe, pruebas de SEO y bots.
title: ¿Cómo funciona  [!DNL Target] ?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 612089bcde266804efa6a54be89eff55329d4bfc
workflow-type: tm+mt
source-wordcount: '2562'
ht-degree: 98%

---

# Cómo funciona [!DNL Adobe Target]

Descubra cómo funciona [!DNL Adobe Target], incluida la información acerca de las bibliotecas de JavaScript ([!DNL Adobe Experience Platform Web SDK] y at.js). Este artículo también presenta los distintos tipos de actividades que puede crear mediante [!DNL Target]. También puede obtener información sobre la red de Edge de [!DNL Target], la optimización de los motores de búsqueda (SEO) y cómo [!DNL Target] detecta los bots.

## Bibliotecas de JavaScript de [!DNL Adobe Target] {#libraries}

[!DNL Target] se integra con los sitios web que utilizan el [!DNL Experience Platform Web SDK] o at.js:

* **[!DNL Adobe Experience Platform Web SDK]:** El [SDK web de Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} es una nueva biblioteca JavaScript del lado del cliente. El [!DNL Experience Platform Web SDK] permite a los clientes de [!DNL Adobe Experience Cloud] interactuar con los distintos servicios de [!DNL Experience Cloud] (incluido [!DNL Target]) a través de la red de Edge de [!DNL Experience Platform]. [!DNL Adobe] recomienda que todos los clientes nuevos de [!DNL Target] implementen el [!DNL Experience Platform Web SDK].
* **at.js:** La biblioteca at.js es una biblioteca de implementación para [!DNL Target]. La biblioteca at.js mejora los tiempos de carga de página en implementaciones web y proporciona mejores opciones de implementación en aplicaciones de una sola página. at.js se actualiza con frecuencia con nuevas funciones. [!DNL Adobe] recomienda que todos los clientes que utilicen at.js actualicen sus implementaciones a la [última versión de at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

>[!NOTE]
>
>La biblioteca mbox.js es la biblioteca de implementación heredada para [!DNL Target]. La biblioteca mbox.js deja de ser compatible a partir del 31 de marzo de 2021. Actualice al SDK web de Experience Platform (preferido) o a la última versión de at.js.

Haga referencia a [!DNL Experience Platform Web SDK] o at.js en todas las páginas del sitio. Por ejemplo, puede añadir una de estas bibliotecas al encabezado global. Alternativamente, considere la posibilidad de utilizar [etiquetas en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es) para implementar [!DNL Target].

Los siguientes recursos contienen información detallada para ayudarle a implementar el [!DNL Experience Platform Web SDK] o at.js:

* Extensión de [[!DNL Adobe Experience Platform Web SDK] ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=es)
* [Implementación [!DNL Target]  mediante  [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)

Cada vez que un visitante solicita una página que se ha optimizado para [!DNL Target], se envía una solicitud al sistema de segmentación. La solicitud ayuda a determinar qué contenido se mostrará a ese visitante. Este proceso se produce en tiempo real. Cada vez que se carga una página, el sistema realiza una solicitud del contenido y la completa. El contenido está regido por reglas de actividades y experiencias controladas por especialistas en marketing y se segmenta para cada visitante del sitio. El contenido se sirve para indicar que el visitante de cada sitio tiene más probabilidades de responder, interactuar con o, en última instancia, comprar. El contenido personalizado ayuda a maximizar las tasas de respuesta, las tasas de adquisición y los ingresos.

En [!DNL Target], cada elemento de la página forma parte de una única experiencia para la página completa. Cada experiencia puede incluir varios elementos en la página.

El contenido que se muestra a los visitantes depende del tipo de actividad que cree:

### [!UICONTROL Prueba A/B]

El contenido que se muestra en una prueba A/B básica se elige aleatoriamente entre las experiencias que asigna a la actividad. Puede asignar los porcentajes de asignación de tráfico para cada experiencia. Como resultado de esta división aleatoria del tráfico, puede consumir una gran cantidad de tráfico inicial antes de que se igualen los porcentajes. Por ejemplo, si crea una campaña con dos experiencias, la experiencia inicial se elige de forma aleatoria. Si hay poco tráfico, es posible que el porcentaje de visitantes se desvíe hacia una experiencia. A medida que aumenta el tráfico, los porcentajes se igualan.

Se pueden especificar los objetivos de porcentaje para cada experiencia. En este caso, se genera un número aleatorio que se utiliza para elegir la experiencia que se mostrará. Es posible que los porcentajes resultantes no coincidan exactamente con los objetivos especificados, pero con más tráfico resulta necesario dividir las experiencias para aproximarse a los objetivos.

1. Un cliente solicita una página al servidor y esta se muestra en el navegador.
1. Se establece una cookie de origen en el explorador del cliente para almacenar su comportamiento.
1. La página realiza una llamada al sistema de segmentación.
1. El contenido se muestra en función de las reglas establecidas para la actividad.

Para obtener más información, consulte [Creación de pruebas A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### [!UICONTROL Asignación automática]

[!UICONTROL Asignación automática] identifica un ganador entre dos o más experiencias. [!UICONTROL La asignación automática] reasigna automáticamente más tráfico a la experiencia ganadora, lo que ayuda a aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.

Para obtener más información, consulte [[!UICONTROL Asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### [!UICONTROL Segmentación automática] (AT)

[!UICONTROL La segmentación automática] utiliza el aprendizaje automático avanzado para seleccionar entre varias experiencias de alto nivel de rendimiento definidas por expertos en marketing. [!UICONTROL La segmentación automática] proporciona una experiencia más adaptada a cada visitante. La entrega de experiencias se basa en los perfiles de clientes individuales y en el comportamiento de los visitantes anteriores con perfiles similares. Utilice la [!UICONTROL segmentación automática] para personalizar el contenido y dirigir las conversiones.

Para obtener más información, consulte [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

### [!UICONTROL Automated Personalization] (AP)

[!UICONTROL Automated Personalization] (AP) combina ofertas o mensajes, y utiliza el aprendizaje automático avanzado para asignar diferentes variaciones de ofertas a cada visitante. La entrega de experiencias se basa en perfiles de clientes individuales para personalizar el contenido y dirigir el alza.

Para obtener más información, consulte [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### [!UICONTROL Segmentación de experiencias] (XT)

[!UICONTROL Segmentación de experiencias] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

[!UICONTROL La segmentación de experiencias], incluyendo el targeting geográfico, sirve para definir reglas que dirigen un contenido o experiencia determinados a una audiencia concreta. En una actividad se pueden definir reglas para entregar diversas variaciones de contenido a distintas audiencias. Cuando los visitantes ven el sitio, [!UICONTROL Segmentación de experiencias] (XT) los evalúa para determinar si cumplen con los criterios establecidos. En caso afirmativo, participan en la actividad y se les muestra la experiencia diseñada para clasificar audiencias. Puede crear experiencias para varias audiencias dentro de una misma actividad.

Consulte [direccionamiento de experiencias](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obtener más información.

### [!UICONTROL Prueba multivariable] (MVT)

[!UICONTROL Prueba multivariada] (MVT) compara combinaciones de ofertas entre elementos de una página para ver cuál ofrece el mejor resultado para una audiencia específica. MVT ayuda a identificar qué elemento tiene el mayor impacto en el éxito de la actividad.

Consulte [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obtener más información.

### [!UICONTROL Recommendations]

Las actividades de [!UICONTROL Recommendations] muestran automáticamente productos o contenido que podría interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.

Para obtener más información, consulte [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

## La red de Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

“Edge” es una arquitectura de servidores distribuidos geográficamente que garantiza tiempos de respuesta óptimos para los visitantes que solicitan contenido desde cualquier lugar del mundo.

Para mejorar los tiempos de respuesta, Edge [!DNL Target] almacena solo la lógica de la actividad, los perfiles en caché y la información de las ofertas.

Las bases de datos de actividades y contenido, los datos de [!DNL Analytics], las API y las interfaces de usuario de los expertos en marketing se hospedan en los clústeres de datos centrales de Adobe. Las actualizaciones se envían a los Edges de [!DNL Target]. Los clústeres centrales y de Edge se sincronizan automáticamente para actualizar de forma continua los datos de actividades en caché. Todo el modelado 1:1 también se almacena en cada Edge, de modo que las solicitudes más complejas también pueden ser procesadas en el Edge.

Cada clúster de Edge dispone de toda la información necesaria para responder a la solicitud de contenido del visitante y realizar un seguimiento de los datos de análisis de dicha solicitud. Las solicitudes de los visitantes se dirigen al clúster de Edge más próximo.

Para obtener más información, consulte el documento técnico [Información general sobre la seguridad de Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

La solución de [!DNL Target] está alojada en centros de datos de todo el mundo que Adobe tiene alquilados o en propiedad.

Las ubicaciones del clúster central contienen un centro de recopilación de datos y uno de procesamiento de datos. Las ubicaciones del clúster de Edge contienen solo un centro de recopilación de datos. Cada grupo de informes está asignado a un centro de procesamiento de datos específico.

Los datos de actividad del sitio del cliente los recopila el más cercano de siete clústeres de Edge. Estos datos se dirigen al destino de clúster central predeterminado por el cliente (a una de las tres ubicaciones: Oregón, Dublín, Singapur) para su procesamiento. Los datos del perfil del visitante se almacenan en el clúster de Edge más cercano al visitante del sitio. Entre las ubicaciones de clústeres de Edge se encuentran las del clúster central y Virginia, Bombay, Sídney y Tokio.

En lugar de responder a todas las solicitudes de direccionamiento desde una sola ubicación, el clúster de Edge más cercano al visitante procesa las solicitudes. Este proceso ayuda a mitigar el impacto del tiempo de viaje en red/Internet.

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
>[!DNL Adobe Target] actualmente no tiene ningún clúster de Edge en China y el rendimiento del visitante sigue siendo limitado para los clientes de [!DNL Target] de China. Debido al firewall y a la falta de clústeres de Edge dentro del país, las experiencias de los sitios con [!DNL Target] implementado pueden verse afectadas. Las experiencias pueden procesarse lentamente y las cargas de página pueden verse afectadas. Además, los especialistas en marketing pueden experimentar latencia al utilizar la IU de creación de [!DNL Target].

Si lo desea, puede incluir en las listas de permitidos los clústeres de Edge de [!DNL Target]. Para obtener más información, consulte cómo [incluir en la lista de permitidos los nodos de Edge de Target](https://developer.adobe.com/target/before-implement/privacy/allowlist-edges/){target=_blank}.

## Experiencia del usuario protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] garantiza que la disponibilidad y el rendimiento de la infraestructura de direccionamiento sea lo más segura posible. Sin embargo, el desglose de las comunicaciones entre el explorador del visitante y los servidores de [!DNL Adobe] puede imposibilitar la entrega de contenido.

Para evitar interrupciones del servicio y problemas de conectividad, todas las ubicaciones están configuradas para incluir contenido predeterminado (definido por el cliente). Este contenido predeterminado se muestra si el explorador del usuario no se puede conectar a [!DNL Target].

No se realiza ningún cambio en la página si el explorador del usuario no se puede conectar en un plazo de tiempo de espera definido (15 segundos de manera predeterminada). Si se alcanza este umbral de tiempo de espera, se muestra el contenido de ubicación predeterminado.

[!DNL Adobe] protege la experiencia del usuario al optimizar y garantizar el rendimiento.

* [!DNL Adobe] garantiza pruebas de referencia de rendimiento que se basan en estándares del sector (avaladas por el contrato de nivel de servicio de Adobe).
* La red de Edge garantiza que la entrega de datos se realice a tiempo.
* [!UICONTROL Adobe] utiliza un enfoque de varios niveles para garantizar sus aplicaciones y proporcionar la máxima disponibilidad y fiabilidad a sus clientes.
* Los servicios de asesoramiento de [!DNL Target] ofrecen asistencia para la implementación y soporte continuado para los productos.

## Pruebas sencillas para la optimización del motor de búsqueda (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] se adhiere a las directrices de motores de búsqueda en las pruebas.

Google promueve las pruebas de usuario. Google afirma en su documentación que las [!UICONTROL Pruebas multivariadas] y A/B no perjudican las clasificaciones de los motores de búsqueda orgánica si se siguen determinadas directrices.

Para obtener más información, consulte los siguientes recursos de Google:

* [Pruebas en sitios web y Búsqueda de Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos y encubrimiento](https://support.google.com/analytics/answer/2576845?hl=es&amp;ref_topic=1745207)

Las directrices se publicaron en una entrada del [blog Google Webmaster Central](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Aunque la publicación es de 2012, sigue siendo la información más reciente de Google sobre este tema y las directrices continúan vigentes.

* **Sin encubrimiento**: El encubrimiento muestra un conjunto de contenido a los usuarios y otro conjunto diferente a los bots de los motores de búsqueda. El encubrimiento se lleva a cabo identificando bots de forma específica y alimentándolos a propósito con contenido diferente.

   [!DNL Target], como plataforma, se ha configurado para que trate a los bots de los motores de búsqueda como a cualquier usuario. Como resultado, los bots se pueden incluir en las actividades si se seleccionan aleatoriamente y “ven” las variaciones de la prueba.

* **Usar rel=&quot;canonical&quot;**: algunas veces, hay que configurar una prueba A/B con distintas direcciones URL para las variaciones. En estos casos, todas las variaciones deben contener una etiqueta de `rel="canonical"` que haga referencia a la URL (de control) original. Por ejemplo, supongamos que [!DNL Adobe] está probando su página de inicio utilizando distintas direcciones URL para cada variación. La siguiente etiqueta canónica para la página principal iría en la etiqueta `<head>` para cada una de las variaciones:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Usar redirecciones 302 (temporales)**: en los casos en que se usan URL distintas para las páginas de variación en una prueba, Google recomienda usar una redirección 302 para redirigir el tráfico hacia las variaciones de prueba. La redirección 302 indica a los motores de búsqueda que el redireccionamiento es temporal y está activo solo mientras se esté ejecutando la prueba.

   Una redirección 302 se efectúa en el lado del servidor y [!DNL Target], así como la mayoría de los proveedores de optimización, utiliza capacidades del lado del cliente. Por lo tanto, en esta área, [!DNL Target] no cumple del todo las recomendaciones de Google. No obstante, esta práctica solo afecta a una pequeña parte de las pruebas. El método habitual de realizar pruebas a través de [!DNL Target] exige cambiar el contenido en una sola URL, de modo que no es necesario ninguna redirección. Hay casos en que los clientes necesitan usar varias URL para representar las variaciones de la prueba. En estas instancias, [!DNL Target] utiliza el comando JavaScript `window.location`. Este comando dirige a los usuarios a probar las variaciones, lo que no significa explícitamente que la redirección sea de tipo 301 o 302.

   [!DNL Adobe] sigue buscando soluciones viables para cumplir completamente con las directrices de los motores de búsqueda. Para los clientes que deben utilizar direcciones URL independientes para realizar pruebas, [!DNL Adobe] está seguro de que la correcta implementación de las etiquetas canónicas mitigará el riesgo asociado con este método.

* **Realizar experimentos solo cuando sea necesario**: [!DNL Adobe] cree que “cuando sea necesario” significa cuando haya que alcanzar la relevancia estadística. [!DNL Target] proporciona prácticas recomendadas y la [!DNL Adobe Target] [Calculadora de tamaño de muestra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) para determinar cuándo la prueba ha alcanzado este punto. [!DNL Adobe] le recomienda que incorpore la implementación incrustada en el código de las pruebas ganadoras en el flujo de trabajo de pruebas y le asigne los recursos apropiados.

   No se recomienda usar la plataforma [!DNL Target] para “publicar” pruebas ganadoras como solución permanente. Si la prueba ganadora se publica para el 100 % de los usuarios el 100 % de las veces, este método se puede utilizar mientras se completa el proceso de incrustar en el código la prueba ganadora.

   También es importante tener en cuenta lo que la prueba ha cambiado. Actualizar el color de los botones u otros artículos pequeños que no sean de texto en la página no influirá en las clasificaciones orgánicas. No obstante, los cambios realizados en el texto se deben incrustar en el código.

   Tampoco hay que olvidar la accesibilidad de la página que se está probando. Si la página no es accesible para los motores de búsqueda y no se diseñó para clasificarse en la búsqueda orgánica en primer lugar, no se aplica ninguna de las consideraciones anteriores. Un ejemplo es una página de aterrizaje dedicada para una campaña de correo electrónico.

Desde Google afirman que estas directrices “harán que las pruebas tengan un impacto mínimo o nulo en los resultados de búsqueda del sitio”.

Además de estas directrices, Google también proporciona otra pauta en la documentación de la herramienta Experimentos con contenido:

* “Las páginas de variación deben mantener la esencia del contenido en las páginas originales. Estas variaciones no deben cambiar la percepción general ni el significado de esta que el usuario tiene del contenido original”.

Google pone el ejemplo de que “si la página original de un sitio se carga con palabas clave que no están relacionadas con las combinaciones que se muestran a los usuarios, nos reservamos el derecho a eliminar el sitio de nuestro índice”.

[!UICONTROL Adobe] considera que sería difícil cambiar de forma involuntaria el significado del contenido original dentro de las variaciones de prueba. Sin embargo, [!UICONTROL Adobe] recomienda tener en cuenta las temáticas de palabras clave de una página y mantenerlas. Al cambiar el contenido de una página, especialmente añadiendo o eliminando palabras clave importantes, puede variar la clasificación de la URL en la búsqueda orgánica. [!DNL Adobe] recomienda que incluya a su socio de optimización de los motores de búsqueda en el protocolo de prueba.

## Bots {#bots}

Adobe [!DNL Target] utiliza la métrica [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) “isRobot” para detectar bots conocidos basados en la cadena del agente de usuario pasada en el encabezado de la solicitud.

>[!NOTE]
>
> Para las solicitudes [!DNL Server-Side], el valor pasado en el nodo [“Contexto” de la solicitud](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tiene prioridad sobre la cadena del agente de usuario para la detección de bots.

El tráfico que se identifica como generado por un bot sigue siendo contenido servido. Los bots se tratan como un usuario normal para garantizar que [!DNL Target] esté en armonía con las directrices de optimización de los motores de búsqueda. El uso del tráfico de bots puede afectar a las pruebas A/B o los algoritmos de personalización, si se tratan como usuarios normales. Por lo tanto, si se detecta un bot conocido en la actividad de [!DNL Target], el tráfico se trata de manera ligeramente diferente. La eliminación del tráfico de bots proporciona una medición más precisa sobre la actividad del usuario.

En concreto, para el tráfico de bots conocido, [!DNL Target] no:

* Crea ni recupera un perfil de visitante
* Registra atributos de perfil ni ejecuta scripts de perfil
* Busca segmentos de [!DNL Adobe Audience Manager] (AAM) (si corresponde)
* Utiliza el tráfico de bots para modelar y ofrecer contenido personalizado para actividades de [!UICONTROL Recommendations], [!UICONTROL Segmentación automática], [!UICONTROL Automated Personalization] o [!UICONTROL Asignación automática]
* Registra una visita de actividad para la creación informes
* Registra datos que se enviarán a la plataforma de [!DNL Adobe Experience Cloud]

Para el tráfico de bots conocido al usar [!UICONTROL Analytics for Target] (A4T), [!DNL Target] no ocurre lo siguiente:

* Envía eventos a [!DNL Analytics]

Para el tráfico de bots conocido al utilizar el registro del lado del cliente, [!DNL Target] no devuelve lo siguiente:

* carga útil tnta
