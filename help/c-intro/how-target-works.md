---
keywords: SDK web de Adobe Experience Platform;aep web sdk;aep sdk;optimización del motor de búsqueda;seo;clústeres Edge, clústeres centrales;at.js;mbox.js;
description: Obtenga información sobre el funcionamiento de Adobe Target, incluida información sobre las bibliotecas de JavaScript de Destinatario (at.js y AEP Web SDK), los centros de datos de Adobe y las pruebas de SEO.
title: ¿Cómo Funciona El Destinatario?
feature: Información general
translation-type: tm+mt
source-git-commit: 1e5448ecdfe57c2b6cc492180c7225f3740b7147
workflow-type: tm+mt
source-wordcount: '2567'
ht-degree: 32%

---


# Cómo funciona Adobe Target

Descubra cómo [!DNL Adobe Target] funciona, incluida información sobre las bibliotecas [!DNL Adobe Experience Platform Web SDK] y JavaScript (at.js y mbox.js). Este artículo también presenta los distintos tipos de actividades que puede crear mediante [!DNL Target]. También puede obtener más información sobre la [!DNL Target] red Edge, la Optimización de motores de búsqueda (SEO) y cómo [!DNL Target] detecta los bots.

## SDK web de la plataforma destinatario y bibliotecas de JavaScript {#libraries}

[!DNL Target] se integra con sitios web que utilizan las bibliotecas  [!DNL AEP Web SDK] o JavaScript:

* **SDK web de Adobe Experience Platform:** El  [SDK web de ](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) AEP es una nueva biblioteca JavaScript del lado del cliente. El SDK web de AEP permite a los clientes de [!DNL Adobe Experience Cloud] interactuar con los distintos servicios de [!DNL Experience Cloud] (incluyendo [!DNL Target]) a través de la [!DNL AEP] red perimetral. Adobe recomienda que todos los clientes nuevos [!DNL Target] implementen el [!DNL AEP Web SDK].
* **at.js:** La biblioteca  [at.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) es una biblioteca de implementación para  [!DNL Target]. La biblioteca at.js mejora los tiempos de carga de página en implementaciones web y proporciona mejores opciones de implementación en aplicaciones de una sola página. at.js se actualiza con frecuencia con nuevas funciones. Adobe recomienda que todos los clientes que utilicen at.js actualicen sus implementaciones a la [última versión de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:**[](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) la biblioteca mbox.js es la biblioteca de implementación heredada para [!DNL Target]. La biblioteca mbox.js es compatible hasta el 31 de marzo de 2021; sin embargo, no habrá actualizaciones de funciones.

>[!IMPORTANT]
>
>Todos los clientes deben migrar a [!DNL AEP Web SDK] o a la última versión de at.js. Para obtener más información, consulte [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) o [Migrar a at.js desde mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Haga referencia a [!DNL AEP Web SDK] o at.js en todas las páginas del sitio. Por ejemplo, puede agregar una de estas bibliotecas al encabezado global. Otra opción es utilizar [Platform launch de Adobe](https://experienceleague.adobe.com/docs/launch/using/overview.html) para implementar [!DNL Target].

Los siguientes recursos contienen información detallada para ayudarle a implementar el SDK web de AEP o at.js:

* [Extensión de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implementar Target utilizando Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Cada vez que un visitante solicita una página que se ha optimizado para [!DNL Target], se envía una solicitud al sistema de segmentación. La solicitud ayuda a determinar qué contenido se debe proporcionar a ese visitante. Este proceso se realiza en tiempo real. Cada vez que se carga una página, el sistema realiza y completa una solicitud de contenido. El contenido está regido por reglas de actividades y experiencias controladas por especialistas en marketing y se segmenta para cada visitante del sitio. El contenido se proporciona con la mayor probabilidad de que cada visitante del sitio responda, interactúe o, en última instancia, compre. El contenido personalizado ayuda a maximizar las tasas de respuesta, las tasas de adquisición y los ingresos.

En [!DNL Target], cada elemento de la página forma parte de una única experiencia para toda la página. Cada experiencia puede incluir varios elementos en la página.

El contenido que se muestra a los visitantes depende del tipo de actividad que cree:

### Prueba A/B

El contenido que se muestra en una prueba A/B básica se elige aleatoriamente entre las experiencias que se asignan a la actividad. Puede asignar los porcentajes de asignación de tráfico para cada experiencia. Como resultado de esta división aleatoria del tráfico, puede tomar una cantidad significativa de tráfico inicial antes de que los porcentajes se igualen. Por ejemplo, si crea una campaña con dos experiencias, la experiencia inicial se elige de forma aleatoria. Si hay poco tráfico, es posible que el porcentaje de visitantes se desvíe hacia una experiencia. A medida que aumenta el tráfico, los porcentajes se igualan.

Se pueden especificar los objetivos de porcentaje para cada experiencia. En este caso, se genera un número aleatorio que se utiliza para elegir la experiencia que se mostrará. Es posible que los porcentajes resultantes no coincidan exactamente con los objetivos especificados, pero con más tráfico resulta necesario dividir las experiencias para aproximarse a los objetivos.

1. Un cliente solicita una página al servidor y esta se muestra en el navegador.
2. Se establece una cookie de origen en el explorador del cliente para almacenar el comportamiento del cliente.
3. La página realiza una llamada al sistema de segmentación.
4. El contenido se muestra en función de las reglas establecidas para la actividad.

Para obtener más información, consulte [Creación de pruebas A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

### Asignación automática

La asignación automática identifica un ganador entre dos o más experiencias. La asignación automática reasigna automáticamente más tráfico a la experiencia ganadora, lo que ayuda a aumentar las conversiones mientras la prueba continúa ejecutándose y aprendiendo.

Para obtener más información, consulte [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

### Segmentación automática (AT)

El Destinatario automático utiliza aprendizaje automático avanzado para seleccionar entre varias experiencias definidas por especialistas en marketing de alto rendimiento. El Destinatario automático ofrece la experiencia más adaptada a cada visitante. Experience envío se basa en perfiles de clientes individuales y en el comportamiento de visitantes anteriores con perfiles similares. Utilice el Destinatario automático para personalizar el contenido y dirigir las conversiones.

Para obtener más información, consulte [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md).

### Personalización automatizada (AP)

Automated Personalization (AP) combina ofertas o mensajes y utiliza aprendizaje automático avanzado para hacer coincidir las distintas variaciones de oferta con cada visitante. Experience envío se basa en perfiles de cliente individuales para personalizar el contenido y dirigir el alza.

Para obtener más información, consulte [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9).

### Segmentación de experiencias (XT)

Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.

La segmentación de experiencias, incluyendo Geotargeting, sirve para definir reglas que dirigen un contenido o experiencia determinados a una audiencia concreta. En una actividad se pueden definir varias reglas para entregar diversas variaciones de contenido a distintas audiencias. Cuando los visitantes ven el sitio, Segmentación de experiencias (XT) los evalúa para determinar si cumplen los criterios establecidos. En caso afirmativo, participan en la actividad y se les muestra la experiencia diseñada para clasificar audiencias. Puede crear experiencias para varias audiencias dentro de una misma actividad.

Consulte [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obtener más información.

### Prueba multivariable (MVT)

Multivariate Testing (MVT) compara combinaciones de ofertas en elementos de una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica. MVT ayuda a identificar qué elemento tiene mayor impacto en el éxito de la actividad.

Consulte [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obtener más información.

### Recommendations

Las actividades de Recommendations muestran automáticamente productos o contenido que podría interesar a sus clientes en función de la actividad previa del usuario u otros algoritmos. Recommendations le ayuda a dirigir a los clientes hacia artículos relevantes que es posible que no conozcan de otra manera.

Para obtener más información, consulte [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

## La red Edge {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

&quot;Edge&quot; es una arquitectura de servidores distribuidos geográficamente que garantiza tiempos de respuesta óptimos para los visitantes que solicitan contenido, independientemente de su ubicación en todo el mundo.

Para mejorar los tiempos de respuesta, [!DNL Target] Bordes hospeda únicamente lógica de actividad, perfiles en caché e información de oferta.

Las bases de datos de contenido y actividad, los [!DNL Analytics] datos, las API y las interfaces de usuario de los especialistas en mercadotecnia se alojan en los clústeres centrales de Adobe. Las actualizaciones se envían a los [!DNL Target] bordes. Los clústeres centrales y los clústeres de Edge se sincronizan automáticamente para actualizar continuamente los datos de actividad en caché. Todos los modelos 1:1 también se almacenan en cada borde, por lo que las solicitudes más complejas también se pueden procesar en el borde.

Cada clúster de Edge tiene toda la información necesaria para responder a la solicitud de contenido del visitante y rastrear los datos de análisis de dicha solicitud. Las solicitudes de visitante se dirigen al clúster de Edge más cercano.

Para obtener más información, consulte el documento técnico [Información general sobre la seguridad de Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

La solución [!DNL Target] se aloja en centros de datos de propiedad de Adobes y alquilados por Adobes en todo el mundo.

Las ubicaciones de clúster central contienen un centro de recopilación de datos y un centro de procesamiento de datos. Las ubicaciones de clúster de Edge contienen solo un centro de recopilación de datos. Cada grupo de informes está asignado a un centro de procesamiento de datos específico.

Los datos de actividad del sitio del cliente son recopilados por los siete clústeres de Edge más cercanos. Estos datos se dirigen al destino de clúster central predeterminado de un cliente (una de las tres ubicaciones: Oregón, Dublín, Singapur) para su procesamiento. Los datos de perfil de visitante se almacenan en el clúster de Edge más cercano al visitante del sitio. Las ubicaciones de clústeres perimetrales incluyen las ubicaciones de Cluster Central y Virginia, Amsterdam, Sydney, Tokio y Hong Kong.

En lugar de responder a todas las solicitudes de segmentación desde una sola ubicación, el clúster de Edge más cercano al visitante procesa las solicitudes. Este proceso ayuda a mitigar el impacto del tiempo de viaje en red/Internet.

![Tipos de mapas de servidores Destinatario](/help/c-intro/assets/target-servers.png)

[!DNL Target] Los clústeres centrales, alojados en los servicios web de Amazon (AWS), incluyen:

* Oregón, EE.UU.
* Dublín, Irlanda
* República de Singapur

[!DNL Target] Los clústeres de Edge, alojados en AWS, incluyen:

* Bombay, India
* Tokio, Japón
* Virginia, EE.UU.
* Oregón, EE.UU.
* Sídney, Australia
* Dublín, Irlanda
* República de Singapur

El servicio [!DNL Target Recommendations] está alojado en un centro de datos [!DNL Adobe] en Oregon.

>[!IMPORTANT]
>
>[!DNL Adobe Target] actualmente no tiene un clúster perimetral en China y el rendimiento del visitante sigue siendo limitado para  [!DNL Target] los clientes en China. Debido al cortafuegos y a la falta de clústeres perimetrales dentro del país, las experiencias de los sitios con [!DNL Target] implementación pueden verse afectadas. Las experiencias pueden procesarse con lentitud y las cargas de página pueden verse afectadas. Además, los especialistas en marketing pueden experimentar latencia al utilizar la IU de creación [!DNL Target].

Si lo desea, puede lista de permitidos [!DNL Target] clústeres de Edge. Para obtener más información, consulte [nodos de borde de Destinatario de lista de permitidos](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Experiencia de usuario protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

Adobe garantiza que la disponibilidad y el rendimiento de la infraestructura de segmentación sea lo más segura posible. Sin embargo, un desglose de comunicación entre el navegador de un visitante y los servidores de Adobe puede provocar una interrupción del envío de contenido.

Para protegerse contra interrupciones del servicio y problemas de conectividad, todas las ubicaciones están configuradas para incluir contenido predeterminado (definido por el cliente). Este contenido predeterminado se muestra si el explorador del usuario no se puede conectar a [!DNL Target].

No se realiza ningún cambio en la página si el explorador del usuario no se puede conectar en un plazo de tiempo de espera definido (de manera predeterminada: 15 segundos). Si se alcanza este umbral de tiempo de espera, se muestra el contenido de ubicación predeterminado.

Adobe protege la experiencia del usuario al optimizar y garantizar el rendimiento.

* Adobe garantiza pruebas de referencia de rendimiento que se basan en estándares del sector (avaladas por el contrato de nivel de servicio de Adobe).
* La red de Edge garantiza que la entrega de datos se realice a tiempo.
* Adobe utiliza un enfoque de varios niveles para garantizar sus aplicaciones y proporcionar la máxima disponibilidad y fiabilidad a sus clientes.
* Los servicios de asesoramiento de [!DNL Target] ofrecen asistencia para la implementación y soporte continuado para los productos.

## Pruebas sencillas para la optimización del motor de búsqueda (SEO){#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] se adhiere a las directrices de motores de búsqueda en las pruebas.

Google anima a los usuarios a realizar pruebas. Google afirma en su documentación que A/B y Multivariate Testing no perjudican las clasificaciones orgánicas de los motores de búsqueda si se siguen ciertas pautas.

Para obtener más información, consulte los siguientes recursos de Google:

* [Pruebas en sitios web y Búsqueda de Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos y encubrimiento](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

Las directrices se publicaron en una entrada del [blog Google Webmaster Central](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Aunque la publicación es de 2012, sigue siendo la información más reciente de Google sobre este tema y las directrices continúan vigentes.

* **Sin encubrimiento**: El cierre muestra un conjunto de contenido a los usuarios y otro diferente a los bots de los motores de búsqueda. El encubrimiento se logra identificando específicamente a los bots y alimentándolos a propósito con diferentes contenidos.

   [!DNL Target], como plataforma, se ha configurado para que trate a los bots de los motores de búsqueda como a cualquier usuario. Como resultado, se pueden incluir bots en las actividades si los bots están seleccionados al azar y &quot;ver&quot; las variaciones de la prueba.

* **Use rel=&quot;canonical&quot;**: A veces, una prueba A/B debe configurarse con distintas direcciones URL para las variaciones. En estos casos, todas las variaciones deben contener una etiqueta de `rel="canonical"` que haga referencia a la URL (de control) original. Como ejemplo, supongamos que Adobe está probando su página de inicio mediante distintas direcciones URL para cada variación. La siguiente etiqueta canónica para la página de inicio iría en la etiqueta `<head>` para cada una de las variaciones:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Utilice redirecciones** 302 (temporales): En los casos en que se utilizan direcciones URL independientes para las páginas de variación en una prueba, Google recomienda utilizar una redirección 302 para dirigir el tráfico hacia las variaciones de prueba. El redireccionamiento 302 indica a los motores de búsqueda que el redireccionamiento es temporal y solo está activo mientras se esté ejecutando la prueba.

   Una redirección 302 es una redirección del lado del servidor y [!DNL Target], junto con la mayoría de los proveedores de optimización, utiliza capacidades del lado del cliente. Por lo tanto, las redirecciones es un área en la que [!DNL Target] no cumple completamente con las recomendaciones de Google. Sin embargo, esta práctica sólo afecta a una pequeña fracción de las pruebas. El método estándar para ejecutar pruebas mediante [!DNL Target] requiere cambiar el contenido dentro de una sola dirección URL, por lo que no es necesario realizar redirecciones. Hay instancias en las que los clientes deben utilizar varias direcciones URL para representar sus variaciones de prueba. En estos casos, [!DNL Target] utiliza el comando JavaScript `window.location`. Este comando dirige a los usuarios a probar las variaciones, lo que no significa explícitamente si la redirección es 301 o 302.

   Adobe continúa buscando soluciones viables para alinearse completamente con las pautas de los motores de búsqueda. Para aquellos clientes que deben utilizar direcciones URL independientes para realizar pruebas, Adobe confía en que la correcta implementación de las etiquetas canónicas mitigue el riesgo asociado con este método.

* **Ejecute los experimentos únicamente mientras sea necesario**: Adobe cree que &quot;mientras sea necesario&quot; es el tiempo que se necesita para alcanzar una relevancia estadística. [!DNL Target] [sugiere prácticas recomendadas](https://docs.adobe.com/content/target-microsite/testcalculator.html) para determinar el momento en que una prueba ha alcanzado este punto. Adobe recomienda incorporar la implementación codificada de pruebas ganadoras en el flujo de trabajo de prueba y asignar los recursos adecuados.

   No se recomienda utilizar la plataforma [!DNL Target] para &quot;publicar&quot; pruebas ganadoras como solución permanente. Si la prueba ganadora se publica para el 100 % de los usuarios el 100 % de las veces, este método se puede utilizar mientras se completa el proceso de codificar la prueba ganadora.

   También es importante tener en cuenta lo que la prueba ha cambiado. La simple actualización del color de los botones u otros elementos menores no basados en texto en la página no influye en las clasificaciones orgánicas. No obstante, los cambios realizados en el texto se deben incrustar en el código.

   Tampoco hay que olvidar la accesibilidad de la página que se está probando. Si los motores de búsqueda no pueden acceder a la página y nunca se diseñó para clasificarla en la búsqueda orgánica en primer lugar, no se aplica ninguna de las consideraciones anteriores. Un ejemplo es una página de aterrizaje dedicada a una campaña de correo electrónico.

Desde Google afirman que estas directrices “harán que las pruebas tengan un impacto mínimo o nulo en los resultados de búsqueda del sitio”.

Además de estas directrices, Google también proporciona otra pauta en la documentación de la herramienta Experimentos con contenido:

* “Las páginas de variación deben mantener la esencia del contenido en las páginas originales. Estas variaciones no deben cambiar la percepción general ni el significado de esta que el usuario tiene del contenido original”.

Google pone el ejemplo de que “si la página original de un sitio se carga con palabas clave que no están relacionadas con las combinaciones que se muestran a los usuarios, nos reservamos el derecho a eliminar el sitio de nuestro índice”.

Adobe considera que sería difícil cambiar de forma involuntaria el significado del contenido original en las variaciones de prueba. Sin embargo, Adobe recomienda tener en cuenta las temáticas de palabras clave en una página y mantener dichas temáticas. Al cambiar el contenido de una página, especialmente añadiendo o eliminando palabras clave importantes, puede variar la clasificación de la URL en la búsqueda orgánica. Adobe recomienda que se involucre con su socio SEO como parte del protocolo de prueba.

## Bots {#bots}

Adobe [!DNL Target] utiliza la métrica [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) &quot;isRobot&quot; para detectar bots conocidos basados en la cadena del agente de usuario pasada en el encabezado de solicitud.

>[!NOTE]
>
> Para las solicitudes [!DNL Server-Side], el valor pasado en el nodo [&quot;Contexto&quot; de la solicitud](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tiene prioridad sobre la cadena del agente de usuario para la detección de bots.

El tráfico que se identifica como generado por un bot sigue siendo contenido servido. Los bots se tratan como un usuario normal para asegurarse de que [!DNL Target] esté de acuerdo con las pautas de SEO. El uso del tráfico de bots puede afectar a las pruebas A/B o los algoritmos de personalización, si se tratan como usuarios normales. Por lo tanto, si se detecta un bot conocido en la actividad [!DNL Target], el tráfico se trata de forma ligeramente diferente. La eliminación del tráfico de bots proporciona una medición más precisa sobre la actividad del usuario.

Específicamente, para el tráfico de bots conocido [!DNL Target] no:

* Crea ni recupera un perfil de visitante.
* Registra atributos de perfil ni ejecuta scripts de perfil.
* Busca segmentos de Adobe Audience Manager (AAM) (si corresponde).
* Usar el tráfico de bots en el modelado y el servicio de contenido personalizado para actividades de Recommendations, Destinatario automático, Automated Personalization o asignación automática
* Registra una visita de actividad para la creación informes.
* Los datos de registro que se enviarán a la plataforma [!DNL Adobe Experience Cloud]
